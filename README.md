# NLX

**NLX** is a **Vite plugin** that parses `.nlx` files written in natural language into **Vue** components. It leverages **Tailwind CSS** for styling and **ShadCN** as the design system, enabling developers to write modular, framework-compliant code effortlessly.

---

## **Features**
- **Natural Language to Vue**: Write UI components in `.nlx` files and compile them into clean, reusable Vue components.
- **Tailwind CSS Integration**: Automatically applies utility-first styling from Tailwind.
- **ShadCN Support**: Seamlessly integrates with ShadCN design tokens and components.
- **Hot Module Replacement (HMR)**: Experience live updates during development.
- **Modular Design**: Outputs structured, maintainable, and reusable Vue components.

---

## **Getting Started**

### **Installation**

1. Install NLX and its dependencies:
   ```bash
   npm install nlx-plugin @vitejs/plugin-vue tailwindcss @shadcn/ui
   ```

2. Configure Tailwind CSS:
   ```bash
   npx tailwindcss init
   ```
   Update the `tailwind.config.js` file to include ShadCN plugins:
   ```javascript
   module.exports = {
     content: ['./src/**/*.{vue,nlx}'],
     plugins: [require('@shadcn/ui/tailwind')],
   };
   ```

---

### **Setup**

1. Add the NLX plugin to your `vite.config.js`:
   ```javascript
   import { defineConfig } from 'vite';
   import vue from '@vitejs/plugin-vue';
   import nlxPlugin from 'nlx-plugin';

   export default defineConfig({
     plugins: [vue(), nlxPlugin()],
   });
   ```

2. Create your first `.nlx` file in the `src/components` directory:
   ```bash
   mkdir -p src/components
   echo "# Button\n- A button with text: \"Click Me\"." > src/components/Button.nlx
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

---

## **Example Usage**

### Input `.nlx` File
```nlx
# Button
- A button with text: "Click Me".

## Styling
- Background color: blue.
- Padding: 1rem.

## Logic
- On click, increment "count".
```

### Output Vue Component
```vue
<template>
  <button @click="increment" class="bg-blue-500 p-4">
    Click Me
  </button>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
  },
};
</script>
```

---

## **Supported Features**
- Framework: **Vue**
- CSS: **Tailwind CSS**
- Design System: **ShadCN**

---

## **Roadmap**
- Add support for additional frameworks (e.g., React, Svelte).
- Expand support for other design systems.

---

## **Contributing**
We welcome contributions! To get started:
1. Fork this repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a clear description of the changes.

---

## **License**
This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
