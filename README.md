# Course Management

A full-stack web app where teachers can add and manage the courses they teach, and visitors can browse what's on offer and get in touch with a teacher about a course.

The repo is split in two:

- `Server/` — a .NET 7 Web API. I kept it in layers: `Server` holds the API and controllers, `Bl` the business logic, `DataAccessLayer` the EF Core code and the database, and `Common` for shared pieces. There are two controllers so far — one for authentication (register / login) and one for the courses. Data is stored in SQL Server and accessed through Entity Framework Core.
- `Client/react-project-2024/` — the frontend, in React 18. Routing is react-router-dom, API calls go through axios, forms use react-hook-form, and styling is Bootstrap.

## Running it locally

You'll need the .NET 7 SDK, Node, and SQL Server LocalDB.

Backend:

```
cd Server
dotnet run --project Server/Server.csproj
```

Frontend, in a second terminal:

```
cd Client/react-project-2024
npm install
npm start
```

The React app comes up on http://localhost:3000 and talks to the API. On Windows there's also a `run.ps1` at the root that starts both at once.

## Database

The models were scaffolded from an existing SQL Server database (`CoursesDB`), which I ran on LocalDB while developing. Before the course endpoints will work you'll need to point the connection string in `Server/Server/appsettings.json` at your own database.

## Notes

This was one of the first bigger full-stack things I built, so parts of it are rougher than how I'd write them now. But it's a complete, working app — authentication, a real database, and a React client all wired together end to end. If you look through it and see something worth changing, tell me.
