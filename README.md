# 🛒 URBAN GROCERS – API para pedidos de kits de comestibles

URBAN GROCERS es una API que permite gestionar pedidos de comestibles agrupados en kits. Este proyecto forma parte del bootcamp de QA Engineer en TripleTen y tiene como objetivo automatizar pruebas de endpoints clave como creación de usuarios y consulta de kits de productos.

---

## 🚀 Funcionalidades principales

- Crear usuarios con nombre, teléfono y dirección.
- Consultar los kits de productos disponibles.
- Verificar que los datos de los usuarios registrados se almacenen correctamente.
- Automatizar pruebas positivas para el endpoint de creación de usuarios.

---

## 🛠️ Tecnologías utilizadas

- Python 3.x
- `requests` – Para el envío de solicitudes HTTP
- `pytest` (puede añadirse para pruebas más avanzadas)
- API RESTful proporcionada por TripleTen

---

## 📁 Estructura del proyecto

```bash
urban-grocers-api/
├── configuration.py           # Contiene las rutas y URL base del servicio
├── data.py                    # Define los headers y datos base para usuarios y productos
├── sender_stand_request.py   # Funciones para interactuar con la API (POST, GET)
├── create_user_test.py        # Pruebas positivas y negativas para la creación de usuarios
└── README.md                  # Documentación del proyecto

## 📌 Endpoints principales

- `POST /api/v1/users/` – Crear un nuevo usuario
- `GET /api/db/resources/user_model.csv` – Obtener la tabla de usuarios
- `GET /api/v1/products/kits/` – Consultar kits de productos

---

## 🔍 Ejemplo de prueba automatizada

Archivo: `create_user_test.py`

```python
def positive_assert(first_name):
    user_body = get_user_body(first_name)
    user_response = sender_stand_request.post_new_user(user_body)
    assert user_response.status_code == 201
    assert user_response.json()["authToken"] != ""
    
    Se hacen preubas negativas y positivas.

📎 Notas adicionales
Proyecto desarrollado como parte del Bootcamp de QA Engineer de TripleTen.

El entorno de pruebas está basado en una URL y rutas proporcionadas por la academia.

Desarrollado por Sara Correa – Bootcamp QA Engineer