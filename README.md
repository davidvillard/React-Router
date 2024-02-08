# React Router
## _Configurar React Router_

[![N|Solid](https://sahilthakur7blog.files.wordpress.com/2018/08/1_tkvltenqtkp1s-evb5hrvg2x.png)](https://reactrouter.com/en/main)
<br><br><br><br>
- React Router es una librería para la gestion de rutas en un proyecto React
<br><br><br>

## Introducción
##### Antes de nada necesitamos instalar varias herramientas indispensables para trabajar con React Router
- ## Vite 
 [![N|Solid](https://seeklogo.com/images/V/vite-logo-BFD4283991-seeklogo.com.png)](https://vitejs.dev/)
 <br><br><br><br><br><br>
- ## Node.js 
 [![N|Solid](https://cdn.worldvectorlogo.com/logos/nodejs.svg)](https://nodejs.org/en)
 <br><br><br><br><br><br>
- ## Npm 
 [![N|Solid](https://desarrolloweb.com/storage/tag_images/actual/ys4swMGOM7UHXjCLdQLxiIWjasBJYNPs9xHRPy35.png)](https://www.npmjs.com/)
 <br><br><br><br><br><br>

## Pasos
<br>
Abrimos nuestra terminal para crear una nueva React App con Vite:
<br><br>

```bash
npm create vite@latest 
<escribe el nombre de tu proyecto>
<selecciona un framework>
<selecciona una variante>
cd <nombre de tu directorio del proyecto>
npm install react-router-dom localforage match-sorter sort-by
npm run dev
```
<br><br>
Una vez inciada la web, nos la abrira automaticamente en nuestro navegador. Esa sera la web con la que trabajaras con React Router.
Antes de configurar y enseñarte como funciona React y React Router te dejo unos archivos para que copies y pegues en tu proyecto
<br><br>

**👉 Copia Pega el archivo CSS en src/index.css**
<br><br>

```css
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
    "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
    monospace;
}

html,
body {
  height: 100%;
  margin: 0;
  line-height: 1.5;
  color: #121212;
}
textarea,
input,
button {
  font-size: 1rem;
  font-family: inherit;
  border: none;
  border-radius: 8px;
  padding: 0.5rem 0.75rem;
  box-shadow: 0 0px 1px hsla(0, 0%, 0%, 0.2), 0 1px 2px hsla(0, 0%, 0%, 0.2);
  background-color: white;
  line-height: 1.5;
  margin: 0;
}
button {
  color: #3992ff;
  font-weight: 500;
}

textarea:hover,
input:hover,
button:hover {
  box-shadow: 0 0px 1px hsla(0, 0%, 0%, 0.6), 0 1px 2px hsla(0, 0%, 0%, 0.2);
}

button:active {
  box-shadow: 0 0px 1px hsla(0, 0%, 0%, 0.4);
  transform: translateY(1px);
}

#contact h1 {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}
#contact h1 form {
  display: flex;
  align-items: center;
  margin-top: 0.25rem;
}
#contact h1 form button {
  box-shadow: none;
  font-size: 1.5rem;
  font-weight: 400;
  padding: 0;
}
#contact h1 form button[value="true"] {
  color: #a4a4a4;
}
#contact h1 form button[value="true"]:hover,
#contact h1 form button[value="false"] {
  color: #eeb004;
}

form[action$="destroy"] button {
  color: #f44250;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}

#root {
  display: flex;
  height: 100%;
  width: 100%;
}

#sidebar {
  width: 22rem;
  background-color: #f7f7f7;
  border-right: solid 1px #e3e3e3;
  display: flex;
  flex-direction: column;
}

#sidebar > * {
  padding-left: 2rem;
  padding-right: 2rem;
}

#sidebar h1 {
  font-size: 1rem;
  font-weight: 500;
  display: flex;
  align-items: center;
  margin: 0;
  padding: 1rem 2rem;
  border-top: 1px solid #e3e3e3;
  order: 1;
  line-height: 1;
}

#sidebar h1::before {
  content: url("data:image/svg+xml,%3Csvg width='25' height='18' viewBox='0 0 25 18' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M19.4127 6.4904C18.6984 6.26581 18.3295 6.34153 17.5802 6.25965C16.4219 6.13331 15.9604 5.68062 15.7646 4.51554C15.6551 3.86516 15.7844 2.9129 15.5048 2.32334C14.9699 1.19921 13.7183 0.695046 12.461 0.982805C11.3994 1.22611 10.516 2.28708 10.4671 3.37612C10.4112 4.61957 11.1197 5.68054 12.3363 6.04667C12.9143 6.22097 13.5284 6.3087 14.132 6.35315C15.2391 6.43386 15.3241 7.04923 15.6236 7.55574C15.8124 7.87508 15.9954 8.18975 15.9954 9.14193C15.9954 10.0941 15.8112 10.4088 15.6236 10.7281C15.3241 11.2334 14.9547 11.5645 13.8477 11.6464C13.244 11.6908 12.6288 11.7786 12.0519 11.9528C10.8353 12.3201 10.1268 13.3799 10.1828 14.6234C10.2317 15.7124 11.115 16.7734 12.1766 17.0167C13.434 17.3056 14.6855 16.8003 15.2204 15.6762C15.5013 15.0866 15.6551 14.4187 15.7646 13.7683C15.9616 12.6032 16.423 12.1505 17.5802 12.0242C18.3295 11.9423 19.1049 12.0242 19.8071 11.6253C20.5491 11.0832 21.212 10.2696 21.212 9.14192C21.212 8.01428 20.4976 6.83197 19.4127 6.4904Z' fill='%23F44250'/%3E%3Cpath d='M7.59953 11.7459C6.12615 11.7459 4.92432 10.5547 4.92432 9.09441C4.92432 7.63407 6.12615 6.44287 7.59953 6.44287C9.0729 6.44287 10.2747 7.63407 10.2747 9.09441C10.2747 10.5536 9.07172 11.7459 7.59953 11.7459Z' fill='black'/%3E%3Cpath d='M2.64217 17.0965C1.18419 17.093 -0.0034949 15.8971 7.72743e-06 14.4356C0.00352588 12.9765 1.1994 11.7888 2.66089 11.7935C4.12004 11.797 5.30772 12.9929 5.30306 14.4544C5.29953 15.9123 4.10366 17.1 2.64217 17.0965Z' fill='black'/%3E%3Cpath d='M22.3677 17.0965C20.9051 17.1046 19.7046 15.9217 19.6963 14.4649C19.6882 13.0023 20.8712 11.8017 22.3279 11.7935C23.7906 11.7854 24.9911 12.9683 24.9993 14.4251C25.0075 15.8866 23.8245 17.0883 22.3677 17.0965Z' fill='black'/%3E%3C/svg%3E%0A");
  margin-right: 0.5rem;
  position: relative;
  top: 1px;
}

#sidebar > div {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #e3e3e3;
}

#sidebar > div form {
  position: relative;
}

#sidebar > div form input[type="search"] {
  width: 100%;
  padding-left: 2rem;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' class='h-6 w-6' fill='none' viewBox='0 0 24 24' stroke='%23999' stroke-width='2'%3E%3Cpath stroke-linecap='round' stroke-linejoin='round' d='M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z' /%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: 0.625rem 0.75rem;
  background-size: 1rem;
  position: relative;
}

#sidebar > div form input[type="search"].loading {
  background-image: none;
}

#search-spinner {
  width: 1rem;
  height: 1rem;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24'%3E%3Cpath stroke='%23000' strokeLinecap='round' strokeLinejoin='round' strokeWidth='2' d='M20 4v5h-.582m0 0a8.001 8.001 0 00-15.356 2m15.356-2H15M4 20v-5h.581m0 0a8.003 8.003 0 0015.357-2M4.581 15H9' /%3E%3C/svg%3E");
  animation: spin 1s infinite linear;
  position: absolute;
  left: 0.625rem;
  top: 0.75rem;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

#sidebar nav {
  flex: 1;
  overflow: auto;
  padding-top: 1rem;
}

#sidebar nav a span {
  float: right;
  color: #eeb004;
}
#sidebar nav a.active span {
  color: inherit;
}

i {
  color: #818181;
}
#sidebar nav .active i {
  color: inherit;
}

#sidebar ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

#sidebar li {
  margin: 0.25rem 0;
}

#sidebar nav a {
  display: flex;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;

  white-space: pre;
  padding: 0.5rem;
  border-radius: 8px;
  color: inherit;
  text-decoration: none;
  gap: 1rem;
}

#sidebar nav a:hover {
  background: #e3e3e3;
}

#sidebar nav a.active {
  background: hsl(224, 98%, 58%);
  color: white;
}

#sidebar nav a.pending {
  color: hsl(224, 98%, 58%);
}

#detail {
  flex: 1;
  padding: 2rem 4rem;
  width: 100%;
}

#detail.loading {
  opacity: 0.25;
  transition: opacity 200ms;
  transition-delay: 200ms;
}

#contact {
  max-width: 40rem;
  display: flex;
}

#contact h1 {
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
  line-height: 1.2;
}

#contact h1 + p {
  margin: 0;
}

#contact h1 + p + p {
  white-space: break-spaces;
}

#contact h1:focus {
  outline: none;
  color: hsl(224, 98%, 58%);
}

#contact a[href*="twitter"] {
  display: flex;
  font-size: 1.5rem;
  color: #3992ff;
  text-decoration: none;
}
#contact a[href*="twitter"]:hover {
  text-decoration: underline;
}

#contact img {
  width: 12rem;
  height: 12rem;
  background: #c8c8c8;
  margin-right: 2rem;
  border-radius: 1.5rem;
  object-fit: cover;
}

#contact h1 ~ div {
  display: flex;
  gap: 0.5rem;
  margin: 1rem 0;
}

#contact-form {
  display: flex;
  max-width: 40rem;
  flex-direction: column;
  gap: 1rem;
}
#contact-form > p:first-child {
  margin: 0;
  padding: 0;
}
#contact-form > p:first-child > :nth-child(2) {
  margin-right: 1rem;
}
#contact-form > p:first-child,
#contact-form label {
  display: flex;
}
#contact-form p:first-child span,
#contact-form label span {
  width: 8rem;
}
#contact-form p:first-child input,
#contact-form label input,
#contact-form label textarea {
  flex-grow: 2;
}

#contact-form-avatar {
  margin-right: 2rem;
}

#contact-form-avatar img {
  width: 12rem;
  height: 12rem;
  background: hsla(0, 0%, 0%, 0.2);
  border-radius: 1rem;
}

#contact-form-avatar input {
  box-sizing: border-box;
  width: 100%;
}

#contact-form p:last-child {
  display: flex;
  gap: 0.5rem;
  margin: 0 0 0 8rem;
}

#contact-form p:last-child button[type="button"] {
  color: inherit;
}

#zero-state {
  margin: 2rem auto;
  text-align: center;
  color: #818181;
}

#zero-state a {
  color: inherit;
}

#zero-state a:hover {
  color: #121212;
}

#zero-state:before {
  display: block;
  margin-bottom: 0.5rem;
  content: url("data:image/svg+xml,%3Csvg width='50' height='33' viewBox='0 0 50 33' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M38.8262 11.1744C37.3975 10.7252 36.6597 10.8766 35.1611 10.7128C32.8444 10.4602 31.9215 9.55475 31.5299 7.22456C31.3108 5.92377 31.5695 4.01923 31.0102 2.8401C29.9404 0.591789 27.4373 -0.416556 24.9225 0.158973C22.7992 0.645599 21.0326 2.76757 20.9347 4.94569C20.8228 7.43263 22.2399 9.5546 24.6731 10.2869C25.8291 10.6355 27.0574 10.8109 28.2646 10.8998C30.4788 11.0613 30.6489 12.292 31.2479 13.3051C31.6255 13.9438 31.9914 14.5731 31.9914 16.4775C31.9914 18.3819 31.6231 19.0112 31.2479 19.6499C30.6489 20.6606 29.9101 21.3227 27.696 21.4865C26.4887 21.5754 25.2581 21.7508 24.1044 22.0994C21.6712 22.834 20.2542 24.9537 20.366 27.4406C20.4639 29.6187 22.2306 31.7407 24.3538 32.2273C26.8686 32.8052 29.3717 31.7945 30.4415 29.5462C31.0032 28.3671 31.3108 27.0312 31.5299 25.7304C31.9238 23.4002 32.8467 22.4948 35.1611 22.2421C36.6597 22.0784 38.2107 22.2421 39.615 21.4443C41.099 20.36 42.4248 18.7328 42.4248 16.4775C42.4248 14.2222 40.9961 11.8575 38.8262 11.1744Z' fill='%23E3E3E3'/%3E%3Cpath d='M15.1991 21.6854C12.2523 21.6854 9.84863 19.303 9.84863 16.3823C9.84863 13.4615 12.2523 11.0791 15.1991 11.0791C18.1459 11.0791 20.5497 13.4615 20.5497 16.3823C20.5497 19.3006 18.1436 21.6854 15.1991 21.6854Z' fill='%23E3E3E3'/%3E%3Cpath d='M5.28442 32.3871C2.36841 32.38 -0.00698992 29.9882 1.54551e-05 27.0652C0.00705187 24.1469 2.39884 21.7715 5.32187 21.7808C8.24022 21.7878 10.6156 24.1796 10.6063 27.1027C10.5992 30.0187 8.20746 32.3941 5.28442 32.3871Z' fill='%23E3E3E3'/%3E%3Cpath d='M44.736 32.387C41.8107 32.4033 39.4096 30.0373 39.3932 27.1237C39.3769 24.1984 41.7428 21.7973 44.6564 21.7808C47.5817 21.7645 49.9828 24.1305 49.9993 27.0441C50.0156 29.9671 47.6496 32.3705 44.736 32.387Z' fill='%23E3E3E3'/%3E%3C/svg%3E%0A");
}

#error-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}
```
<br><br>

**👉 Copia pega el archivo javascript en src/contacts.js**
<br><br>

```javascript
import localforage from "localforage";
import { matchSorter } from "match-sorter";
import sortBy from "sort-by";

export async function getContacts(query) {
  await fakeNetwork(`getContacts:${query}`);
  let contacts = await localforage.getItem("contacts");
  if (!contacts) contacts = [];
  if (query) {
    contacts = matchSorter(contacts, query, { keys: ["first", "last"] });
  }
  return contacts.sort(sortBy("last", "createdAt"));
}

export async function createContact() {
  await fakeNetwork();
  let id = Math.random().toString(36).substring(2, 9);
  let contact = { id, createdAt: Date.now() };
  let contacts = await getContacts();
  contacts.unshift(contact);
  await set(contacts);
  return contact;
}

export async function getContact(id) {
  await fakeNetwork(`contact:${id}`);
  let contacts = await localforage.getItem("contacts");
  let contact = contacts.find(contact => contact.id === id);
  return contact ?? null;
}

export async function updateContact(id, updates) {
  await fakeNetwork();
  let contacts = await localforage.getItem("contacts");
  let contact = contacts.find(contact => contact.id === id);
  if (!contact) throw new Error("No contact found for", id);
  Object.assign(contact, updates);
  await set(contacts);
  return contact;
}

export async function deleteContact(id) {
  let contacts = await localforage.getItem("contacts");
  let index = contacts.findIndex(contact => contact.id === id);
  if (index > -1) {
    contacts.splice(index, 1);
    await set(contacts);
    return true;
  }
  return false;
}

function set(contacts) {
  return localforage.setItem("contacts", contacts);
}

// fake a cache so we don't slow down stuff we've already seen
let fakeCache = {};

async function fakeNetwork(key) {
  if (!key) {
    fakeCache = {};
  }

  if (fakeCache[key]) {
    return;
  }

  fakeCache[key] = true;
  return new Promise(res => {
    setTimeout(res, Math.random() * 800);
  });
}
```
<br><br>

**👉 Borra los archivos ineccesarios en src/ solo necesitas tener estos:**
<br><br>

```cmd
src
├── contacts.js
├── index.css
└── main.jsx
```
<br><br>

## Añadir un Router
<br>

Lo primero es configurar nuestro primer router en main.jsx
<br><br>

```jsx
import * as React from "react";
import * as ReactDOM from "react-dom/client";
import {
  createBrowserRouter,
  RouterProvider,
} from "react-router-dom";
import "./index.css";

const router = createBrowserRouter([
  {
    path: "/",
    element: <div>Hello world!</div>,
  },
]);

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
<br>

Este primer router sera el router root, ya que todos los demas seran renderizados dentro de el.
<br><br>

## El router root
<br>

Vamos a añadir la layout global para nuestra app

- Crea en src/routes el archivo root.jsx

- Crea el componente root layout

<br><br>

```jsx
export default function Root() {
  return (
    <>
      <div id="sidebar">
        <h1>React Router Contacts</h1>
        <div>
          <form id="search-form" role="search">
            <input
              id="q"
              aria-label="Search contacts"
              placeholder="Search"
              type="search"
              name="q"
            />
            <div
              id="search-spinner"
              aria-hidden
              hidden={true}
            />
            <div
              className="sr-only"
              aria-live="polite"
            ></div>
          </form>
          <form method="post">
            <button type="submit">New</button>
          </form>
        </div>
        <nav>
          <ul>
            <li>
              <a href={`/contacts/1`}>Your Name</a>
            </li>
            <li>
              <a href={`/contacts/2`}>Your Friend</a>
            </li>
          </ul>
        </nav>
      </div>
      <div id="detail"></div>
    </>
  );
}
```
<br><br>


Ahora en src/main.jxs declara el elemento root
<br><br>

```jsx
/* existing imports */
import Root from "./routes/root";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
  },
]);

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
<br><br>

- De momento la aplicacion tendria una vista tal que asi:

 ![N|Solid](https://reactrouter.com/_docs/tutorial/01.webp)

<br><br><br><br>

## Configurar el Not Found Errors
<br>

Ahora vamos a configurar los errores de nuestra pagina. Estamos hablando de los tipicos errores de 404.


Si haceis click en alguno de los "usuarios" de nuestro sidebar veremos el not found error.

- 👉 Por ello crearemos el componente error-page.jsx en src/error.page.jsx
<br><br>

```jsx
import { useRouteError } from "react-router-dom";

export default function ErrorPage() {
  const error = useRouteError();
  console.error(error);

  return (
    <div id="error-page">
      <h1>Oops!</h1>
      <p>Sorry, an unexpected error has occurred.</p>
      <p>
        <i>{error.statusText || error.message}</i>
      </p>
    </div>
  );
}
```
<br><br>

Ahora pondremos el ErrorPage como 'errorElement' en el root router, por lo tanto entramos en src/main.jsx
<br><br>

```jsx
/* previous imports */
import ErrorPage from "./error-page";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
  },
]);

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
<br><br>

- Ahora veriamos la pagina tal que asi al clickar en un usuario:

 ![N|Solid](https://reactrouter.com/_docs/tutorial/03.webp)
 
<br><br><br><br>

## Configurar el route de contactos para que no aparezca el 404 error
<br>

Ahora vamos a hacer los contactos:

👉 Crea el modulo de ruta de contacto llamado contact.jsx en src/routes

Ahora añade el componenete contactos en el archivo creado:
<br><br>

```jsx
import { Form } from "react-router-dom";

export default function Contact() {
  const contact = {
    first: "Your",
    last: "Name",
    avatar: "https://placekitten.com/g/200/200",
    twitter: "your_handle",
    notes: "Some notes",
    favorite: true,
  };

  return (
    <div id="contact">
      <div>
        <img
          key={contact.avatar}
          src={contact.avatar || null}
        />
      </div>

      <div>
        <h1>
          {contact.first || contact.last ? (
            <>
              {contact.first} {contact.last}
            </>
          ) : (
            <i>No Name</i>
          )}{" "}
          <Favorite contact={contact} />
        </h1>

        {contact.twitter && (
          <p>
            <a
              target="_blank"
              href={`https://twitter.com/${contact.twitter}`}
            >
              {contact.twitter}
            </a>
          </p>
        )}

        {contact.notes && <p>{contact.notes}</p>}

        <div>
          <Form action="edit">
            <button type="submit">Edit</button>
          </Form>
          <Form
            method="post"
            action="destroy"
            onSubmit={(event) => {
              if (
                !confirm(
                  "Please confirm you want to delete this record."
                )
              ) {
                event.preventDefault();
              }
            }}
          >
            <button type="submit">Delete</button>
          </Form>
        </div>
      </div>
    </div>
  );
}

function Favorite({ contact }) {
  // yes, this is a `let` for later
  let favorite = contact.favorite;
  return (
    <Form method="post">
      <button
        name="favorite"
        value={favorite ? "false" : "true"}
        aria-label={
          favorite
            ? "Remove from favorites"
            : "Add to favorites"
        }
      >
        {favorite ? "★" : "☆"}
      </button>
    </Form>
  );
}
```
<br><br>

Una vez añadido el componenete, lo importamos y creamos una nueva ruta en main.jsx:
<br><br>

```jsx
/* existing imports */
import Contact from "./routes/contact";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
  },
  {
    path: "contacts/:contactId",
    element: <Contact />,
  },
]);

/* existing code */
```
<br><br>

- Ahora veriamos la pagina de esta manera:

 ![N|Solid](https://reactrouter.com/_docs/tutorial/04.webp)
 
 <br><br><br><br>

 ## Añadir el componente contactos dentro del diseño Root:
 <br>

 Para ellos hacemos que la ruta contacto sea hija de la ruta root.
 
 👉 En main.jsx:
 <br><br>

 ```jsx

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
      },
    ],
  },
]);
```
<br><br>

Ahora veriamos en la ruta root una pagina en blanco a la derecha. Por ello necesitamos decirle a la ruta root donde queremos que se represente sus rutas secundarias, y lo haremos con 'Outlet'

Busca el 'div id='detail'' y pon un outlet dentro, en root.jsx
<br><br>

```jsx
import { Outlet } from "react-router-dom";

export default function Root() {
  return (
    <>
      {/* all the other elements */}
      <div id="detail">
        <Outlet />
      </div>
    </>
  );
}
```
<br><br>

## Enrutamiento de lado cliente
<br>

Cuando hacemos click en los enlaces de la barra lateral el navegador realiza una solicitud completa del documento en lugar de usar React Router. El enrutamiento de lado cliente permite que se actualice sin solicitar otro documento del servidor.

Esto lo haremos con 'Link'


👉 Cambia en la barra lateral 'a href' a 'Link to' en root.jsx

<br><br>

```jsx
import { Outlet, Link } from "react-router-dom";

export default function Root() {
  return (
    <>
      <div id="sidebar">
        {/* other elements */}

        <nav>
          <ul>
            <li>
              <Link to={`contacts/1`}>Your Name</Link>
            </li>
            <li>
              <Link to={`contacts/2`}>Your Friend</Link>
            </li>
          </ul>
        </nav>

        {/* other elements */}
      </div>
    </>
  );
}
```
<br><br>

## Cargando datos
<br>

 A menudo necesitas cargar datos dependiendo de la URL a la que el usuario acceda. Por ello utilizaremos dos herramientas para facilitar este proceso: loader y useLoaderData.
 
 Estas herramientas ayudan a desacoplar la carga de datos de tus componentes de ruta, facilitando la gestión de datos dinámicos en tu aplicación.
 
 Exporta el loader en root.jsx
 <br><br>

 ```jsx
 import { Outlet, Link } from "react-router-dom";
import { getContacts } from "../contacts";

export async function loader() {
  const contacts = await getContacts();
  return { contacts };
}
 ```
 <br><br>

 Configuralo en la ruta en main.jsx
 <br><br>

 ```jsx
 /* other imports */
import Root, { loader as rootLoader } from "./routes/root";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    loader: rootLoader,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
      },
    ],
  },
]);
 ```
 <br><br>

 Accede y renderiza los datos en root.jsx
 <br><br>

 ```jsx
 import {
  Outlet,
  Link,
  useLoaderData,
} from "react-router-dom";
import { getContacts } from "../contacts";

/* other code */

export default function Root() {
  const { contacts } = useLoaderData();
  return (
    <>
      <div id="sidebar">
        <h1>React Router Contacts</h1>
        {/* other code */}

        <nav>
          {contacts.length ? (
            <ul>
              {contacts.map((contact) => (
                <li key={contact.id}>
                  <Link to={`contacts/${contact.id}`}>
                    {contact.first || contact.last ? (
                      <>
                        {contact.first} {contact.last}
                      </>
                    ) : (
                      <i>No Name</i>
                    )}{" "}
                    {contact.favorite && <span>★</span>}
                  </Link>
                </li>
              ))}
            </ul>
          ) : (
            <p>
              <i>No contacts</i>
            </p>
          )}
        </nav>

        {/* other code */}
      </div>
    </>
  );
}
 ```
 <br><br>

 Ahora React Router tendra automaticamente los datos sincronizadps con la interfaz de usuario. Por ahora obtendriamos esto:
 
  ![N|Solid](https://reactrouter.com/_docs/tutorial/06.webp)
  
  <br><br><br><br>

## Escritura de Datos y fomrularios HTML
<br>

React Router simplifica la navegación al emular el comportamiento de los formularios HTML, permitiendo el renderizado del lado del cliente con la simplicidad de los modelos web tradicionales. Los formularios HTML provocan la navegación del navegador, similar a los enlaces, pero con la capacidad adicional de modificar los métodos y cuerpos de las solicitudes. React Router imita este comportamiento, manejando los datos localmente en lugar de enviarlos al servidor. Probar esto con un botón "Nuevo" puede causar problemas si el servidor no está configurado para solicitudes POST.

  ![N|Solid](https://reactrouter.com/_docs/tutorial/07.webp)
<br><br><br><br>

En lugar de enviar un POST al servidor Vite para crear un contacto, usaremos el enrutamiento del lado cliente.

<br><br>

## Crear Contactos
<br>

Crearemos contactos exportando una accion en root y conectandola a la configuracion de la ruta y cambiando 'form' por 'Form' en root.jsx
<br><br>

```jsx
import {
  Outlet,
  Link,
  useLoaderData,
  Form,
} from "react-router-dom";
import { getContacts, createContact } from "../contacts";

export async function action() {
  const contact = await createContact();
  return { contact };
}

/* other code */

export default function Root() {
  const { contacts } = useLoaderData();
  return (
    <>
      <div id="sidebar">
        <h1>React Router Contacts</h1>
        <div>
          {/* other code */}
          <Form method="post">
            <button type="submit">New</button>
          </Form>
        </div>

        {/* other code */}
      </div>
    </>
  );
}
```
<br><br>

Importa y establece la accion en la ruta en main.jsx
<br><br>

```jsx
/* other imports */

import Root, {
  loader as rootLoader,
  action as rootAction,
} from "./routes/root";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    loader: rootLoader,
    action: rootAction,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
      },
    ],
  },
]);
```
<br><br>

- Ahora si hacemos click en añadir nuevo contacto se abrira un nuevo pop dentro de la lista

![N|Solid](https://reactrouter.com/_docs/tutorial/08.webp)

<br><br><br><br>


## Parametros de URL

<br>

Ahor vamos a hacer que el ID del contacto no se uno aleatorio, si no que sea una ID real
<br><br>

👉 Añadimos loader a la pagina de contacto y el acceso de datos con useLoaderData en contact.jsx:

```jsx
import { Form, useLoaderData } from "react-router-dom";
import { getContact } from "../contacts";

export async function loader({ params }) {
  const contact = await getContact(params.contactId);
  return { contact };
}

export default function Contact() {
  const { contact } = useLoaderData();
  // existing code
}
```
<br><br>

Configura el loader en main.jsx
<br><br>

```jsx
/* existing code */
import Contact, {
  loader as contactLoader,
} from "./routes/contact";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    loader: rootLoader,
    action: rootAction,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
        loader: contactLoader,
      },
    ],
  },
]);
```

Una vez terminado, la pagina nos quedaria tal que asi:
<br><br>

![N|Solid](https://reactrouter.com/_docs/tutorial/10.webp)
<br><br><br><br>


## Actualización de Datos
<br>
Al igual que al crear datos, puedes actualizar datos con `<Form>`. Vamos a crear una nueva ruta en `contacts/:contactId/edit`. Nuevamente, comenzaremos con el componente y luego lo conectaremos a la configuración de la ruta.
<br><br>
👉 Crear el componente de edición
<br><br>

```cmd
touch src/routes/edit.jsx
```

<br><br>
👉 Agregar la interfaz de la página de edición

Nada que no hayamos visto antes, siéntete libre de copiar y pegar:
<br><br>

```jsx
import { Form, useLoaderData } from "react-router-dom";

export default function EditContact() {
  const { contact } = useLoaderData();

  return (
    <Form method="post" id="contact-form">
      <p>
        <span>Nombre</span>
        <input
          placeholder="Primero"
          aria-label="Nombre"
          type="text"
          name="first"
          defaultValue={contact.first}
        />
        <input
          placeholder="Apellido"
          aria-label="Apellido"
          type="text"
          name="last"
          defaultValue={contact.last}
        />
      </p>
      <label>
        <span>Twitter</span>
        <input
          type="text"
          name="twitter"
          placeholder="@jack"
          defaultValue={contact.twitter}
        />
      </label>
      <label>
        <span>URL del Avatar</span>
        <input
          placeholder="https://ejemplo.com/avatar.jpg"
          aria-label="URL del Avatar"
          type="text"
          name="avatar"
          defaultValue={contact.avatar}
        />
      </label>
      <label>
        <span>Notas</span>
        <textarea
          name="notes"
          defaultValue={contact.notes}
          rows={6}
        />
      </label>
      <p>
        <button type="submit">Guardar</button>
        <button type="button">Cancelar</button>
      </p>
    </Form>
  );
}
```
<br><br>
👉 Agregar la nueva ruta de edición
<br><br>

```jsx
/* código existente */
import EditContact from "./routes/edit";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    loader: rootLoader,
    action: rootAction,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
        loader: contactLoader,
      },
      {
        path: "contacts/:contactId/edit",
        element: <EditContact />,
        loader: contactLoader,
      },
    ],
  },
]);

/* código existente */
```
<br><br>
Queremos que se renderice en el outlet de la ruta principal, así que lo hicimos un hermano de la ruta secundaria existente.
<br><br>
(Apunta que reutilizamos `contactLoader` para esta ruta. Esto se hace solo porque estamos siendo vagos en el tutorial. No hay razón para intentar compartir loaders entre rutas, por lo general, tienen los suyos propios).
<br><br>
¡Bien, al hacer clic en el botón "Editar" nos da esta nueva interfaz de usuario!
<br><br>
![N|Solid](https://reactrouter.com/_docs/tutorial/11.webp)
<br><br><br><br>
## Actualización de Contactos con FormData
<br>
La ruta de edición que acabamos de crear ya renderiza un formulario. Todo lo que necesitamos hacer para actualizar el registro es conectar una acción a la ruta. El formulario se enviará a la acción y los datos se volverán a validar automáticamente.
<br><br>
👉 Agregar una acción al módulo de edición

```jsx
import {
  Form,
  useLoaderData,
  redirect,
} from "react-router-dom";
import { updateContact } from "../contacts";

export async function action({ request, params }) {
  const formData = await request.formData();
  const updates = Object.fromEntries(formData);
  await updateContact(params.contactId, updates);
  return redirect(`/contacts/${params.contactId}`);
}
/* código existente */
```
<br><br>
👉 Conectar la acción a la ruta

```jsx
/* código existente */
import EditContact, {
  action as editAction,
} from "./routes/edit";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    errorElement: <ErrorPage />,
    loader: rootLoader,
    action: rootAction,
    children: [
      {
        path: "contacts/:contactId",
        element: <Contact />,
        loader: contactLoader,
      },
      {
        path: "contacts/:contactId/edit",
        element: <EditContact />,
        loader: contactLoader,
        action: editAction,
      },
    ],
  },
]);

/* código existente */
```
<br><br>
Completa el formulario, haz clic en guardar, ¡y deberías ver algo como esto!
<br><br>
![N|Solid](https://reactrouter.com/_docs/tutorial/12.webp)