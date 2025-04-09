
# MoviesApi

MoviesApi is a RESTful API built with ASP.NET Core 8.0 that allows users to manage movies and genres. It provides endpoints for creating, retrieving, updating, and deleting movies and genres, as well as filtering movies by genre.

## Features

- **Movies Management**: Create, retrieve, update, and delete movies.
- **Genres Management**: Create, retrieve, update, and delete genres.
- **Filtering**: Retrieve movies by genre.
- **File Upload**: Upload movie posters with size and format validation.
- **Swagger Integration**: API documentation and testing using Swagger UI.
- **JWT Authentication**: Secure endpoints with Bearer token authentication.

## Technologies Used

- **.NET 8.0**
- **Entity Framework Core**: Database access and migrations.
- **AutoMapper**: Object mapping.
- **Swashbuckle**: Swagger/OpenAPI documentation.
- **SQL Server**: Database provider.

## Getting Started

### Prerequisites

- .NET 8.0 SDK
- SQL Server
- Visual Studio 2022 or any compatible IDE

### Installation

1. Clone the repository:
   
```
   git clone https://github.com/your-repo/moviesapi.git
   cd moviesapi
   
```

2. Configure the database connection string in `appsettings.json`:
   
```
   "ConnectionStrings": {
     "DefaultConnection": "Your SQL Server connection string here"
   }
   
```

3. Apply database migrations:
   
```
   dotnet ef database update
   
```

4. Run the application:
   
```
   dotnet run
   
```

5. Access the Swagger UI at `https://localhost:<port>/swagger`.

## API Endpoints

### Movies

- `GET /api/movies`: Retrieve all movies.
- `GET /api/movies/{id}`: Retrieve a movie by ID.
- `GET /api/movies/GetByGenreId?genreId={genreId}`: Retrieve movies by genre ID.
- `POST /api/movies`: Create a new movie (requires poster upload).
- `PUT /api/movies/{id}`: Update an existing movie.
- `DELETE /api/movies/{id}`: Delete a movie.

### Genres

- `GET /api/genres`: Retrieve all genres.
- `POST /api/genres`: Create a new genre.
- `PUT /api/genres/{id}`: Update an existing genre.
- `DELETE /api/genres/{id}`: Delete a genre.

## Validation Rules

- **Poster**: Only `.jpg` and `.png` formats are allowed, with a maximum size of 1MB.
- **Genre**: Genre ID must be valid when creating or updating a movie.
