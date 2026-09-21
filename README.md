# Restaurante App 
## Componentes y contenedores con Tkinder

## Datos del estudiante

**Nombre**: Bonner Javier García Guanga


## Descripción
El objetivo de la semana 14 es mejorar la interfaz gráfica de la aplicación mediante el uso de componentes y contenedores, manteniendo la arquitectura desarrollada en semanas anteriores y permitiendo la gestión de productos mediante operaciones básicas de registro, consulta, actualización y eliminación


## Estructura del proyecto

```text
biblioteca_app/
├── assets/
│   ├── icons/
│   └── logo/
├── datos/
│   ├── libros.json
│   └── usuarios.json
├── modelos/
├── servicios/
├── ui/
└── main.py

``` 

## Capas

`modelos/`: define las clases `Usuario` y `Producto`, con validaciones basicas para evitar campos vacios.

`servicios/`: contiene la logica de consulta, registro, actualizacion, eliminacion y persistencia.

`datos/`: guarda la informacion persistente en archivos JSON.

`ui/`: contiene las vistas creadas con Tkinter.

`assets/icons/`: contiene los iconos PNG usados por los botones. Si falta un icono, la aplicacion sigue funcionando con texto.

`assets/logo/`: contiene la identidad visual principal de la aplicacion. `logo.png` se muestra dentro de la interfaz y `icono.png` se usa como icono de la ventana.

## Componentes utilizados

La interfaz gráfica fue desarrollada utilizando componentes de Tkinter y ttk:

- Label
- Entry
- Button
- Frame
- LabelFrame
- Treeview
- Scrollbar
- Messagebox

## Contenedores utilizados

Para mejorar la organización visual de la aplicación se utilizaron los siguientes contenedores:

- Frame para dividir las diferentes áreas de la interfaz.
- LabelFrame para agrupar formularios y secciones de información.
- Frame lateral para el menú de navegación.
- Frame principal para el contenido dinámico.
- Barra de estado para mostrar información general del sistema.

## Funcionalidades implementadas

**Inicio de sesión**

La aplicación solicita usuario y contraseña para acceder al sistema.

La validación se realiza mediante RestauranteServicio, manteniendo separada la lógica de negocio de la interfaz gráfica.

**Consulta de usuarios**

Permite visualizar los usuarios registrados en el sistema mediante una tabla organizada en la interfaz.

**Gestión de productos**

La sección Productos permite realizar las siguientes operaciones:

- Registrar producto.
- Consultar producto por código.
- Actualizar producto.
- Eliminar producto.
- Visualizar productos registrados.

Todas las operaciones son ejecutadas mediante botones utilizando command= y delegadas a RestauranteServicio.

**Persistencia de datos**

La información se almacena en archivos JSON locales:

- productos.json
- usuarios.json

La lectura y escritura de datos se realiza mediante ArchivoServicio.

Las modificaciones permanecen almacenadas incluso después de cerrar la aplicación.

## Flujo general de la aplicación

```text
Inicio de la aplicación
        ↓
LoginView
        ↓
Validación de credenciales
        ↓
MainView
        ↓
Consulta de usuarios
        ↓
Gestión de productos
        ↓
Registrar | Consultar | Actualizar | Eliminar
        ↓
RestauranteServicio
        ↓
Persistencia en productos.json
        ↓
Actualización de la interfaz
```

## Ejecución del proyecto

1. Abrir el proyecto en Visual Studio Code.
2. Verificar que existan los archivos JSON dentro de la carpeta datos.
3. Ejecutar el archivo principal:
```text
python main.py
```
4. Ingresar con un usuario registrado.
5. Utilizar el menú lateral para acceder a Usuarios o Productos.

## Credencial de demostración

Usuario: `admin`

Contrasena: `1234`

## Mejoras realizadas 

- Reorganización visual de la interfaz mediante contenedores.
- Incorporación de formularios para la gestión de productos.
- Implementación de tabla para visualización de registros.
- Integración de botones de acción para CRUD de productos.
- Actualización automática de la información mostrada.
- Mejora de la experiencia de usuario mediante una interfaz más clara y ordenada.
- Conservación de la arquitectura modular desarrollada en semanas anteriores.

## Conclusión

La evolución del proyecto permitió fortalecer el desarrollo de interfaces gráficas mediante el uso de componentes y contenedores de Tkinter. La aplicación mantiene la separación de responsabilidades entre modelos, servicios e interfaz, permitiendo gestionar productos de forma organizada y conservar la información mediante archivos JSON. Además, la mejora visual realizada facilita la interacción del usuario y demuestra la integración adecuada de los conceptos estudiados durante la semana.