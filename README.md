# Next.js & NextUI PRO Template  Node v20.14.0

This is a template for creating applications using Next.js 14 (pages directory) and NextUI (v2).

[Try it on CodeSandbox](https://githubbox.com/nextui-org/next-pages-template)

>Note: Since Next.js 14, the pages router is recommend migrating to the [new App Router](https://nextjs.org/docs/app) to leverage React's latest features
>
>Read more: [Pages Router](https://nextjs.org/docs/pages)

## Technologies Used

- [Next.js 14](https://nextjs.org/docs/getting-started)
- [NextUI](https://nextui.org)
- [Tailwind CSS](https://tailwindcss.com)
- [Tailwind Variants](https://tailwind-variants.org)
- [TypeScript](https://www.typescriptlang.org)
- [Framer Motion](https://www.framer.com/motion)
- [next-themes](https://github.com/pacocoursey/next-themes)

## How to Use

To create a new project based on this template using `create-next-app`, run the following command:

```bash
npx create-next-app -e https://github.com/nextui-org/next-pages-template
```

### Install dependencies

You can use one of them `npm`, `yarn`, `pnpm`, `bun`, Example using `npm`:

```bash
npm install
```

### Run the development server

```bash
npm run dev
```

### Setup pnpm (optional)

If you are using `pnpm`, you need to add the following code to your `.npmrc` file:

```bash
public-hoist-pattern[]=*@nextui-org/*
```

After modifying the `.npmrc` file, you need to run `pnpm install` again to ensure that the dependencies are installed correctly.

## License

Licensed under the [MIT license](https://github.com/nextui-org/next-pages-template/blob/main/LICENSE).


## Install Iconify Icons

Iconify is a popular icons library that supports multiple icon sets, it has over 200,000 icons from 100+ icon sets. NextUI Pro uses Iconify icons by default to make it easier to use icons.

To use Iconify icons, you need to install the Iconify React component.

npm, yarn, pnpm

```bash
npm install --save-dev @iconify/react
```
To learn more about Iconify, please visit [Iconify React](https://iconify.design/docs/icon-components/react/)

## Install `usehooks-ts` package

Some components in NextUI Pro use the `usehooks-ts` package, which is a collection of reusable React hooks. To use these components, you need to install the `usehooks-ts` package.

npm, yarn, pnpm

```bash
npm install usehooks-ts
```
To learn more about `usehooks-ts`, please visit [usehooks-ts Documentation](https://usehooks-ts.com)

## Install `clsx` and `tailwind-merge` packages

NextUI Pro uses the `clsx` and `tailwind-merge` packages to merge TailwindCSS classNames together avoiding the TailwindCSS classes conflicts. These packages are required to create the `cn` utility function in the next step.

npm, yarn, pnpm

```bash
npm install clsx tailwind-merge
```
Add the `cn` utility function (Updated)

NextUI Pro uses the `cn` utility function to conditionally join classNames together. This is a simple utility function that you can use to join classNames together avoiding the TailwindCSS classes conflicts.

```bash
import type {ClassValue} from "clsx";

import clsx from "clsx";
import {extendTailwindMerge} from "tailwind-merge";

const COMMON_UNITS = ["small", "medium", "large"];

/**
 * We need to extend the tailwind merge to include NextUI's custom classes.
 *
 * So we can use classes like `text-small` or `text-default-500` and override them.
 */
const twMerge = extendTailwindMerge({
  extend: {
    theme: {
      opacity: ["disabled"],
      spacing: ["divider"],
      borderWidth: COMMON_UNITS,
      borderRadius: COMMON_UNITS,
    },
    classGroups: {
      shadow: [{shadow: COMMON_UNITS}],
      "font-size": [{text: ["tiny", ...COMMON_UNITS]}],
      "bg-image": ["bg-stripe-gradient"],
    },
  },
});

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}
```
To learn more about `clsx` and `tailwind-merge`, please visit [clsx](https://github.com/lukeed/clsx) and [tailwind-merge.](https://github.com/dcastil/tailwind-merge)

You are ready to use NextUI Pro 🎉

Now you can copy & paste any component from NextUI Pro and use it in your React application.

To learn more about NextUI Open Source, please visit [NextUI](https://nextui.org)
