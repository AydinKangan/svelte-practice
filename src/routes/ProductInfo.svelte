<script lang="ts">
  import type { Product } from "$lib/product";
  import {
    Heading,
    Table,
    TableBody,
    TableBodyCell,
    TableBodyRow,
    TableHead,
    TableHeadCell,
  } from "flowbite-svelte";
  import { CloseCircleSolid } from "flowbite-svelte-icons";

  export let products: Product[] = [];

  function deleteClickHandler(product: Product) {
    products = products.filter((p) => p.id !== product.id);
  }
</script>

<div class="p-5 w-full border-solid border-2">
  <Heading tag="h3">Products</Heading>
  <Table>
    <TableHead>
      <TableHeadCell>Id</TableHeadCell>
      <TableHeadCell>name</TableHeadCell>
      <TableHeadCell>Quantity</TableHeadCell>
      <TableHeadCell>Price</TableHeadCell>
    </TableHead>
    <TableBody>
      {#each products as product}
        <TableBodyRow>
          <TableBodyCell>{product.id}</TableBodyCell>
          <TableBodyCell>{product.name}</TableBodyCell>
          <TableBodyCell>{product.quantity}</TableBodyCell>
          <TableBodyCell>${product.price}</TableBodyCell>
          <TableBodyCell
            ><CloseCircleSolid
              on:click={() => deleteClickHandler(product)}
            /></TableBodyCell
          >
        </TableBodyRow>
      {/each}
    </TableBody>
  </Table>
</div>
