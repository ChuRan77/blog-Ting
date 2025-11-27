# Simple Vue: Create and log "hello word!"

This short guide shows two simple ways to create a minimal Vue app and output `hello word!` to the browser console.

## Prerequisites
- Node.js and npm installed (for the Vite method)
- Any modern browser (Chrome/Edge/Firefox)

---

## Method A — Quick single-file (CDN)
1. Create a new folder (e.g. `quick-vue`) and inside it create `index.html`.
2. Put this content in `index.html`:

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Vue CDN Example</title>
  </head>
  <body>
    <div id="app">{{ message }}</div>

    <!-- Vue 3 CDN -->
    <script src="https://unpkg.com/vue@3/dist/vue.global.prod.js"></script>
    <script>
      // Create app and log "hello word!"
      console.log('hello word!');
      const { createApp } = Vue;
      createApp({
        data() {
          return { message: 'Hello from Vue (CDN)' };
        }
      }).mount('#app');
    </script>
  </body>
</html>
```

3. Open `index.html` in your browser and check the browser console (F12) to see `hello word!`.

---

## Method B — Vite (recommended for real projects)
1. Open a Windows terminal (PowerShell or Command Prompt) and run:

```powershell
# create a new Vite + Vue project
npm create vite@latest my-vue-app -- --template vue

cd my-vue-app
npm install
```

2. Edit `src/main.js` (or `src/main.ts`) and add the `console.log` line. Example `src/main.js`:

```js
import { createApp } from 'vue'
import App from './App.vue'

// log "hello word!" to the console
console.log('hello word!')

createApp(App).mount('#app')
```

3. Start the dev server:

```powershell
npm run dev
```

4. Open the displayed localhost URL (typically `http://localhost:5173`) and open the browser console to see `hello word!`.

---

## Notes
- The console output appears in the browser's developer tools console (press F12).
- Use the CDN method for quick tests; use Vite for a real project with hot-reload and build tools.
