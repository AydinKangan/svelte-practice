# Instructions
You need to make the application function.
The application needs to be able to allow a user to:
1. add a new user using the user input component
2. add a new product using the product input component
3. new users and products must display in the corresponding Info components
4. clicking on a delete button will delete the user/product from the data stored
5. (bonus) when adding a user don't allow a duplicate username
6. (bonus) when adding a product don't allow a duplicate productId

## Deliverables
Before you start coding, read the code that is there and:
1. Identify which component data for users and products is stored
2. Identify where events/interactions have to be handled on the application
3. A diagram/s showing where messages need to be sent and received.  Include the message names that you intend to use on the diagram

then
1. Complete the code

# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
