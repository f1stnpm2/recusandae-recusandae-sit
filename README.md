# @f1stnpm2/recusandae-recusandae-sit

Performance-minded React linting rules for ESLint (motivated by [esamatti](https://twitter.com/esamatti)'s post ["React.js pure render performance anti-pattern"](https://medium.com/@esamatti/react-js-pure-render-performance-anti-pattern-fb88c101332f)).

# Installation

```sh
$ npm i @f1stnpm2/recusandae-recusandae-sit
```

Add `plugins` section and specify @f1stnpm2/recusandae-recusandae-sit as a plugin.

```json
{
  "plugins": ["react-perf"]
}
```

# List of supported rules

- [react-perf/jsx-no-new-object-as-prop](docs/rules/jsx-no-new-object-as-prop.md): Prevent `{...}` as JSX prop value
- [react-perf/jsx-no-new-array-as-prop](docs/rules/jsx-no-new-array-as-prop.md): Prevent `[...]` as JSX prop value
- [react-perf/jsx-no-new-function-as-prop](docs/rules/jsx-no-new-function-as-prop.md): Prevent `function` as JSX prop value
- [react-perf/jsx-no-jsx-as-prop](docs/rules/jsx-no-jsx-as-prop.md): Prevent JSX as JSX prop value

# Configuration

As of v3.3.0, each @f1stnpm2/recusandae-recusandae-sit rule supports configuration to control whether native elements (lower case first letter React components) are ignored.

With this configuration, all native elements are ignored for this rule:

```json
{
  "react-perf/jsx-no-new-object-as-prop": [
    "error",
    {
      "nativeAllowList": "all"
    }
  ]
}
```

With this configuration, the "style" attribute is ignored for native elements for this rule:

```json
{
  "react-perf/jsx-no-new-object-as-prop": [
    "error",
    {
      "nativeAllowList": ["style"]
    }
  ]
}
```

## Recommended

This plugin exports a `recommended` configuration that enforce React good practices.

To enable this configuration use the `extends` property in your `.eslintrc` config file:

```js
{
  "extends": ["plugin:react-perf/recommended"]
}
```

See [ESLint documentation](http://eslint.org/docs/user-guide/configuring#extending-configuration-files) for more information about extending configuration files.

The rules enabled in this configuration are:

- [react-perf/jsx-no-new-object-as-prop](docs/rules/jsx-no-new-object-as-prop.md)
- [react-perf/jsx-no-new-array-as-prop](docs/rules/jsx-no-new-array-as-prop.md)
- [react-perf/jsx-no-new-function-as-prop](docs/rules/jsx-no-new-function-as-prop.md)
- [react-perf/jsx-no-jsx-as-prop](docs/rules/jsx-no-jsx-as-prop.md)

## All

This plugin also exports an `all` configuration that includes every available rule.

```js
{
  "plugins": [
    "react-perf"
  ],
  "extends": ["plugin:react-perf/all"]
}
```

# Test anti-patterns in runtime

Try out [cvazac/test-ref-pattern](https://github.com/cvazac/test-ref-pattern).

# License

@f1stnpm2/recusandae-recusandae-sit is licensed under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
