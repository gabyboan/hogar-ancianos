# B-Software

[![Astro](https://img.shields.io/badge/Astro-5-111111?logo=astro)](https://astro.build/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-38bdf8?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Cloudflare Pages](https://img.shields.io/badge/Cloudflare_Pages-publicado-f38020?logo=cloudflare&logoColor=white)](https://bsoftware.pages.dev/)
[![SEO](https://img.shields.io/badge/SEO-sitemap_robots_llms-22c55e)](https://bsoftware.pages.dev/sitemap.xml)

Sitio comercial de B-Software para presentar servicios, casos reales y una
forma concreta de contratar desarrollo web, sistemas internos, aplicaciones
moviles y automatizaciones.

## Enlaces

- Sitio publicado: https://bsoftware.pages.dev/
- GitHub: https://github.com/gabyboan
- Contacto: gabrielboan14@gmail.com

## Que muestra

- Propuesta comercial centrada en problemas operativos y resultados.
- Siete servicios con alcance, entregables orientativos y cliente ideal.
- Casos de estudio con problema, solucion, funciones, stack y estado real.
- Proceso en cuatro etapas y criterios para cotizar sin publicar precios rigidos.
- Formulario de calificacion que prepara un mensaje real de WhatsApp.
- Metadata para compartir en LinkedIn, GitHub, WhatsApp y plataformas freelance.
- `robots.txt`, `sitemap.xml`, `llms.txt` y datos estructurados Schema.org.
- Verificacion de Google Search Console por archivo HTML y meta tag.

## Proyectos destacados

| Proyecto | Tipo | Stack principal | Repositorio |
| --- | --- | --- | --- |
| Legajo Digital | Sistema interno | Next.js, React, Supabase | [gabyboan/legajo-digital](https://github.com/gabyboan/legajo-digital) |
| HESM Gestion RRHH | Escritorio operativo | Flutter, Riverpod, Supabase | [gabyboan/hesm-gestion-rrhh](https://github.com/gabyboan/hesm-gestion-rrhh) |
| Consulta Horas | Portal publico + API | Cloudflare Pages, Worker, Turnstile | [gabyboan/consulta-horas](https://github.com/gabyboan/consulta-horas) |
| Suplencias Propuesta | Aplicacion operativa | Flutter, Dart, Supabase, PostgreSQL | [gabyboan/app-suplencias-propuesta](https://github.com/gabyboan/app-suplencias-propuesta) |

`Suplencias Propuesta` se incluye como producto en desarrollo activo: ya cuenta
con autenticacion, roles, conexion con Supabase y documentacion publica sin
credenciales ni datos reales.

## Tecnologias

- Astro 5
- Tailwind CSS 4
- Cloudflare Pages
- Wrangler

## Desarrollo

```bash
npm install
npm run dev
```

Abrir `http://localhost:4321/`. El selector ES/EN guarda la preferencia en el
navegador; el contenido fuente del sitio se mantiene en español.

## Compilacion

```bash
npm run build
npm run check
```

La salida estatica se genera en `dist/`.

`npm run check` valida Astro, HTML embebido y TypeScript. No hay reglas de
estilo ESLint separadas porque el proyecto mantiene muy poco JavaScript cliente.

## Despliegue

```bash
npm run build
npx wrangler pages deploy dist --project-name bsoftware --commit-dirty=true
```

Configuracion recomendada en Cloudflare Pages:

- Framework: Astro
- Comando de compilacion: `npm run build`
- Directorio de salida: `dist`
- Node.js: 20 o superior

El deploy actual es completamente estatico y no requiere variables de entorno.

## Editar contenido comercial

- Servicios, problemas, proceso, cotizacion y FAQ: `src/pages/index.astro`.
- Casos detallados: `src/pages/proyectos/`.
- Textos en ingles: `src/i18n/translations.ts`.
- Navegacion y CTA principal: `src/components/NavBar.astro`.
- Metadata general y Open Graph: `src/layouts/Layout.astro`.
- URLs indexables: `public/sitemap.xml` y `public/robots.txt`.

Al agregar un caso, crear su pagina dentro de `src/pages/proyectos/`, enlazarla
desde la portada y sumar la URL al sitemap. Las imagenes publicas se guardan en
`public/` con dimensiones declaradas, texto alternativo y formatos optimizados.

## Contacto

El formulario de portada no simula un envio ni guarda datos: valida los campos,
arma el resumen de la consulta y abre WhatsApp para que la persona lo revise y
lo envie. El telefono y el email se editan en `src/pages/index.astro`,
`src/components/NavBar.astro`, `public/llms.txt` y los datos estructurados.

Si en el futuro se necesita guardar consultas sin salir del sitio, la opcion
recomendada es una Function de Cloudflare Pages protegida contra abuso y un
proveedor de email configurado con secretos; hasta entonces no se expone una
API ni se promete un envio inexistente.

## Higiene

No subir archivos de diseno fuente, zips exportados, credenciales ni tokens de
servicios externos. El repositorio ignora esos artefactos locales desde
`.gitignore`.
