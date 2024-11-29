# knip trace bug repro

This repository is a minimal reproduction of a bug in the [knip](https://github.com/webpro-nl/knip) package.

## Steps to reproduce

1. Clone this repository
2. Run `pnpm i`
3. Run `pnpm dump:trace`
4. Open the generated `trace.json` file.

Output:

```
src/pages/my-page/my-page.ts:MyPage x

src/index.ts ◯ x

src/components/example/my-named-component.ts:MyNamedComponent
└─ src/pages/my-page/my-page.ts ✓

src/components/example/my-default-component.ts:default x
```

You will see that the file that exported a default (my-default-component.ts) doesn't show its imports.
