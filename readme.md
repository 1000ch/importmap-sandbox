# importmap-sandbox

> [Import maps](https://wicg.github.io/import-maps/) allow web pages to control the behavior of JavaScript imports.

Import maps is implemented on [Chromium 74~ experimentaly](https://caniuse.com/import-maps), so you have to enable **Experimental Web Platform features** flag on `chrome://flags/#enable-experimental-web-platform-features` if you want to try it.

```html
<script type="importmap">
  {
    "imports": {
      "x-marked": "https://unpkg.com/x-marked",
      "social-button": "https://unpkg.com/social-button"
    }
  }
</script>
<script type="module">
  import XMarked from 'x-marked';
  import { TwitterButton, FacebookButton } from 'social-button';

  customElements.define('x-marked', XMarked);
  customElements.define('twitter-button', TwitterButton);
  customElements.define('facebook-button', FacebookButton);
</script>
<twitter-button type="follow" width="220" height="30" user="1000ch"></twitter-button>
```
