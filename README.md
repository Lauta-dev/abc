# Game API

Este repositorio alberga el código fuente de un proyecto que implementa una API utilizando JavaScript en conjunto con el framework de backend NestJS y la tecnología de mapeo objeto-relacional TypeORM. La aplicación está diseñada para almacenar datos en una base de datos SQLite.

Esta base de datos cuenta con **35** registros con su:

- Título
- Descripción
- Género
- Cover/Caratula en **webp** y **jpg**
- Consola
- Año de lanzamiento
- Precio
- Generación que pertenece el juego

## Tecnologías Utilizadas

- [NestJS](https://github.com/nestjs/nest): Framework de backend que facilita el desarrollo de aplicaciones escalables y modularizadas en Node.js.
- [TypeORM](https://github.com/typeorm/typeorm): Mapeo objeto-relacional que simplifica la interacción con bases de datos relacionales utilizando TypeScript.
- [SQLite](https://www.sqlite.org/index.html): Motor de base de datos ligero que permite el almacenamiento eficiente de datos sin necesidad de un servidor dedicado.
- [Preact](https://github.com/preactjs/preact): Una alternativa a **React** con una API similar.
- [Hosting Vercel](https://vercel.com): Hosting dónde esta alojada la demo
- [Hosting Render](https://render.com): Hosting dónde esta alojada la API

## Iniciarlo en local

1. Clonar el repositorio

```bash
git clone https://github.com/Lauta-dev/render-nestjs.git
```

2. Instalar dependencias

- En este proyecto lo hice con [pnpm](https://github.com/pnpm/pnpm)

```bash
pnpm install

# o puedes usar npm
npm install
```

3. Levantar API

```bash
pnpm run start:dev
```

4. Levantar front-end

```bash
cd demo
pnpm run dev
```

## Rutas de la API

- **Ruta:** `/`
- **Método:** `GET` 
- **Descripción:** Obtener todos los juegos.

#### Parámetros de Consulta Soportados:
- `limit`, (opcional), **Por defecto el limite es 10 x página**
    - **Descripción:** Limita el número de juegos devueltos por página.
    - **Tipo**: Number

- `page`, (opcional), **Por defecto es la página 0**
    - **Descripción:** Especifica la página de resultados.
    - **Tipo**: Number

---

- **Ruta:** `/consoles`
- **Método:** `GET` 
- **Descripción:** Obtener todas las consolas de la base de datos.

---

- **Ruta:** `/generations`
- **Método:** `GET` 
- **Descripción:** Obtener todas las generaciones de consolas de ls base de datos.

---

- **Ruta:** `/id/:id`
- **Parámetro:** `id`
- **Método:** `GET` 
- **Descripción:** Obtener un objeto del juego que se le pase por `id`.

---

- **Ruta:** `/console/:console`
- **Método:** `GET` 
- **Descripción:** Obtener todos los juegos de una misma consola.
- **Posibles valores:** ps1, ps2, ps3, ps4, xbox, xbox_360, xbox_one

---

- **Ruta:** `/generation/:generation`
- **Método:** `GET` 
- **Descripción:** Obtener todos los juegos de una Generación.
- **Posibles valores:** ps1, ps2, ps3, ps4, xbox, xbox_360, xbox_one
