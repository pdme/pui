# pui
Pebbles UI

An example of a build setup using Rollup for a component library based on React + Tailwind. Inspired by:

* https://dev.to/alexeagleson/how-to-create-and-publish-a-react-component-library-2oe
* https://samrobbins.uk/blog/tailwind-component-library

Work flow:

* You develop your components in isolation using Storybook (excluded in this example repo for simplicity). You export your components and typings as shown in the Button example.
* Once ready to publish a new version, you build using rollup (`yarn build`). This will create a dist folder with CommonJS as well as ESM modules. Tailwind's css is purged and included in the JS bundle (you can choose to extract the css into a separate file if desired). Typings are also included and sourcemapped.
* You then bump the version number in package.json, and publish to GitHub packages (`npm publish`).

Any user with a valid read access token in their `~/.npmrc` can use the comp lib by doing (in case of LUI) `yarn add @LiveIntent/lui`. It has no dependency on Tailwind.

When coding and adding a Button, say, in your JSX, your IDE will automatically detect and suggest the Button from the comp lib.

