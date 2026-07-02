# Docker PHP DB Apache

tags: #internship #learning #docker #php #database #apache

## Why this matters

Docker can package the development environment so PHP, database, and web server versions are controlled and easier to reproduce.

## Mental model

Instead of installing everything directly on Windows, each service can run in its own container:

```text
PHP application
Database
Apache / web server
```

These containers communicate with each other like separate machines in a small private network.

## What to learn first

- What is an image?
- What is a container?
- What is a volume?
- What is a port mapping?
- What is `docker compose`?
- How PHP connects to a database container
- How Apache/Nginx serves a PHP app

## Internship context

Raw notes mention:

- using Docker for environment
- learning Docker for PHP, DB, Apache
- checking Gino's WSL setup and `/project` folder

## Related notes

- [[PHP MVC CodeIgniter Laravel]]
- [[SQL on Ubuntu]]
- [[2026-06-15]]
