# CyberBank

[![Java](https://img.shields.io/badge/Java-Spring%20Boot%203.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Next.js](https://img.shields.io/badge/Next.js-14-000000?logo=nextdotjs)](https://nextjs.org)
[![MySQL](https://img.shields.io/badge/MySQL-AWS%20RDS-4479A1?logo=mysql&logoColor=white)](https://aws.amazon.com/rds/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A digital banking system with a Spring Boot REST API and a Next.js web client for customers, accounts, cards and transactions.

## Table of Contents

- [About](#about)
- [Features](#features)
- [API](#api)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Team](#team)
- [License](#license)

## About

CyberBank was built in two parts for a systems development course at Universidade
Presbiteriana Mackenzie (2024): first the Java back end with JPA persistence on a MySQL
database hosted on AWS RDS, then a React (Next.js) front end that consumes it. The UI
is in Portuguese.

## Features

- Customer registration identified by CPF, with contact data
- Bank accounts with branch, number and balance
- Debit and credit cards linked to an account
- Transfers between accounts with a transaction history
- Login, menu, cards and transactions screens on the web client

## API

| Resource | Endpoints |
| --- | --- |
| Customers | `GET/POST /api/cliente`, `GET/PUT/DELETE /api/cliente/{cpf}` |
| Accounts | `GET/POST /api/conta`, `GET/PUT/DELETE /api/conta/{id}` |
| Cards | `GET/POST /api/cartao`, `DELETE /api/cartao/{id}` |
| Transactions | `GET/POST /api/transacao`, `GET /api/transacao/{id}` |

## Getting Started

Requirements: JDK 17+, Node.js 18+ and a MySQL database.

**Back end**

```bash
git clone https://github.com/EnzoFerroni/Projeto-CyberBank.git
cd Projeto-CyberBank/backend
```

Point `spring.datasource.url` and `spring.datasource.username` in
`src/main/resources/application.properties` to your database. The password is read
from an environment variable:

```bash
export DB_PASSWORD=your_password
./mvnw spring-boot:run
```

Tables are created automatically (`ddl-auto=update`).

**Front end**

```bash
cd ../frontend
npm install
npm run dev
```

The client calls the API at `http://127.0.0.1:3000/api`; adjust the URLs in
`src/app` if your back end runs on another host or port.

## Project Structure

```
├── backend/    Spring Boot API (Controller, Entidades, Repositorio)
└── frontend/   Next.js client (Login, Menu, Cartao, Transacao)
```

## Team

- Enzo Ferroni ([@EnzoFerroni](https://github.com/EnzoFerroni))
- Leonardo Rodrigues
- Rafael Neves

## License

Released under the [MIT License](LICENSE). Copyright (c) 2024 Enzo Ferroni, Leonardo
Rodrigues and Rafael Neves.
