<script lang="ts">
  import type { Product } from "$lib/product";
  import type { User } from "$lib/user";
  import ProductInput from "./ProductInput.svelte";
  import UserInput from "./UserInput.svelte";

  export let user: User;
  export let product: Product;
</script>

<div class="flex flex-col w-10/12">
  <ProductInput bind:product />
  <br />
  <hr />
  <br />
  <UserInput bind:user />
</div>
