# sveltekit-adapter-browser-extension

[Adapter](https://kit.svelte.dev/docs#adapters) for SvelteKit which turns your app into a cross-platform browser extension.

## Usage

Install with `npm i -D sveltekit-adapter-browser-extension`, then add the adapter to your `svelte.config.js`, and set the appDir to something without an underscore:

```js
// svelte.config.js
import adapter from 'sveltekit-adapter-browser-extension';

export default {
	kit: {
		adapter: adapter(),
		appDir: 'ext' // This is important - chrome extensions can't handle the default _app directory name.
	}
};
```

## Try it

An example barebone app exists at `./example-app`. You can `npm run build` here and install the extension.

### To try with your own app:

Install the adapter and `npm run build`. Go to your browser's extension page and install unpacked extension - point it at the build directory within your app.

If you get an error about `_app` being a disallowed folder, delete `_app` from within the build dir. It appears there sometimes and I'm not sure why - I'll fix as soon as possible!

## Roadmap

I am looking for help to build and maintain this module. Roadmap is:

* Specifying the type of extension via config
* Allowing icons and such to be driven by configuration
* Bring-your-own manifest where you can merge a provided manifest with the generated one.

## License

[MIT](LICENSE)
