---
titulo: Validaciones y servicios en axum
fecha: 22/12/2025
dia: día 3
descripcionPrevia: Más practica y desarrollo de validaciones, manejo de errores y servicios.
layout: "../../layouts/PlantillaArticulos.astro"
---

# Validaciones y servicios en axum

#### Fecha: 22 de diciembre del 2025

Ok, el día de hoy fue un día bastante productivo, pasé aprendiendo como hacer validaciones en rust y en cómo aplicarselas a mis estructurar, no es tan dificil, resulta que hay una dependencia que se llama "validator" que me permite validar campos de una estructura, puedo manejar más fácilmente los errores.

Esa es otra cosa, estuve trabajando en una utilidad para manejar los errores que se pueden encontrar en una api, ya conocemos los más famosos, el not_found, el internal server error, el bad request, y entre muchos otros, solo que me centré en esos 3 que mencioné.

Al principio me costó mucho entenderlo, la curva de aprendizaje de rust es muy larga, y hay cosas que hay que dedicarle mucho tiempo para manejarlas a la perfección, por ahora logré entender lo que hice:

```rust
    use axum::{
    Json,
    http::StatusCode,
    response::{IntoResponse, Response},
    };
    use serde_json::json;
    use validator::ValidationErrors;

    #[derive(Debug)]
    pub enum AppError {
        NotFound(String),
        InternalServerError(String),
        ValidationError(ValidationErrors),
    }

    impl IntoResponse for AppError {
        fn into_response(self) -> Response {
            let (status, message_error) = match self {
                AppError::NotFound(message) => (
                    StatusCode::NOT_FOUND,
                    json!({
                        "success": false,
                        "message": message
                    }),
                ),
                AppError::InternalServerError(message) => (
                    StatusCode::INTERNAL_SERVER_ERROR,
                    json!({
                        "success": false,
                        "message": message
                    }),
                ),
                AppError::ValidationError(err) => {
                    let error = err
                        .field_errors()
                        .into_iter()
                        .map(|(field, errors)| {
                            let messages: Vec<String> = errors
                                .iter()
                                .filter_map(|e| e.message.clone())
                                .map(|m| m.to_string())
                                .collect();

                        json!({
                            "field": field,
                            "error": messages
                        })
                    })
                    .collect::<Vec<_>>();

                (
                    StatusCode::BAD_REQUEST,
                    json!({
                        "success": false,
                        "message": "Validation Error",
                        "errors": error
                    }),
                )
            }
        };
        (status, Json(message_error)).into_response()
    }

}

```

Todo ese código de ahí me costó un poco, me siento muy orgulloso de comprenderlo, métodos como el into_iter, el filter_map y esos método raros no los comprendía pero logré hacerlo.

Me enfoqué hoy más que todo en la práctica de crear y comprender la estructura que estoy utilizando en axum, es la siguiente, no está tan alejada a la que uso en node js:

```rust
    api-users-rust/
    ├── Cargo.toml
    ├── .env                    # Variables de entorno
    ├── .gitignore
    └── src/
        ├── main.rs            # Entry point, configuración del servidor
        ├── lib.rs             # Opcional: para exponer módulos públicos
        │
        ├── routes/            # Definición de rutas
        │   ├── mod.rs
        │   ├── users.rs
        │   └── auth.rs
        │
        ├── handlers/          # Controladores/Handlers (lógica de endpoints)
        │   ├── mod.rs
        │   ├── users.rs
        │   └── auth.rs
        │
        ├── models/            # Estructuras de datos (DTOs, entities)
        │   ├── mod.rs
        │   ├── user.rs
        │   └── response.rs
        │
        ├── services/          # Lógica de negocio
        │   ├── mod.rs
        │   └── user_service.rs
        │
        ├── repositories/      # Acceso a datos (DB, cache, etc)
        │   ├── mod.rs
        │   └── user_repository.rs
        │
        ├── middleware/        # Middleware (auth, logging, etc)
        │   ├── mod.rs
        │   └── auth.rs
        │
        ├── helpers/             # Utilidades
        │   ├── mod.rs
        │   └── validation.rs
        │
        └── config/            # Configuración
            ├── mod.rs
            └── database.rs
```

A veces por alguna razón suelo cambiar de utils a helpers, como que aún no me decido con cual quedarme, por ahora en proyectos de node js uso utils y en rust estoy usando helpers, realmente quería seguir practicando pero llevo todo el día con las validaciones, el manejo de errores y la creación de servicios.

El plan de mañana será hacer el módulo de autenticación con JWT, y si me da tiempo haré el crud completo, por ahora solo se puede obtener usuarios y crear usuarios, solo me hace falta eliminar y actualizar.
