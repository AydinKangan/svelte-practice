<script lang="ts">
  import type { User } from "$lib/user";
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

  export let users: User[];

  function deleteClickHandler(user: User) {
    users = users.filter((u) => u.username !== user.username);
  }
</script>

<div class="p-5 w-full border-solid border-2">
  <Heading tag="h3">Users</Heading>
  <Table>
    <TableHead>
      <TableHeadCell>Username</TableHeadCell>
      <TableHeadCell>First Name</TableHeadCell>
      <TableHeadCell>Last Name</TableHeadCell>
    </TableHead>
    <TableBody>
      {#each users as user}
        <TableBodyRow>
          <TableBodyCell>{user.username}</TableBodyCell>
          <TableBodyCell>{user.firstName}</TableBodyCell>
          <TableBodyCell>{user.lastName}</TableBodyCell>
          <TableBodyCell
            ><CloseCircleSolid
              on:click={() => deleteClickHandler(user)}
            /></TableBodyCell
          >
        </TableBodyRow>
      {/each}
    </TableBody>
  </Table>
</div>
