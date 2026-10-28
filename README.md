# AdoptaPet — Frontend

Panel web para administrar el proceso de adopción de mascotas. Permite a administradores y trabajadores gestionar animales, adoptantes, solicitudes y entregas mediante la API de AdoptaPet.

## Funcionalidades

- Inicio y cierre de sesión, con navegación y acceso según el rol.
- Registro y gestión de mascotas con fotografías.
- Consulta de adoptantes y gestión de su estado.
- Evaluación de solicitudes: aprobación, rechazo, cancelación y finalización.
- Programación de entregas, reprogramaciones y registro de inasistencias.
- Descarga de documentos y carga de actas firmadas.
- Administración de trabajadores y reportes PDF para administradores.

## Tecnologías

Angular 21 · TypeScript 5.9 · RxJS · Angular Router · HttpClient · CSS · Vitest

## Instalación y ejecución

Requiere **Node.js compatible con Angular 21**, **npm** y el [backend de AdoptaPet](https://github.com/thoonidev/AdoptaPet-Backend) configurado y en ejecución. El proyecto declara `npm@11.12.1` como gestor de paquetes.

```bash
git clone https://github.com/thoonidev/AdoptaPet-Frontend.git
cd AdoptaPet-Frontend
npm install
npm start
```

Abre `http://localhost:4200`. Inicia sesión con una cuenta del backend que tenga el rol `ROLE_ADMIN` o `ROLE_TRABAJADOR`; las rutas de este panel están restringidas a esos perfiles.

## Conexión con el backend

La aplicación utiliza `http://localhost:8080` como dirección del servidor. Las URL están definidas directamente en `src/app/services/`; no se requiere un archivo `.env`.

Si cambias la dirección del backend, actualiza también las URL de fotografías y documentos en:

- `src/app/components/lista-mascotas/lista-mascotas.ts`
- `src/app/components/solicitud-detalle/solicitud-detalle.ts`

El backend debe permitir el origen `http://localhost:4200` en su configuración CORS. La autenticación utiliza HTTP Basic mediante un interceptor y conserva la sesión en `localStorage`.

## Comandos

| Comando | Descripción |
| --- | --- |
| `npm start` | Inicia el servidor de desarrollo. |
| `npm run build` | Genera la compilación de producción en `dist/proyect-angular/`. |
| `npm run watch` | Compila en modo desarrollo y observa los cambios. |
| `npm test` | Ejecuta las pruebas con Vitest mediante Angular CLI. |
