# typescript-run

> **Warning**
>
> Deprecated. I started this project to-
> - Execute typescript files faster 
> - have a `--watch` mode on them.
>
> [Bun](https://bun.sh/) has solved for both the cases in more performant way. So do check it out instead.
>
> You can also checkout [tsx](https://github.com/esbuild-kit/tsx) which has solved for both the cases as well.

[ts-node](https://npmjs.com/package/ts-node) but extremely fast ⚡️ 

Uses [esbuild](https://npmjs.com/package/esbuild) to compile TypeScript to JavaScript.

[Run Demo on StackBlitz](https://stackblitz.com/edit/node-vhctbs?file=index.ts)
## Install

Install globally
```sh
npm i -g typescript-run

ts-run ./src/index.ts
```

*or*

Execute with `npx`
```sh
npx typescript-run ./src/index.ts
```

## Usage

`ts-run` is an alias to `typescript-run`. You can use either of them.

```sh
typescript-run <file-path> # or `ts-run <file-path>`
```

### Options

#### Watch Mode 

Pass `--watch` or `-w` flag to enable watch mode. This will listen to your file changes and re-run the script.

```sh
ts-run src/index.ts --watch
```

By default, watch flag will watch over the files that are going to part of your bundle (`.ts` `.js` files imported in entry file). You can also override this behavior by passing path to `--watch` flag with-
```sh
ts-run src/index.ts --watch src
```

This will watch over all the changes in `src` folder.

You can also pass multiple directories with `--watch src examples`. This will watch over `src` and `examples` both

## When to use?

Use `tsc` for builds and `typescript-run` for dev-mode.

*Warning:*
- *Not ready for serious projects*
- *Make sure you check out [ESBuild TypeScript Caveats](https://esbuild.github.io/content-types/#typescript-caveats) first.*

## Why esbuild?

- Esbuild does not do type-checking which makes the TypeScript to JavaScript compilation super fast!
- Type-checking is not a blocker for running scripts in dev-mode. IDEs can handle it as well as you can individually run `tsc` in emit mode.


Thanks! Have fun 🌻