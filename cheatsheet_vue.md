## Comandos proyecto basico Vue3

1.  ```
    npm create vite@latest
    ```

2.  ```
    cd <name_project>
    npm i
    ```

## Comandos proyecto tailwind

1.  ```
    npm -D tailwindcss postcss autoprefixer
    ``` 

2.  ```
    npx tailwind init -p
    ``` 
3. En archivo taliwind.config.js:
    ```js
        /** @type {import('tailwindcss').Config} */
    module.exports = {
    content: [
        "./index.html",
        "./src/**/*.{vue,js,ts,jsx,tsx}"
    ],
    theme: {
        extend: {},
    },
    plugins: [],
    }
    ``` 
4. En archivo main.css
    ``` css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
