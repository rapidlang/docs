---
description: Create ready to use binary from source files
---

# Compiler

## Installation

With `NPM`:

```
$ npm i rapid-lang -g
```

or `Yarn`:

```text
$ yarn global add rapid-lang
```

{% hint style="info" %}
To run compiler you will need **Node 12** or newer. Go to [https://nodejs.org/en/download/](https://nodejs.org/en/download/) to get installation files.
{% endhint %}

### Example usage

Compiles `file.rapid` and outputs `app.wasm` with `sourcemaps` ready to be run in browser.

{% tabs %}
{% tab title="Bash" %}
```text
$ wasm -f file.rapid -o app.wasm -s
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

**`--help`** Show help **\[boolean\]**

**`--version`** Show version number **\[boolean\]**

**`-f, --file`** Path to source file to be compiled **\[string\] \[required\]**

**`-o, --output`** Path to result file to be saved **\[string\] \[required\]**

**`-s, --sourceMaps`** Generate sourceMaps for debugging **\[boolean\]**

**`-t, --textFormat`** Generate WebAssembly Text Format \(wat\) file **\[string\]**
