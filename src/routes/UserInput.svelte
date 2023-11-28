<script lang="ts">
  import type { User } from "$lib/user";
  import { Button, Input } from "flowbite-svelte";

  let username: string = "";
  let firstName: string = "";
  let lastName: string = "";

  export let user: User;

  const handleSubmit = () => {
    const newUser = {
      username,
      firstName,
      lastName,
    };
    user = newUser;

    username = "";
    firstName = "";
    lastName = "";
  };
</script>

<div>
  <form on:submit={handleSubmit}>
    <Input type="text" placeholder="Username" bind:value={username} />
    <Input type="text" placeholder="First Name" bind:value={firstName} />
    <Input type="text" placeholder="Last Name" bind:value={lastName} />
    <Button type="submit">Add User</Button>
  </form>
</div>
