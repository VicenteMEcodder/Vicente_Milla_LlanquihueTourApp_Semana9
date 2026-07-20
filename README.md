# Vicente_Milla_LlanquihueTourApp_Semana9
Llanquihue tour app es una aplicación de gestión desarrollado únicamente con Java que permite administrar las operaciones de la agencia de turismo de Llanquihue, ubicada en la comuna homónima, en la región de los Lagos en chile.

La aplicación permite gestionar eficazmente:

1. Gestionar guías turísticos, proveedores, operadores y tours.
2. Administrar servicios turísticos (rutas gastronómicas, paseos lacustres a lo largo de la comuna y excursiones culturales).
3. Registrar y buscar entidades.
4. Realizar registros y búsquedas de entidades.
5. Presentar la información a través de una interfaz grafica.


Estructura del Llanquihue Tour App:

# Llanquihue Tour App

## Descripcion del Sistema

Llanquihue Tour App es un sistema de gestion turistica desarrollado en Java que permite administrar las operaciones de la agencia de turismo Llanquihue Tour, ubicada en la comuna de Llanquihue, Region de Los Lagos, Chile.

El sistema permite:
- Gestionar guias turisticos, proveedores, operadores y tours
- Administrar servicios turisticos (rutas gastronomicas, paseos lacustres, excursiones culturales)
- Registrar y buscar entidades
- Visualizar informacion a traves de consola e interfaz grafica
- Aplicar principios de Programacion Orientada a Objetos

## Estructura del Proyecto

Estructura del Llanquihue Tour App:

LlanquihueTourApp/

├── app/ # Punto de entrada de la aplicacion

│ └── LlanquihueTourApp.java

├── data/ # Gestion de datos

│ ├── DataLoader.java # Carga de datos desde archivos

│ ├── DataManager.java # Gestion central de datos

│ ├── GestorEntidades.java # Gestion de entidades Registrables

│ └── GestorServicios.java # Gestion de servicios turisticos

├── model/ # Clases del dominio

│ ├── Registrable.java # Interfaz para entidades registrables

│ ├── Persona.java # Clase base para personas

│ ├── Guia.java # Guia turistico

│ ├── Proveedor.java # Proveedor de servicios

│ ├── Operador.java # Operador de transporte

│ ├── ServicioTuristico.java # Clase base para servicios

│ ├── RutaGastronomica.java

│ ├── PaseoLacustre.java

│ ├── ExcursionCultural.java

│ └── Tour.java # Paquete turistico

├── service/ # Servicios de negocio

│ ├── BusquedaService.java # Busqueda de informacion

│ └── RegistroService.java # Registro de entidades

├── ui/ # Interfaz de usuario

│ └── GuiLlanquihueTour.java # GUI con Swing

├── util/ # Utilidades

│ └── Validador.java # Validaciones (RUT, email, etc.)

└── resources/ # Archivos de datos

├── guias.txt

├── proveedores.txt

├── operadores.txt

└── tours.txt

## Clases Principales y sus Funciones

### Modelo (model/)

| Clase | Descripcion |
|-------|-------------|
| `Registrable` | Interfaz que define el contrato `mostrarResumen()` para todas las entidades del sistema. Permite el polimorfismo y la gestion unificada de diferentes tipos de entidades. |
| `Persona` | Clase base para todas las personas del sistema. Contiene atributos comunes: RUT, nombre, apellido, telefono y email. Proporciona validaciones y metodos getters/setters. |
| `Guia` | Representa un guia turistico. Extiende Persona e incluye especialidad, anos de experiencia, certificacion e idiomas. Implementa `mostrarResumen()` para mostrar informacion especifica. |
| `Proveedor` | Representa un proveedor de servicios turisticos. Extiende Persona e incluye tipo de servicio, rubro, calificacion (1-5) y estado (activo/inactivo). |
| `Operador` | Representa un operador de transporte. Extiende Persona e incluye tipo de operacion, zona de operacion, capacidad maxima y estado de habilitacion. |
| `ServicioTuristico` | Clase base para servicios turisticos. Contiene nombre y duracion en horas. Implementa Registrable y proporciona el metodo `mostrarInformacion()`. |
| `RutaGastronomica` | Representa una ruta gastronomica. Extiende ServicioTuristico e incluye el numero de paradas gastronomicas. |
| `PaseoLacustre` | Representa un paseo lacustre. Extiende ServicioTuristico e incluye el tipo de embarcacion utilizada. |
| `ExcursionCultural` | Representa una excursion cultural. Extiende ServicioTuristico e incluye el lugar historico a visitar. |
| `Tour` | Representa un paquete turistico completo. Implementa Registrable e incluye codigo, nombre, descripcion, precio, duracion, guia asignado, lista de proveedores y actividades. |

### Gestion de Datos (data/)

| Clase | Descripcion |
|-------|-------------|
| `DataLoader` | Clase utilitaria para cargar datos desde archivos de texto (.txt) en la carpeta resources/. Proporciona metodos estaticos para cargar guias, proveedores, operadores y tours. |
| `DataManager` | Clase central de gestion de datos. Mantiene colecciones de todas las entidades y proporciona metodos para buscar, filtrar y mostrar informacion. |
| `GestorEntidades` | Gestiona entidades que implementan la interfaz Registrable en una coleccion polimorfica. Permite agregar, listar y filtrar entidades por tipo usando instanceof. |
| `GestorServicios` | Gestiona especificamente los servicios turisticos. Proporciona metodos para agregar, listar y mostrar estadisticas de servicios. |

### Servicios de Negocio (service/)

| Clase | Descripcion |
|-------|-------------|
| `BusquedaService` | Proporciona funcionalidades de busqueda para guias, proveedores, tours y servicios turisticos. Permite filtrar por especialidad, rubro, precio, nombre y duracion. |
| `RegistroService` | Proporciona funcionalidades de registro para nuevas entidades. Permite registrar nuevos guias y proveedores en el sistema. |

### Interfaz de Usuario (ui/)

| Clase | Descripcion |
|-------|-------------|
| `GuiLlanquihueTour` | Interfaz grafica desarrollada con Swing. Permite registrar guias, proveedores y tours, mostrar listados y estadisticas de entidades de forma visual e intuitiva. |

### Utilidades (util/)

| Clase | Descripcion |
|-------|-------------|
| `Validador` | Clase utilitaria con metodos estaticos para validar RUT, email, telefono, textos no vacios, numeros positivos y calificaciones (1-5). |

## Principios de POO Aplicados

| Principio | Aplicacion |
|-----------|------------|
| **Encapsulamiento** | Atributos privados con getters y setters en todas las clases |
| **Herencia** | `Persona` -> `Guia`, `Proveedor`, `Operador`; `ServicioTuristico` -> `RutaGastronomica`, `PaseoLacustre`, `ExcursionCultural` |
| **Polimorfismo** | Coleccion `List<Registrable>` con llamado a `mostrarResumen()` sin importar el tipo concreto |
| **Interfaces** | `Registrable` con metodo `mostrarResumen()` como contrato comun |
| **Composicion** | `Tour` contiene listas de `Proveedor` y referencia a `Guia` |
| **Sobrescritura** | `@Override` en metodos `mostrarResumen()` y `toString()` |
| **Sobrecarga** | Multiples constructores en `Persona`, `Guia`, `Proveedor`, `Operador` |

## Instrucciones para Clonar y Ejecutar el Proyecto

### Requisitos Previos

| Requisito | Version |
|-----------|---------|
| Java Development Kit (JDK) | 17 o superior |
| IntelliJ IDEA (recomendado) | 2023.1 o superior |
| Git | 2.0 o superior |
| Sistema Operativo | Windows, macOS o Linux |

### Paso 1: Clonar el Repositorio

Abre la terminal o consola de comandos y ejecuta el siguiente comando:

```bash
git clone https://github.com/tu-usuario/LlanquihueTourApp.git
```

Alternativamente, si el repositorio es privado, usa:

```bash
git clone git@github.com:tu-usuario/LlanquihueTourApp.git
```

### Paso 2: Abrir el Proyecto en IntelliJ IDEA

1. Abre IntelliJ IDEA
2. Selecciona "Open" o "Abrir"
3. Navega hasta la carpeta donde clonaste el proyecto y selecciona la carpeta `LlanquihueTourApp`
4. Espera a que IntelliJ indexe los archivos y configure el proyecto

### Paso 3: Configurar el JDK

1. Ve a `File` > `Project Structure` > `Project`
2. En `SDK`, selecciona Java 17 o superior
3. En `Language level`, selecciona `17 - Sealed types, preview features`
4. Haz clic en `Apply` y luego en `OK`

### Paso 4: Ejecutar el Proyecto

#### Desde IntelliJ IDEA

1. Navega al paquete `app`
2. Haz clic derecho en `LlanquihueTourApp.java`
3. Selecciona `Run 'LlanquihueTourApp.main()'`
4. El sistema se ejecutara en la consola


### Paso 5: Usar el Sistema

Una vez ejecutado el sistema, se mostrara el menu principal:

+=================================================+
|                                                 |
|        LLANQUIHUE TOUR APP                      |
|        Sistema de Gestion Turistica             |
|        Region de Los Lagos, Chile               |
|                                                 |
+=================================================+

=== MENU PRINCIPAL ===
1. Mostrar todos los datos
2. Buscar informacion
3. Registrar nuevo elemento
4. Ver estadisticas
5. Abrir interfaz grafica
6. Salir
Seleccione una opcion:
```

### Estructura de Archivos de Datos

Los archivos .txt en la carpeta `resources/` deben seguir estos formatos:

| Archivo | Formato |
|---------|---------|
| `guias.txt` | `rut,nombre,apellido,telefono,email,especialidad,anosExp,certificado,idiomas` |
| `proveedores.txt` | `rut,nombre,apellido,telefono,email,tipoServicio,rubro,calificacion` |
| `operadores.txt` | `rut,nombre,apellido,telefono,email,tipoOperacion,zona,capacidad` |
| `tours.txt` | `codigo,nombre,descripcion,precio,duracion,rutGuia,rutsProveedores|actividades` |

### Ejemplo de Archivo guias.txt

```
12345678-9,Maria,Gonzalez,987654321,maria@email.com,Trekking,5,true,Espanol,Ingles
87654321-0,Juan,Perez,912345678,juan@email.com,Navegacion,8,false,Espanol
```

### Ejemplo de Archivo tours.txt

```
TR-001,Tour Lago Todos los Santos,Recorrido por el lago,45000,4,12345678-9,87654321-0|11223344-5,Navegacion|Almuerzo
```

## Solucion de Problemas Comunes

| Problema | Solucion |
|----------|----------|
| `ClassNotFoundException` | Verifica que el proyecto este compilado correctamente y que el `classpath` este configurado |
| `FileNotFoundException` | Asegurate de que los archivos .txt esten en la carpeta `resources/` |
| `UnsupportedClassVersionError` | Actualiza tu JDK a la version 17 o superior |
| La interfaz grafica no se abre | Verifica que Swing este instalado correctamente en tu JDK |

## Tecnologias Utilizadas

| Tecnologia | Version | Uso |
|------------|---------|-----|
| Java | 17+ | Lenguaje de programacion principal |
| Swing | - | Interfaz grafica de usuario (GUI) |
| Git | - | Control de versiones |
| Mermaid.js | - | Diagramas de estructura en README |

## Desarrollado por

Vicente Milla Espinoza
Duoc UC- Programacion orientada a objetos 

## Licencia

Este proyecto es de uso academico y no tiene licencia comercial.
