# SISTEMA-UPARK

Sistema informático para la administración y el control del estacionamiento de UPIICSA. El proyecto busca centralizar la información de los beneficiarios, sus vehículos, los cajones asignados y los movimientos de entrada y salida.

## Descripción del proyecto

Al inicio de cada semestre, UPIICSA selecciona mediante convocatoria y sorteo a los alumnos y docentes que recibirán un cajón de estacionamiento. El sistema no realiza esta selección: la universidad proporcionará la lista de beneficiarios y sus asignaciones, y el administrador será responsable de registrarlas.

UPARK permitirá mantener actualizada esta información y facilitar la verificación de los vehículos autorizados, el control de los cajones y la consulta del historial de movimientos.

## Problemática

La administración manual puede presentar problemas cuando:

- Cambian las placas o los vehículos de un beneficiario.
- Se extravía o reemplaza un corbatín.
- Ingresa un automóvil no registrado.
- Es necesario identificar qué vehículos permanecen dentro de la universidad.
- Se requiere consultar quién utiliza un cajón o cuándo ocurrió un movimiento.
- Se desconoce el estado real de los cajones disponibles, ocupados o deshabilitados.

## Funcionalidades previstas

### Administración

- Registrar beneficiarios, indicando número de boleta o empleado.
- Asignar el cajón y el periodo de autorización correspondiente.
- Consultar y actualizar los datos de usuarios y vehículos.
- Cambiar el estado de los cajones a libre, ocupado o deshabilitado.
- Consultar vehículos dentro de las instalaciones.
- Revisar el historial de entradas y salidas.

### Beneficiarios

- Asociar hasta tres vehículos a su perfil.
- Registrar placas, marca, modelo, color y tipo de automóvil.
- Utilizar distintos vehículos durante el periodo autorizado.
- Evitar que más de un vehículo del mismo beneficiario permanezca dentro al mismo tiempo.

### Control de accesos

- Consultar a un beneficiario mediante su número de boleta o empleado.
- Verificar que el usuario, el vehículo y el periodo de autorización sean válidos.
- Registrar la entrada con fecha y hora.
- Marcar el cajón asignado como ocupado.
- Solicitar la salida y registrarla con fecha y hora.
- Liberar el cajón al completar el proceso de salida.
- Impedir registros incorrectos o movimientos duplicados.

## Roles

| Rol | Responsabilidades principales |
| --- | --- |
| Administrador | Registra beneficiarios, asignaciones y permisos; mantiene actualizada la información y supervisa el estado de los cajones. |
| Operador | Consulta beneficiarios y vehículos; registra entradas y confirma salidas. |
| Beneficiario | Proporciona sus datos y registra o actualiza sus vehículos autorizados. |

## Entidades principales

- **Beneficiario:** Datos personales e identificación académica o laboral.
- **Vehículo:** Placas, marca, modelo, color y tipo.
- **Cajón:** Identificador y estado dentro del estacionamiento.
- **Asignación:** Relación entre beneficiario, cajón y periodo de autorización.
- **Movimiento:** Entrada o salida de un vehículo, con fecha y hora.

## Flujo general

1. La universidad entrega al administrador la lista de beneficiarios y sus cajones.
2. El administrador registra a los usuarios y sus asignaciones vigentes.
3. Cada beneficiario registra hasta tres vehículos en su perfil.
4. Al ingresar, el operador verifica al usuario y identifica el vehículo.
5. El sistema valida la autorización y que el beneficiario no tenga otro vehículo dentro.
6. Si la información es correcta, se registra la entrada y el cajón pasa a ocupado.
7. Para la salida, el operador verifica la solicitud y registra la hora de salida.
8. El vehículo deja de aparecer como presente y el cajón pasa a libre.

## Arquitectura

El proyecto está organizado con una propuesta de arquitectura MVC:

```text
SISTEMA-UPARK-github/
├── Controller/    # Lógica de control y coordinacion de operaciones
├── Model/         # Entidades y reglas de negocio
├── View/          # Interfaces de interacción con el usuario
├── main.cpp       # Punto de entrada de la aplicación
└── README.md
```

## Tecnologías

- C++ para la implementación del sistema.
- Archivos locales o una base de datos para el almacenamiento de la información.
- Git para el control de versiones.
- Visual Studio Code como entorno de desarrollo.

## Estado del proyecto

El repositorio contiene la estructura inicial del sistema, pero la implementación aún no está disponible.

## Uso

Después de completar la implementación, la aplicación podrá compilarse con un compilador de C++, por ejemplo:

```bash
g++ main.cpp -o UPARK
```

En Windows puede ejecutarse el archivo generado:

```bash
UPARK.exe
```

## Posibles mejoras

- Interfaz gráfica para administrador, operador y beneficiario.
- Persistencia mediante archivos o una base de datos.
- Inicio de sesión con permisos por rol.
- Registro de incidentes y mantenimiento de cajones.
- Reportes por periodo, usuario, vehículo o movimiento.
- Generación de identificadores digitales o impresión de corbatines.

## Alcance

Este sistema atiende la administración posterior a la convocatoria y el sorteo. La selección de beneficiarios, la asignación inicial realizada por la universidad y el reparto de corbatines forman parte de procesos externos al sistema.

## Autoría

Proyecto académico desarrollado para la materia de Programación Orientada a Objetos.
