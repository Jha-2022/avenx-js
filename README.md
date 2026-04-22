# Hoe-JS 🚀

A lightweight, reactive JavaScript framework Proof-of-Concept featuring **Zero-Classname Styling** and a custom template compiler.

## Features

- **Reactivity**: Uses JavaScript Proxies to automatically re-render components when state changes.
- **TTH Templates**: Components are defined in `.tth` files with `<state />`, `<action />`, and standard HTML.
- **DES Styling**: Styles are outsourced to `.des` files. Use the `<@css />` marker in your template to automatically assign a unique hash-class to the preceding HTML element.
- **Scoped CSS**: Supports nesting with `&` (like Sass) which is automatically scoped to the specific element.
- **Zero Configuration**: A simple `compiler.js` bundles everything into a single `dist/` folder.

## File Structure

- `src/components/Name.tth`: The structure and logic of your component.
- `src/components/Name.des`: The styles for your component, using `@css { ... }` blocks.
- `src/main.hoe`: The entry point of your application.
- `src/runtime.js`: The core framework logic.

## How to Build

1. **Prerequisites**: Ensure you have [Node.js](https://nodejs.org/) installed.
2. **Compile**: Run the compiler script from the root directory:
   ```bash
   node compiler.js
   ```
3. **Output**: The compiler will generate:
   - `dist/bundle.js`: Contains the runtime, compiled components, and app logic.
   - `dist/bundle.css`: Contains all scoped styles extracted from your `.des` files.

## Usage Example

### 1. Define Styles (`Counter.des`)
```css
@css {
    color: #333;
    &:hover { color: #ff3e00; }
}
```

### 2. Define Template (`Counter.tth`)
```html
<state count="0" />
<h1 @click="count++">
    <@css />
    Count is {{ count }}
</h1>
```

### 3. Run and View
Open your `index.html` (which should link to `dist/bundle.js` and `dist/bundle.css`) in a browser.

