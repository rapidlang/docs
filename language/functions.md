# Functions

## Example

This is the simplest function which is named **`example`**, takes no parameters and returns a number of type **`int`**.

{% tabs %}
{% tab title="example.rapid" %}
```javascript
function example(): int {
  return 12
}
```
{% endtab %}
{% endtabs %}

## Return statement

Return statement consists of **`return`** keyword and an expression.

Supported expression types:

* `number`

## Definition

{% tabs %}
{% tab title="Function Definition" %}
```javascript
function <name>(<param1>: <param_type>, ...): <return_type> {
  return <expression>
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
If function return type is specified as **`void`** then return statement is obsolete.
{% endhint %}

