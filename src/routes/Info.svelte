<script lang="ts">
  import { Heading } from "flowbite-svelte";
  import ProductInfo from "./ProductInfo.svelte";
  import UserInfo from "./UserInfo.svelte";
  import type { User } from "$lib/user";
  import type { Product } from "$lib/product";

  export let users: User[];
  export let products: Product[];
</script>

<div class="flex flex-col w-full">
  <div class="flex flex-row w-full">
    <ProductInfo {products} />
    <br />
    <hr />
    <br />
    <UserInfo {users} />
  </div>
</div>
