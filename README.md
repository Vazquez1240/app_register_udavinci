# API de Registro de Usuarios

API simple construida con FastAPI para el registro de usuarios con almacenamiento en MySQL.

## Requisitos Previos

- Python 3.10 o superior
- MySQL Server
- pip (gestor de paquetes de Python)

## Configuración

1. Clonar el repositorio:
```bash
git clone <url-del-repositorio>
cd ApiRegistro
```

2. Crear y activar el entorno virtual:
```bash
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

3. Instalar dependencias:
```bash
pip install -r requirements.txt
```

4. Configurar la base de datos:
- Crear una base de datos en MySQL llamada `user_registration`
- Modificar el archivo `database.py` con tus credenciales de MySQL:
```python
SQLALCHEMY_DATABASE_URL = "mysql+pymysql://root:tu_contraseña@localhost/user_registration"
```

## Ejecutar la Aplicación

1. Iniciar el servidor:
```bash
uvicorn main:app --reload
```

2. La API estará disponible en: `http://localhost:8000`

## Uso de la API

### Registrar un Usuario
```bash
POST http://localhost:8000/?nombre=martin&username=vazquez1250&password=eeee
```

Respuesta exitosa:
```json
{
    "message": "User registered successfully",
    "user_id": 1
}
```

## Notas
- Las contraseñas se almacenan de forma segura usando bcrypt
- Los nombres de usuario deben ser únicos
- La API verifica duplicados de usuarios antes de registrar 