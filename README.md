# Vicente_Milla_LlanquihueTourApp_Semana9
Llanquihue tour app es una aplicación de gestión desarrollado únicamente con Java que permite administrar las operaciones de la agencia de turismo de Llanquihue, ubicada en la comuna homónima, en la región de los Lagos en chile.

Estructura del Llanquihue Tour App:

LlanquihueTourApp/
├── app/                                      # Punto de entrada de la aplicacion
│   └── LlanquihueTourApp.java
├── data/                                     # Gestion de datos
│   ├── DataLoader.java                       # Carga de datos desde archivos
│   ├── DataManager.java                      # Gestion central de datos
│   ├── GestorEntidades.java                  # Gestion de entidades Registrables
│   └── GestorServicios.java                  # Gestion de servicios turisticos
├── model/                                    # Clases del dominio
│   ├── Registrable.java                      # Interfaz para entidades registrables
│   ├── Persona.java                          # Clase base para personas
│   ├── Guia.java                             # Guia turistico
│   ├── Proveedor.java                        # Proveedor de servicios
│   ├── Operador.java                         # Operador de transporte
│   ├── ServicioTuristico.java                # Clase base para servicios
│   ├── RutaGastronomica.java
│   ├── PaseoLacustre.java
│   ├── ExcursionCultural.java
│   └── Tour.java                             # Paquete turistico
├── service/                                  # Servicios de negocio
│   ├── BusquedaService.java                  # Busqueda de informacion
│   └── RegistroService.java                  # Registro de entidades
├── ui/                                       # Interfaz de usuario
│   └── GuiLlanquihueTour.java                # GUI con Swing
├── util/                                     # Utilidades
│   └── Validador.java                        # Validaciones (RUT, email, etc.)
└── resources/                                # Archivos de datos
    ├── guias.txt
    ├── proveedores.txt
    ├── operadores.txt
    └── tours.txt
