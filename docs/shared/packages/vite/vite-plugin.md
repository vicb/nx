The Nx plugin for [Vite](https://vitejs.dev/) and [Vitest](https://vitest.dev/).

[Vite.js](https://vitejs.dev/) is a build tool that aims to provide a faster and leaner development experience for modern web projects.

Why should you use this plugin?

- Instant dev server start
- Lightning fast Hot-Module Reloading
- _Fast_ builds using Vite.
- Vite-powered tests with smart and instant watch mode

Read more about Vite and Vitest in the [Vite documentation](https://vitejs.dev/).

## Setting up a new Nx workspace with Vite

You can create a new workspace that uses Vite with one of the following commands:

- Generate a new monorepo with a Web Components app set up with Vite

```shell
npx create-nx-workspace@latest --preset=web-components
```

- Generate a new standalone React app set up with Vite

```shell
npx create-nx-workspace@latest --preset=react-standalone
```

## Add Vite to an existing workspace

There is a number of ways to use Vite in your existing workspace.

### Generate a new project using Vite

You can generate a [React](/packages/react) application or library or a [Web](/packages/web) application that uses Vite.js. The [`@nrwl/react:app`](/packages/react/generators/application), [`@nrwl/react:lib`](/packages/react/generators/library) and [`@nrwl/web:app`](/packages/web/generators/application) generators accept the `bundler` option, where you can pass `vite`. This will generate a new application configured to use Vite.js, and it will also install all the necessary dependencies, including the `@nrwl/vite` plugin.

To generate a React application using Vite.js, run the following:

```bash
nx g @nrwl/react:app my-app --bundler=vite
```

To generate a React library using Vite.js, run the following:

```bash
nx g @nrwl/react:lib my-lib --bundler=vite
```

To generate a Web application using Vite.js, run the following:

```bash
nx g @nrwl/web:app my-app --bundler=vite
```

### Modify an existing React or Web project to use Vite.js

You can use the `@nrwl/vite:configuration` generator to change your React or Web project to use Vite.js. This generator will modify your project's configuration to use Vite.js, and it will also install all the necessary dependencies, including the `@nrwl/vite` plugin..

You can read more about this generator on the [`@nrwl/vite:configuration`](/packages/vite/generators/configuration) generator page.

### Initialize Vite.js

If you do not want to create any new projects or convert any existing projects yet, you can still use Nx to install all the necessary dependencies for Vite.js. This, for example, could be useful if you want to set up Vite.js manually for a project.

#### Install the `@nrwl/vite` plugin

{% tabs %}
{% tab label="npm" %}

```shell
npm install -D @nrwl/vite
```

{% /tab %}
{% tab label="yarn" %}

```shell
yarn add -D @nrwl/vite
```

{% /tab %}
{% tab label="pnpm" %}

```shell
pnpm install -D @nrwl/vite
```

{% /tab %}
{% /tabs %}

#### Ask Nx to install the necessary dependencies

After you install the plugin, you can initialize Vite.js. You can do this by running the `init` executor. This executor will make sure to install all the necessary dependencies.

```bash
nx g @nrwl/vite:init
```

{% callout type="note" title="Choosing a framework" %}
You will notice that the generator will ask you of the framework you are planning to use. This is just to make sure that the right dependencies are installed. You can always install manually any other dependencies you need.
{% /callout %}
