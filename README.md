# BookApi – REST API pentru gestionarea cărților

## Descriere generală

BookApi este o aplicație **WEB REST** dezvoltată în **C# (.NET 8)** care oferă operații **CRUD** pentru gestionarea unei liste de cărți.  
Datele sunt stocate într-o bază de date locală **SQLite**, accesată prin **Entity Framework Core**.  
Aplicația este containerizată și poate rula în **Docker**, conform cerințelor de laborator.

---

## Tehnologii folosite

- .NET 8 – ASP.NET Core Web API  
- C#  
- Entity Framework Core 8  
- SQLite (bază de date locală – fișier `books.db`)  
- Swagger / Swashbuckle (documentare și testare API)  
- Docker + Docker Compose

---

## Arhitectură

Arhitectura este de tip **Client – REST API – Database**:

- **Client** – consumă API-ul (Swagger, Postman sau altă aplicație web)
- **REST API (.NET)** – implementează logica și expune endpoint-uri HTTP
- **SQLite** – păstrează datele în mod persistent

Straturile aplicației:

- `Controllers` – definesc endpoint-urile HTTP
- `Services` – conțin logica de business (BookService)
- `Data` – contextul EF Core (`AppDbContext`)
- `Models` – entități mapate în baza de date (`Book`)
- `Dtos` – Data Transfer Objects (`BookDto`)

---

## Structura proiectului

```text
BookApi/
 ├─ Controllers/
 │   └─ BookController.cs
 ├─ Services/
 │   └─ BookService.cs
 ├─ Data/
 │   └─ AppDbContext.cs
 ├─ Models/
 │   └─ Book.cs
 ├─ Dtos/
 │   └─ BookDto.cs
 ├─ Migrations/
 ├─ books.db
 ├─ Program.cs
 ├─ BookApi.csproj
 ├─ Dockerfile
 └─ docker-compose.yml
