# nuxt

# bun install 
```
npm install -g bun
```

# setup nuxt
```
bunx nuxi init my-nuxt-app
```

# setup tailwind
## install tailwind
```
bun install -D tailwindcss postcss autoprefixer
bunx tailwindcss init
```
## Add Tailwind to your PostCSS configuration
```
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  devtools: { enabled: true },
  postcss: {
    plugins: {
      tailwindcss: {},
      autoprefixer: {},
    },
  },
})
```
## Configure template paths
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./components/**/*.{js,vue,ts}",
    "./layouts/**/*.vue",
    "./pages/**/*.vue",
    "./plugins/**/*.{js,ts}",
    "./app.vue",
    "./error.vue",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
## Add the Tailwind directives to your CSS
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
## Add the CSS file globally
```
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  devtools: { enabled: true },
  css: ['~/assets/css/main.css'],
  postcss: {
    plugins: {
      tailwindcss: {},
      autoprefixer: {},
    },
  },
})
```

# setup app.vue
```
<template>
  <div>
    <NuxtWelcome />
  </div>
</template>

↓

<template>
  <div>
    <NuxtPage />
  </div>
</template>
```