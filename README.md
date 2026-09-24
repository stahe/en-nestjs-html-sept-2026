# Create a web application with the NestJS framework

📖 **Read the tutorial: [https://stahe.github.io/en-nestjs-html-sept-2026/](https://stahe.github.io/en-nestjs-html-sept-2026/)**

This course teaches you how to build an **MVC** web application using the [NestJS](https://nestjs.com) framework: an application whose HTML pages are generated **by the server** using the Handlebars view engine, without a client-side JavaScript framework.

It follows the progression of the course [Introduction to ASP.NET MVC by Example](https://stahe.github.io/en-aspnetmvc-nov-2013/) (2013), adapted to the Node.js/TypeScript ecosystem:

| ASP.NET MVC (2013) | NestJS (2026) |
|---|---|
| C#, controllers, actions | TypeScript, `@Controller`, `@Get`, `@Post` |
| Razor views, `_Layout.cshtml` | Handlebars views, `layout.hbs` |
| `[Required]`, `ModelState.IsValid` | class-validator, form validation |
| session, `TempData` | cookies, JWT token, flash messages |
| filters, `[Authorize]` | middleware, guards, interceptors, `@Roles` |
| Entity Framework | TypeORM + MySQL |

## The Approach: Many Short Examples, Then a Case Study

The course is based on **28 short projects**, each focused on a single concept. You can run and modify them. All examples share a single `npm install`.

| Chapter | Content | Examples |
|---|---|---|
| Controllers, Actions, Routing | routes, responses, redirects, modules, dependency injection | 01–06 |
| The Action Model | parameters, conversion, validation, POST forms, pipes | 07–12 |
| The View and Its Template | Handlebars, templates, partials, helpers, forms, validation, Post/Redirect/Get, confirmation dialog | 13–21 |
| Internationalization | An application in French and English | 22 |
| Data Scopes | Application, request, client | 23 |
| The Request Lifecycle | middleware, guard, interceptor, pipe, exception filter | 24 |
| Authentication and Authorization | JWT in a cookie, roles, CAPTCHA, rate limiting | 25 to 27 |
| Layered Architecture | web / business logic / DAO with TypeORM, transactions, optimistic locking | 28 |

Each example is presented with its complete code and line-by-line comments. The course also shows the results at runtime: browser screenshots, raw HTTP responses obtained with `curl`, and server logs.

## The Case Study: RdvMedecins

The case study is a complete application for **scheduling appointments at a medical practice**. It consists of about sixty files, and **all** of them are listed and commented on. It brings together all the concepts covered in the previous chapters.

- **Three roles:**
  - `ADMIN` manages doctors and clients;
  - `DOCTOR` books and cancels appointments;
  - `USER` is the patient: they book appointments for themselves and manage their account.
- **Business rules:**
  - no appointments in the past;
  - only one upcoming appointment per patient;
  - no duplicate names, thanks to named uniqueness constraints;
  - An optimistic lock prevents overwriting a record that has been modified in the meantime by another user.
- **Privacy:** A patient never sees the names of other patients. This name is not even sent to their browser.
- **Security:**
  - JWT token in an `httpOnly` / `sameSite` cookie;
  - passwords hashed with bcrypt;
  - CAPTCHA and temporary lockout after multiple failed login attempts;
  - account creation protected by a single-use “passcode.”
- **A bilingual interface** (French/English), built with Bootstrap 5.
- **Progressive enhancement:** The application works entirely without JavaScript. A small script simply adds a confirmation dialog that can be navigated using the keyboard.

## Technologies

NestJS 10 · TypeScript 5 · Express · Handlebars (hbs) · class-validator / class-transformer · TypeORM · MySQL 8 / MariaDB · Passport JWT · bcrypt · svg-captcha · Bootstrap 5

## Prerequisites

- A basic understanding of TypeScript (or JavaScript), HTML, and the HTTP protocol.
- Node.js 20 or newer, Visual Studio Code, and a MySQL server (e.g., Laragon on Windows). Installation instructions are provided in the course appendices.

## Author

This course, its examples, and its case study were written by **Claude**, the AI from [Anthropic](https://www.anthropic.com) (September 2026).
