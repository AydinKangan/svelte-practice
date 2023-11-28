<script lang="ts">
  import { Alert, Heading } from "flowbite-svelte";
  import InputComponent from "./InputComponent.svelte";
  import type { User } from "$lib/user";
  import type { Product } from "$lib/product";
  import Info from "./Info.svelte";

  let products: Product[] = [
    {
      id: 0,
      name: 'Apple MacBook Pro 17"',
      quantity: 10,
      price: 2999,
    },
    {
      id: 1,
      name: "Microsoft Surface Pro",
      quantity: 5,
      price: 1999,
    },
    {
      id: 2,
      name: "Magic Mouse 2",
      quantity: 90,
      price: 99,
    },
  ];
  let users: User[] = [
    { username: "jsmith", firstName: "John", lastName: "Smith" },
    { username: "sbrown", firstName: "Sarah", lastName: "Brown" },
    { username: "dduck", firstName: "Donald", lastName: "Duck" },
    { username: "mmouse", firstName: "Minnie", lastName: "Mouse" },
  ];

  let product: Product;
  let user: User;

  let productError: boolean = false;
  let userError: boolean = false;

  let error: string = "";

  $: {
    if (product) {
      productError = false;
      userError = false;
      const isProductIdTaken = products.some((p) => p.id === product.id);
      if (!isProductIdTaken) {
        products = [...products, product];
      } else {
        productError = true;
      }
    }

    if (user) {
      userError = false;
      productError = false;
      const isUsernameTaken = users.some((u) => u.username === user.username);
      if (!isUsernameTaken) {
        users = [...users, user];
      } else {
        userError = true;
      }
    }
  }

  $: {
    if (userError) {
      error = "username";
    } else if (productError) {
      error = "product id";
    } else {
      error = "";
    }
  }
</script>

<div class="flex flex-col items-center">
  {#if error}
    <Alert>
      <span class="font-medium">Invalid Data!</span>
      Make sure the {error} is unique.
    </Alert>
  {/if}
  <Heading class="text-center">Practice Exercise 2</Heading>
  <br />
  <div class="flex flex-col w-10/12 items-center border-solid border-2 p-2">
    <InputComponent bind:user bind:product />
  </div>
  <div class="flex flex-col w-10/12 items-center border-solid border-2 p-2">
    <Info {users} {products} />
  </div>
</div>
