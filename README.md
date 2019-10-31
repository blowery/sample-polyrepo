# Welcome to All the Things
This is a sample polyrepo. What's a polyrepo? It's a set of normal git repos all inside one repository. It should feel like a normal set of git checkouts in a folder, with each checkout able to work independently.
 
## Workflow
Working in the polyrepo is very similar to working with a set of git checkouts in a folder. Everything is independent, though we can reference things across folders if that's helpful. 

For example, if you want to work on `@automattic/components` you would:
```
cd packages/components;
npm i;
npm test;
npm run storybook;
```
Just like you would in a normal environment.

If you want to build and run Calypso:
```
cd apps/calypso;
npm i;
npm start;
```
Now, if you want to work on `@automattic/components` _and see how they're used in Calypso_ you use `npm link` and a special build flag.
```
cd apps/calypso;
npm link ../../packages/components;
FOLLOW_SYMLINKS=true npm start;
```
When you're done, just `npm unlink


## Adding a new "repo"
Just add a new folder. If you're building a reusable npm package, place it under `packages`. If you're building an application that builds and runs, place it under `apps`. If you're building something else, ping @team-calypso. 

That's it!

