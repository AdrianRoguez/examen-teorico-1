# examen-teorico-1

### Actor: **Cliente**

|  Actor | Cliente |
|---|---|
| Descripción  | Persona que utiliza el sistema para alquilar o reservar películas. |
| Características  | Registra datos personales, alquila o reserva películas. |
| Relaciones | Realiza las mismas acciones que el Administrador y el Proveedor en cuanto a interacción con el sistema (selección de películas, registros, etc.). |
| Referencias | Alquilar Película, Reservar Película, Proporcionar Datos Personales. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

| Atributo |||
|---|---|---|
| _Nombre_  | Cliente registrado | _Entidad_ |
| _Correo_  | Dirección de correo electrónico | _String_ |
| _Teléfono_  | Número de contacto | _String_ |

---

### Caso de Uso: **Alquilar Película**

| Caso de Uso (CU) | Alquilar Película |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Cliente, Administrador Videomax |
| Descripción | El cliente selecciona una película, la alquila y el sistema registra el alquiler. |
| Flujo básico | 1. Cliente selecciona película. 2. Cliente alquila película. 3. Administrador registra alquiler. |
| Pre-condiciones | El cliente debe estar registrado y tener una película seleccionada. |
| Post-condiciones | La película queda marcada como alquilada y el sistema registra la transacción. |
| Requerimientos | Cliente registrado en el sistema. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |
| Relaciones | **Include**: Seleccionar Película, Devolver Película |

---

### Caso de Uso: **Registrar Película**

| Caso de Uso (CU) | Registrar Película |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Proveedor, Administrador Videomax |
| Descripción | El proveedor registra las películas disponibles en el sistema Videomax. |
| Flujo básico | 1. Proveedor agrega película al sistema. 2. Administrador valida y registra la película. |
| Pre-condiciones | El proveedor debe tener películas para registrar. |
| Post-condiciones | Las películas quedan disponibles para alquiler y reserva. |
| Requerimientos | Acceso al sistema para registrar películas. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

---

### Actor: **Proveedor**

| Actor | Proveedor |
|---|---|
| Descripción  | Abastece las películas al sistema Videomax. |
| Características  | Registra películas, abastece según la demanda del sistema. |
| Relaciones | Interactúa con el Administrador Videomax para registrar y actualizar las películas. |
| Referencias | Abastecer Película, Registrar Película |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

| Atributo |||
|---|---|---|
| _Nombre_  | Proveedor de contenido | _Entidad_ |
| _Películas_  | Lista de películas suministradas | _Array de String_ |

---

### Caso de Uso: **Abastecer Película**

| Caso de Uso (CU) | Abastecer Película |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Proveedor |
| Descripción | El proveedor abastece las películas según las necesidades del sistema, es decir, ofrece películas que están disponibles para el alquiler. |
| Flujo básico | 1. Proveedor verifica la demanda de películas. 2. Proveedor abastece nuevas películas al sistema. |
| Pre-condiciones | El proveedor debe tener películas disponibles para abastecer. |
| Post-condiciones | Las películas están disponibles para su alquiler en el sistema. |
| Requerimientos | Películas para abastecer. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |
| Relaciones | **Extend**: Registrar Película |

---

### Actor: **Administrador Videomax**

| Actor | Administrador Videomax |
|---|---|
| Descripción  | Persona encargada de gestionar los registros de clientes, películas, alquileres y reservas. |
| Características  | Administra el sistema, realiza registros y actualiza la base de datos de películas y proveedores. |
| Relaciones | Colabora con el Cliente y el Proveedor para gestionar las operaciones. |
| Referencias | Registra Alquiler, Registra Reserva, Registra Película, Registra Cliente, Actualiza Proveedor |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

| Atributo |||
|---|---|---|
| _Nombre_  | Administrador | _Entidad_ |
| _ID_  | Identificación del administrador | _String_ |

---

### Caso de Uso: **Registrar Alquiler**

| Caso de Uso (CU) | Registrar Alquiler |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Administrador Videomax, Cliente |
| Descripción | El administrador registra un alquiler realizado por el cliente. |
| Flujo básico | 1. Cliente alquila película. 2. Administrador registra alquiler. |
| Pre-condiciones | Cliente debe haber seleccionado una película disponible. |
| Post-condiciones | El alquiler queda registrado en el sistema. |
| Requerimientos | Cliente registrado, película disponible. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

---

### Caso de Uso: **Registrar Reserva**

| Caso de Uso (CU) | Registrar Reserva |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Administrador Videomax, Cliente |
| Descripción | El administrador registra una reserva realizada por el cliente para una película no disponible. |
| Flujo básico | 1. Cliente selecciona película. 2. Cliente reserva película. 3. Administrador registra reserva. |
| Pre-condiciones | Cliente debe haber seleccionado una película no disponible para alquiler. |
| Post-condiciones | La película queda marcada como reservada para el cliente. |
| Requerimientos | Cliente registrado, película no disponible. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

---

### Caso de Uso: **Seleccionar Película**

| Caso de Uso (CU) | Seleccionar Película |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Cliente |
| Descripción | El cliente selecciona la película que desea alquilar o reservar. |
| Flujo básico | 1. Cliente navega en el catálogo. 2. Cliente selecciona película. |
| Pre-condiciones | Cliente debe estar registrado. |
| Post-condiciones | La película queda seleccionada para alquiler o reserva. |
| Requerimientos | Cliente registrado en el sistema. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |

---

### Caso de Uso: **Devolver Película**

| Caso de Uso (CU) | Devolver Película |
|---|---|
| Fuentes  | Documento de especificación del sistema Videomax |
| Actor  | Cliente |
| Descripción | El cliente devuelve la película que ha alquilado. |
| Flujo básico | 1. Cliente devuelve película. 2. Sistema registra la devolución. |
| Pre-condiciones | El cliente debe tener una película alquilada. |
| Post-condiciones | La película es marcada como disponible nuevamente. |
| Requerimientos | Cliente registrado, película alquilada. |
| Notas |  |
| Autor  | Adrián |
| Fecha | 19/11/2024 |