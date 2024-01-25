¡Claro! Aquí están los cambios corrigiendo las tildes en tu texto:

```markdown
# React Router
## _Configurar React Router_

[![N|Solid](https://sahilthakur7blog.files.wordpress.com/2018/08/1_tkvltenqtkp1s-evb5hrvg2x.png)](https://reactrouter.com/en/main)

React Router es una librería para la gestión de rutas en un proyecto React.

## Introducción
##### Antes de nada, necesitamos instalar varias herramientas indispensables para trabajar con React Router
- ## Vite 
 [![N|Solid](https://seeklogo.com/images/V/vite-logo-BFD4283991-seeklogo.com.png)](https://vitejs.dev/)
- ## Node.js 
 [![N|Solid](https://cdn.worldvectorlogo.com/logos/nodejs.svg)](https://nodejs.org/en)
- ## Npm 
 [![N|Solid](https://desarrolloweb.com/storage/tag_images/actual/ys4swMGOM7UHXjCLdQLxiIWjasBJYNPs9xHRPy35.png)](https://www.npmjs.com/)

## Pasos

Abrimos nuestra terminal para crear una nueva React App con Vite:


```bash
npm create vite@latest nombre-de-tu-proyecto
cd <nombre de tu directorio del proyecto>
npm install react-router-dom localforage match-sorter sort-by
npm run dev
```

Una vez iniciada la web, nos la abrirá automáticamente en nuestro navegador. Esa será la web con la que trabajarás con React Router. Antes de configurar y enseñarte cómo funciona React y React Router, te dejo unos archivos para que copies y pegues en tu proyecto.

**👉 Copia Pega el archivo CSS en src/index.css**

```css
/* ... (resto del código) ... */
```

**👉 Copia pega el archivo javascript en src/contacts.js**

```javascript
/* ... (resto del código) ... */
```

**👉 Borra los archivos innecesarios en src/, solo necesitas tener estos:**
```cmd
src
├── contacts.js
├── index.css
└── main.jsx
```

## Añadir un Router

Lo primero es configurar nuestro primer router en main.jsx

```jsx
/* ... (resto del código) ... */
```

Este primer router será el router root, ya que todos los demás serán renderizados dentro de él.

### El router root

Vamos a añadir la layout global para nuestra app

- Crea en src/routes el archivo root.jsx

- Crea el componente root layout

```jsx
/* ... (resto del código) ... */
```

Ahora en src/main.jxs declara el elemento root

```jsx
/* ... (resto del código) ... */
```

- De momento la aplicación tendría una vista tal que así:

 [![N|Solid](https://reactrouter.com/_docs/tutorial/01.webp)
 
 ----
 Aún no acabado
 
 ----
