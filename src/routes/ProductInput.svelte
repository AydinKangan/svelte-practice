<script lang="ts">
  import type { Product } from "$lib/product";
  import { Button, Input } from "flowbite-svelte";

  let productId: number = 0;
  let productName: string = "";
  let productQty: number = 0;
  let productPrice: number = 0.0;

  export let product: Product;

  const handleSubmit = () => {
    const newProduct = {
      id: Number(productId),
      name: productName,
      quantity: productQty,
      price: productPrice,
    };

    product = newProduct;

    productId = 0;
    productName = "";
    productQty = 0;
    productPrice = 0.0;
  };
</script>

<div>
  <form on:submit={handleSubmit}>
    <Input type="number" placeholder="Product ID" bind:value={productId} />
    <Input type="text" placeholder="Product Name" bind:value={productName} />
    <Input
      type="number"
      placeholder="Product Quantity"
      bind:value={productQty}
    />
    <Input
      type="number"
      placeholder="Product Price"
      bind:value={productPrice}
    />
    <Button type="submit">Add Product</Button>
  </form>
</div>
