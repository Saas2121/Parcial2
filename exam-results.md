# Resultados del parcial práctico 2

Registrar resultados reales después de implementar y probar los endpoints. Sustituir los IDs de ejemplo por los utilizados.

| Petición y datos utilizados | Código esperado | Código obtenido | Observación |
| --- | --- | --- | --- |

| Crear una reserva con datos válidos y sala existente. | 201 | 201 | created |

| Crear con participants como texto. | 400 | 400 | "message": [
        "participants must not be greater than 20",
        "participants must not be less than 1",
        "participants must be an integer number"
    ],
    "error": "Bad Request", |


| Crear con una propiedad adicional, como status. | 400 | 400 |  "message": [
        "property status should not exist"
    ],
    "error": "Bad Request",|

| Crear con una sala inexistente. | 404 | 404 | "message": "Room was not found",
    "error": "Not Found" |


| Cancelar una reserva activa y consultar el cambio guardado. | 200 | 200 | ok |


| Cancelar de nuevo la misma reserva. | 409 | 409 | "Reservation is already cancelled"|

| Intentar cancelar con ID abc. | 400 | 400 | "Validation failed (numeric string is expected)" error bad request  |

| Intentar cancelar con un ID entero inexistente. | 404 | 404 | "Reservation with id 10 was not found" / "error": "Not Found"|

## Pruebas unitarias

Registrar el resultado de `npm test`.

| Caso | Resultado obtenido |
| --- | --- |
| 1. La regla real rechaza una reserva cancelada. | Pass |
| 2. El servicio cancela y guarda una reserva activa. | Failed |
| 3. Si la regla simulada rechaza, conserva active y no guarda. | Failed |

No alcance a implementar el segundo archivo en lo absoluto

Resumen de ejecución: parcial.
