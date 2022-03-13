# Svelte Countdown

![image](https://user-images.githubusercontent.com/13539403/158040553-6f75b76c-7b9c-45d2-accb-1378bc867ada.png)

<p align=center>
  Simple countdown application to try out the Svelte approach of building websites.
</p>

## About

- The project makes usage of pure CSS and global variables, those can be found at `src/App.svelte`;
- TypeScript was used to build the application, this can be achieved by running a script that comes with the default template;
- No external libraries other than svelte, rollup and typescript (default ones);

## Impressions

The reactive nature of all the variables is really cool, and I doubt any React developer will say otherwise. Still, some things still bother me, for example: the way that you use javascript blocks to dynamically render things, which reminds me a lot of WASM in solutions like Blazor (C#) and can get quite messy pretty fast.

Another thing that I am not a fan of is the way that you must have a section for styles within the rest of the component, something that I always avoid with react to separate things for a better developer experience.

I still find it quite impressive and I'm willing to learn more with time.
