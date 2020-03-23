---
description: Start in seconds
---

# Quick start

### Create some file with Rapid source code

{% tabs %}
{% tab title="main.rapid" %}
```javascript
function main(): int {
  return 12
}
```
{% endtab %}
{% endtabs %}

This is the simplest function named main which returns number 12.

### Use Rapid Compiler

If you don't have it installed yet go to [Compiler](resources/compiler.md) section. Point your `.rapid` file and compile it like:

{% tabs %}
{% tab title="Bash" %}
```bash
$ rapid main.rapid -o main.wasm
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This will output production-ready _WASM_ binary file ready to use in browser without sourcemaps and without _Webassembly Text Format_. If you want debugging or more outputs see [Compiler](resources/compiler.md) and [Debugging](resources/debugging.md) section.
{% endhint %}

### Use binary in the browser

Create a simple `.html` file and inject binary:

{% tabs %}
{% tab title="index.html" %}
```bash
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <script>
      WebAssembly.instantiateStreaming(fetch('main.wasm'), {}).then(results => {
        console.log(results.instance.exports.main());
      });
    </script>
  </head>
  <body></body>
</html>
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
This approach is using the compiler directly. You can also use [Rapid CLI](resources/cli.md) to bootstrap development environment in seconds.
{% endhint %}

### Result

Awesome !

![Output in Chrome](.gitbook/assets/screenshot-2020-03-21-at-16.51.06.png)

