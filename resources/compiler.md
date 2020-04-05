---
description: Create ready to use binary from source files
---

# Compiler

### Installation

With `NPM`:

```
$ npm i @rapid-lang/compiler -g
```

{% hint style="info" %}
To run compiler you will need **Node 12** or newer. Go to [https://nodejs.org/en/download/](https://nodejs.org/en/download/) to get installation files.
{% endhint %}

{% hint style="success" %}
[Rapid Compiler](compiler.md) and [Rapid CLI](cli.md) works on **OS X**, **Windows** and **Linux**.
{% endhint %}

### Example usage

Compiles `file.rapid` and outputs `app.wasm` with sourcemaps ready to be run in browser.

{% tabs %}
{% tab title="Bash" %}
```text
$ rapid-compiler file.rapid -o app.wasm -s
```
{% endtab %}

{% tab title="file.rapid" %}
```javascript
function main(): int {
  return 12
}
```
{% endtab %}

{% tab title="Text Format \(WAT\)" %}
```
(module
 (type $none_=>_i32 (func (result i32)))
 (export "main" (func $main))
 (func $main (; 0 ;) (; has Stack IR ;) (result i32)
  ;;@ file.rapid:2:1
  (i32.const 12)
 )
)
```
{% endtab %}

{% tab title="Linear assembly bytecode" %}
```
func (result i32)
  i32.const 12
end
```
{% endtab %}
{% endtabs %}

### API

```text
Commands:
  index.js source  Path to source file to be compiled

Options:
  -o, --output      Path to result file to be saved          [string] [required]
  -h, --help        Show help                                          [boolean]
  -v, --version     Show version number                                [boolean]
  -s, --sourceMaps  Generate sourceMaps for debugging                  [boolean]
  -t, --textFormat  Generate WebAssembly Text Format (wat) file         [string]
  -p, --port        Sourcemaps default port                             [number]
```

