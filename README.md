# TaskManager API 📝

> Un backend robusto y escalable en FastAPI para gestionar tareas — diseñado con buenas prácticas y listo para integrarse con un frontend en React.

## 🚀 Descripción del Proyecto
**TaskManager API:** Un servicio RESTful basado en FastAPI para crear, leer, actualizar y eliminar tareas. Construido con arquitectura limpia, Pydantic, SQLAlchemy y Docker

## 📋 Tabla de Contenidos
- [Características](#características)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Arquitectura y Estructura](#arquitectura-y-estructura)
- [Primeros Pasos](#primeros-pasos)
- [Uso](#uso)
- [Documentación de la API](#documentación-de-la-api)
- [Tests](#tests)
- [CI/CD](#cicd)
- [Buenas Prácticas](#buenas-prácticas)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)

## ✨ Características
- Operaciones CRUD para tareas
- Autenticación de usuarios (JWT) (Proximamente)
- Validación de entrada con esquemas Pydantic
- Migraciones de base de datos con Alembic
- Dockerizado para desarrollo y despliegue consistentes (Proximamente)
- Documentación interactiva de la API (Swagger UI y ReDoc)

## 🛠 Tecnologías Utilizadas
| Capa             | Tecnología               |
| ---------------- | ------------------------ |
| Framework        | FastAPI                  |
| ORM de base de datos | SQLAlchemy            |
| Migraciones      | Alembic                  |
| Autenticación    | JSON Web Tokens (JWT)    |
| Configuración    | pydantic (BaseSettings)  |
| Testing          | pytest, HTTPX            |
| CI/CD            | GitHub Actions           |
| Contenerización  | Docker y Docker Compose  |
| Linter/Formato   | black, isort, flake8, mypy |

## 🏗 Arquitectura y Estructura
```
│
├── app/                        # Código fuente principal de la aplicación
│   ├── api/                    # Rutas (endpoints de la API)
│   │   ├── v1/                 # Versión de la API
│   │   │   └── routes_tasks.py # Endpoints para tareas
│   │   └── __init__.py
│   │
│   ├── core/                   # Configuraciones de la app (CORS, settings, etc.)
│   │   └── config.py
│   │
│   ├── models/                 # Modelos de datos (pydantic y/o ORMs)
│   │   └── task.py
│   │
│   ├── schemas/                # Esquemas para validación de entrada/salida (Pydantic)
│   │   └── task.py
│   │
│   ├── services/               # Lógica de negocio (CRUD)
│   │   └── task_service.py
│   │
│   ├── db/                     # Interacción con almacenamiento (DB o archivo JSON)
│   │   └── json_handler.py
│   │
│   ├── main.py                 # Punto de entrada de la aplicación FastAPI
│   └── __init__.py
│
├── tests/                      # Pruebas unitarias y funcionales
│   └── test_tasks.py
│
├── venv/                       # Archivos del ambiente virtual
│
├── .gitignore
├── README.md
├── requirements.txt            # Dependencias
├── start.sh                    # Script para iniciar localmente
└── setup.sh                    # Script para configurar desde 0

```

## 📦 Uso
### Ejemplo cURL
```bash
curl -X POST "localhost:8000/tasks/" \
     -H "Content-Type: application/json" \
     -d '{"title":"Comprar víveres","description":"Leche, huevos, pan"}'
```

## 📖 Documentación de la API
FastAPI genera documentación interactiva automáticamente:
- Swagger UI: `/docs`

## 🔄 CI/CD (Proximamente)
- **Lint y Type Check**: black, isort, flake8, mypy
- **Pruebas**: pytest con cobertura
- **Despliegue**: construcción de imagen Docker al hacer push a `main`

## 📄 Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más información.
