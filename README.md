# LiterAlura 📚 – Catálogo de Libros y Autores

Proyecto de consola en **Java 17 + Spring Boot 3.2 + Spring Data JPA + PostgreSQL 16** que consume la **API Gutendex** y construye un pequeño catálogo persistente de libros y autores.

---

## ✨ Características

| Sprint | Funcionalidad principal | Detalles |
|--------|------------------------|-----------|
| 1      | Configuración del entorno | Java 17, Maven 4, Spring Boot 3.2, PostgreSQL 16 |
| 2      | Exploración de la API Gutendex | [gutendex.com/books](https://gutendex.com/books) |
| 3      | Cliente HTTP (HttpClient) | Solicitudes `GET` y manejo de respuestas |
| 4–5    | Deserialización JSON (Jackson) | DTO ➜ clases Java (`BookDTO`, `AuthorDTO`) |
| 6      | Interfaz CLI (CommandLineRunner) | Menú interactivo con `Scanner` |
| 7      | Catálogo en memoria | Buscar libro por título, listar libros, filtrar por idioma |
| 8      | Gestión de autores | Listar autores, filtrar autores vivos por año |
| 9      | Persistencia con PostgreSQL | Entidades JPA (`Book`, `Author`) y repositorios |

---

## 🗄️ Modelo de Datos

### Entidades JPA

| Entidad | Tabla | Campos principales | Relaciones |
|---------|-------|--------------------|------------|
| `Author` | `author` | `id`, `name`, `birth_year`, `death_year` | `@OneToMany` libros |
| `Book` | `book` | `id`, `title`, `languages`, `download_count` | `@ManyToOne` author |

### DTO (para JSON)

- `AuthorDTO`  
- `BookDTO`

---

## ⚙️ Instalación

```bash
# Clonar el proyecto
git clone https://github.com/tu-usuario/literalura.git
cd literalura

# Configurar PostgreSQL (ejemplo)
createdb literalura
createuser postgres -P  # password: joxbar
