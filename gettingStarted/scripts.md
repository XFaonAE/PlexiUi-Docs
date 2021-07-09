## Scripts
PlexiUI is powered by scripts, the entire framework is powered by **TypeScript** but plain **JavaScript** can work just as fine too. We recommend you stay with **TypeScript** if your familiar with it.

When we ran the command `npm run app:dev`, NPM started a script titled `Main.ts`. This script is supposed to run that development server powering your app!

Let's try modifying it to do something else.
Update your `Main.ts` file inside of the `src` folder.
```typescript
import PlexiUi from "../axeri/plexiui/PlexiUi.ts";

new class Main {
    /**
     * Dev script entry
     */
    public constructor() {
        // Create PlexiUi
        const plexiUi = new PlexiUi();

        // Set the options
        plexiUi.setOptions({
            // Run in dev mode
            mode: "dev",

            // Skip a task
            skip: {
                // Skip the renderer task
                renderer: true
            }
        });

        // Run the app
        plexiUi.run();
    }
}
```
We placed many comments to make it easy to understand

Now try running the app with the same command we used last time: `npm run app:dev`.
Watch the output, see how it skipped the renderer task. When the window launched, you will see a white screen without any window frame buttons.

They don't render because we stopped the renderer task.
There are many other options you can set, these are just a few.

## Options
Now we will take a look at all of the options for the script.
As shown before, options can be set with the following method.
```ts
plexiUi.setOptions({
    { ... } // Options
});
```

### Mode
`options.mode`
```ts
{
    mode: { ... }
}
```
Set the mode for the script
Type | Key | Desc
---- | --- | ----
`"dev" | "pack"` | `options.mode` | Run the script in in a task mode

### Skip
`options.skip`

```ts
{
    skip: {
        { ... }
    }
}
```
Skip tasks for the tasks runner
Type | Key | Desc
---- | --- | ----
boolean | `options.skip.renderer` | Skip any tasks for the renderer
boolean | `options.skip.window` | Skip any tasks for the window

 - Next: []()<br />
 - Prev: [Basic Setup](./basicSetup.md)
