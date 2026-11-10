# Options

Every option is a query parameter on the script URL. Only `key` is needed.

```yaml
extra_javascript:
  - https://onetagai.com/ask-docs.js?key=YOUR_ONETAG_KEY&label=Ask%20the%20docs&position=float
```

Values with spaces or special characters need URL encoding: a space is `%20`, `#` is `%23`.

| Option | What it does | Default |
| --- | --- | --- |
| `key` | Your OneTag AI key. | The demo key on `localhost`, none elsewhere |
| `label` | The text on the button and at the top of the box. | `Ask AI` |
| `placeholder` | The text in the empty question field. | `Ask a question about these docs` |
| `position` | Where the button goes: `auto`, `float`, `left` or `none`. | `auto` |
| `button` | A CSS selector for your own element that opens the box. | none |
| `color` | The accent colour, as hex without the `#`: `color=ff6600`. | The theme's accent colour |
| `theme` | `light` or `dark`. | Follows the page |
| `lang` | The language of the box's own text: `en`, `zh-CN`, `zh-TW`. | The page's language |
| `rules` | Replaces the instructions the AI gets. | See [How it works](how-it-works.md#the-instructions) |
| `index` | The address of the index, when it is not found on its own. | Found on its own |

## Where the button goes

- `position=auto`: in the header of Material for MkDocs, next to search. On other themes, floating in the bottom right corner.
- `position=float`: always floating in the bottom right corner.
- `position=left`: floating in the bottom left corner. Use it when something else already sits on the right.
- `position=none`: no button. Open the box from your own element or from code.

## Your own button

Point `button` at any element on your pages:

```yaml
extra_javascript:
  - https://onetagai.com/ask-docs.js?key=YOUR_ONETAG_KEY&position=none&button=.ask-ai
```

```html
<a class="ask-ai" href="#">Ask AI</a>
```

## From JavaScript

```js
onetagAskDocs.open();                      // open the box
onetagAskDocs.close();                     // close it
onetagAskDocs.ask("How do I deploy?");     // open it and ask
```

## Without mkdocs.yml

On a page you write by hand, the same options are `data-` attributes on the script tag:

```html
<script async src="https://onetagai.com/ask-docs.js"
        data-key="YOUR_ONETAG_KEY" data-label="Ask the docs"></script>
```
