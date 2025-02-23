# README

## About

This is a Wails template using Svelte & Tailwindcss with Vite for asset bundling. Immediately after installing do the following:
 1. Make sure you have **[wails v2](https://github.com/wailsapp/wails/tree/master/v2)** installed!
 2. Run `wails init -n $yourProjectName -t https://github.com/charlie-dee/wails-vite-svelte-tailwindcss-template`
 3. Run `npm install` from within the `frontend/` dir to install the JS dependencies
 4. Run `wails build` from the project root dir to build the `dist/` directory for the first time. Completing this is also a good first test.


## Live Development

To run in live development mode, go into the `frontend/` directory and run `npm run dev`. 
Then, in another terminal, run `wails dev` in the project directory. 
You can navigate to http://localhost:34115 in your browser to connect to your application or (preferably) just work off of the Wails app that launches via `wails dev`.

Changes made to frontend source files in should trigger Vite to reload and changes to any .go files should trigger Wails to recompile and reload.

## Building

To build a redistributable, production mode package, use `wails build`.

## Issues

From time to time I have noticed that the live reload seems to stop working, especially for the JS side. 
Normally, closing both dev servers and relaunching, starting with `npm run dev` in `frontend/` 
followed by `wails dev` in the project root seems to take care of that.


## Caveats

By default, Vite does not bundle source files when previewing with the dev server. 
It essentially acts as a no-bundle dev server, using the source files. 
This is feature needs to basically be disabled to function alongside of the Wails dev server.
Therefore, you will notice that the frontend is being rebuilt when Vite sees a change.
This is accomplished by changing the `npm run dev` command from `vite` to `vite build --watch` in `/frontend/package.json`.

As of this writing, Jan 2022, I have only tested this on macOS. I have yet to get a Windows dev environment set up. 
If you try this on Windows, I would appreciate it if you'd let me know how it went.


## Shout-Outs

Being new to both Vite and Wails, the above-mentioned caveat gave me quite a fit for a while, 
but after comparing the `package.json` and `vite.config.js` files in the Wails + Vite + View templates with those 
generated by the Vite-Svelte scaffolded template, I was able to finally get it working. 
You can get more information about the Wails + Vite + View templates here:

 - https://github.com/codydbentley/wails-vite-vue-the-works
 - https://github.com/codydbentley/wails-vite-vue-ts