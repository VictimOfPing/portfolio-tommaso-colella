# Architetto Tommaso Colella

![Next.js](https://img.shields.io/badge/Next.js-16.1-black?logo=nextdotjs)
![React](https://img.shields.io/badge/React-19.2-149eca?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178c6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38bdf8?logo=tailwindcss&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-6.19-2d3748?logo=prisma&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-Storage_&_Auth-3fcf8e?logo=supabase&logoColor=white)

Public website and CMS for an architecture studio in Marcianise, Caserta.
The project turns a service-heavy local practice into a searchable, SEO-ready portfolio with project pages, reviews, contact capture, and a protected admin workflow.

## Preview

![Studio visual preview](./public/background.jpeg)

The repository includes the main visual asset used by the website. The PWA manifest is already prepared for wide and narrow screenshots, so `public/screenshot-wide.png` and `public/screenshot-narrow.png` can be exported when final production captures are available.

## Tech Stack

| Area | Tools |
| --- | --- |
| Frontend | ![Next.js](https://img.shields.io/badge/Next.js-16.1-black?logo=nextdotjs) ![React](https://img.shields.io/badge/React-19.2-149eca?logo=react&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-5-3178c6?logo=typescript&logoColor=white) |
| Styling & Motion | ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38bdf8?logo=tailwindcss&logoColor=white) ![Framer Motion](https://img.shields.io/badge/Framer_Motion-12-0055ff?logo=framer&logoColor=white) ![GSAP](https://img.shields.io/badge/GSAP-3.14-88ce02) |
| 3D Portfolio | ![Three.js](https://img.shields.io/badge/Three.js-0.182-black?logo=threedotjs) ![React Three Fiber](https://img.shields.io/badge/React_Three_Fiber-9.5-black) |
| Data & Auth | ![Prisma](https://img.shields.io/badge/Prisma-6.19-2d3748?logo=prisma&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169e1?logo=postgresql&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-Auth_&_Storage-3fcf8e?logo=supabase&logoColor=white) |
| Forms & Validation | ![React Hook Form](https://img.shields.io/badge/React_Hook_Form-7.70-ec5990?logo=reacthookform&logoColor=white) ![Zod](https://img.shields.io/badge/Zod-4.3-3068b7) |

## Features

- SEO-focused public website with App Router metadata, canonical URLs, Open Graph data, robots, sitemap, JSON-LD, local business schema, FAQ schema, and geo-targeting for Marcianise/Caserta.
- Dynamic portfolio backed by Prisma models for projects, categories, featured items, project detail pages, image galleries, and a Three.js gallery experience.
- Protected admin area for managing projects, contact submissions, and client reviews, with Supabase Auth guarding `/admin` routes.
- Contact workflow with React Hook Form, Zod validation, persisted submissions, read/unread states, bulk actions, and dashboard counters.
- Supabase Storage integration for cover images and project galleries, including unique file naming and public URL handling.

## Architecture

The application is organized around the Next.js App Router:

- `src/app/(site)` contains the public routes: home, portfolio, services, reviews, about, and contacts.
- `src/app/admin` contains the authenticated dashboard and CRUD views for projects, reviews, and messages.
- `src/components` is split by ownership: `sections`, `pages`, `portfolio`, `admin`, `layout`, `animations`, and shared `ui`.
- `src/lib/actions` centralizes server actions for projects, contacts, reviews, auth, and storage.
- `src/lib/seo-config.ts` owns page metadata and structured data generation.
- `prisma/schema.prisma` defines the persisted CMS data: `Project`, `ContactSubmission`, and `Review`.

This keeps public marketing pages, admin workflows, database operations, and SEO configuration separated while still using a single Next.js codebase.

## Results & Impact

- Live domain configured for `https://architettotommasocolella.it`.
- Local architecture SEO is built into the application instead of being added as an afterthought: schema.org data, service keywords, canonical routes, and city/province targeting are generated per page.
- The studio can update portfolio projects, review visibility, featured work, and inbound messages without editing source code.
- The site is ready for PWA presentation through `manifest.json`, branded shortcuts, standalone display mode, and app metadata.

## Run Locally

```bash
npm install
npm run dev
```

For database-backed pages and the admin area, configure the environment variables used by Prisma and Supabase, then run:

```bash
npm run db:migrate
npm run db:seed
npm run build
```

## Links & Contacts

- Live site: [architettotommasocolella.it](https://architettotommasocolella.it)
- Portfolio: [architettotommasocolella.it/portfolio](https://architettotommasocolella.it/portfolio)
- Studio email: [arch.tommasocolella@gmail.com](mailto:arch.tommasocolella@gmail.com)
- LinkedIn: [Tommaso Colella](https://www.linkedin.com/in/tommaso-colella-380a4a90/)
- Source repository: [VictimOfPing/tommaso-colella](https://github.com/VictimOfPing/tommaso-colella)
