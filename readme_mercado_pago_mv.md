# Mercado Pago

Mercado Pago es una plataforma de pagos en línea popular en América Latina, que forma parte del ecosistema de Mercado Libre. Permite a los negocios y usuarios realizar transacciones de manera flexible y segura.

## Tabla de Contenido

1. [Funcionalidades de Mercado Pago](#funcionalidades-de-mercado-pago)
2. [Cómo funciona para comercios](#cómo-funciona-para-comercios)
3. [Cómo funciona para usuarios](#cómo-funciona-para-usuarios)
4. [Ventajas de Mercado Pago](#ventajas-de-mercado-pago)
5. [Componentes Principales de Mercado Pago](#componentes-principales-de-mercado-pago)
6. [Actores Involucrados en Mercado Pago](#actores-involucrados-en-mercado-pago)
7. [Relación entre Componentes y Actores](#relación-entre-componentes-y-actores)
8. [Diagramas Técnicos](#diagramas-técnicos)

## Funcionalidades de Mercado Pago
- **Aceptación de Pagos**: Acepta tarjetas de crédito, pagos en efectivo, transferencias bancarias y financiamiento a través de Mercado Crédito.
- **Mercado Pago Point**: Permite pagos presenciales con tarjetas a través de dispositivos conectados a smartphones.
- **Botón de Pago y Checkout**: Facilita la integración en tiendas en línea con opciones de pago personalizadas.
- **Pagos QR**: Los usuarios pueden pagar en tiendas físicas escaneando códigos QR.
- **Envío de dinero**: Transferencias entre personas sin costo o con comisiones bajas.
- **Billetera digital**: Los usuarios almacenan saldo para compras y pagos de servicios.

## Cómo funciona para comercios
Los comerciantes crean una cuenta, integran la pasarela de pagos en su tienda y gestionan las comisiones por transacción.

## Cómo funciona para usuarios
Los usuarios eligen Mercado Pago como método de pago en línea, usando la app para enviar dinero y pagar servicios.

## Ventajas de Mercado Pago
- **Seguridad**: Protocolos de seguridad avanzados.
- **Facilidad de uso**: Intuitiva y fácil de integrar.
- **Aceptación**: Amplia utilización en América Latina.
- **Opciones de financiamiento**: Posibilidad de pagar en cuotas.

## Componentes Principales de Mercado Pago
- **Pasarela de Pago**: Intermediario en transacciones.
- **API y Plugins**: Herramientas para integración.
- **Billetera Digital**: Almacenamiento de fondos.
- **Pagos QR**: Facilita pagos físicos.
- **Mercado Crédito**: Financiamiento para usuarios.
- **Panel de Control**: Monitoreo de ventas y transacciones.
- **Seguridad y Prevención de Fraude**: Múltiples protocolos de seguridad.

## Actores Involucrados en Mercado Pago
- **Usuarios**: Realizan compras y envían dinero.
- **Comercios**: Venden productos y gestionan pagos.
- **Entidades Financieras**: Procesan autorizaciones de pago.
- **Mercado Pago**: Opera la plataforma.
- **Mercado Crédito**: Ofrece líneas de crédito.
- **Proveedores de Infraestructura**: Soporte técnico y de seguridad.
- **Reguladores**: Supervisan operaciones financieras.

## Relación entre Componentes y Actores
Interacciones entre usuarios, comercios, Mercado Pago y entidades financieras para facilitar las transacciones y asegurar la protección de datos.

## Diagramas Técnicos
### Diagrama de Arquitectura
```mermaid
graph TD
    subgraph "Usuario Final"
        A[App/Plataforma de Usuario]
        B[Navegador Web]
    end
    
    subgraph "Pasarela de Pago"
        C[API de Mercado Pago]
        D[Proceso de Autenticación y Seguridad]
        E[Procesador de Transacciones]
        F[Validador de Pagos]
    end

    subgraph "Billetera Digital"
        G[Saldo en la Cuenta]
        H[Historial de Transacciones]
        I[Pagos a Servicios]
    end
    
    subgraph "Mercado Pago Point"
        J[Terminal de Pago]
        K[Conexión con Smartphone/Tablet]
    end
    
    subgraph "Medios de Pago"
        L[Tarjetas de Crédito/Débito]
        M[Transferencias Bancarias]
        N[Pagos en Efectivo]
        O[Mercado Crédito]
    end
    
    subgraph "Entidades Financieras"
        P[Bancos Emisores de Tarjetas]
        Q[Instituciones Financieras]
    end

    subgraph "Seguridad y Prevención de Fraude"
        R[Encriptación de Datos]
        S[Autenticación de 2 Factores]
        T[Monitoreo de Transacciones]
    end

    subgraph "Panel de Control del Comerciante"
        U[Dashboard de Ventas]
        V[Gestión de Transacciones]
        W[Reembolsos y Conciliación]
    end

    %% Relacion entre los componentes
    A -->|Acceso a la plataforma| C
    B -->|Acceso a la plataforma| C
    C -->|Validación de datos| D
    D -->|Seguridad y Autenticación| S
    D -->|Procesar pagos| E
    E -->|Verificar fondos| F
    F -->|Consulta de saldo| G
    F -->|Consulta medios de pago| L
    F -->|Consulta entidades bancarias| P

    %% Interacciones de la Billetera Digital
    A -->|Gestión de saldo| G
    G -->|Pagos y transferencias| H
    G -->|Pagos a servicios| I
    I -->|Interacción con el API| C

    %% Interacción de Punto de Venta (Point)
    J -->|Procesar pagos físicos| C
    K -->|Conexión con smartphone| J
    C -->|Validar pago físico| F

    %% Relación con medios de pago y entidades
    F -->|Verificar tarjeta| L
    F -->|Verificar transferencia| M
    F -->|Pagos en efectivo| N
    F -->|Pagos a crédito| O
    L -->|Procesar pago con tarjeta| P
    M -->|Procesar pago por banco| Q
    N -->|Pagos en efectivo en tiendas| Q

    %% Seguridad
    T -->|Monitoreo constante| F
    T -->|Prevención de fraude| F

    %% Panel de Control
    V -->|Monitoreo de transacciones| F
    W -->|Reembolsos| F
    V -->|Gestión de ventas| G
    U -->|Dashboard de ventas| G
```

#### Descripción del Diagrama Arquitectura de Software:
- Usuario Final accede a Mercado Pago a través de la aplicación móvil o el navegador web.
- La Pasarela de Pago (API de Mercado Pago) gestiona la interacción de usuarios, comercios y métodos de pago.
- El Proceso de Autenticación y Seguridad asegura que todas las transacciones sean verificadas mediante autenticación y encriptación.
- La Billetera Digital permite a los usuarios almacenar saldo, pagar servicios y consultar el historial de transacciones.
- Mercado Pago Point permite a los comerciantes aceptar pagos físicos mediante terminales conectadas a smartphones o tablets.
- Los Medios de Pago incluyen tarjetas, transferencias bancarias, pagos en efectivo, y Mercado Crédito.
- Las Entidades Financieras validan las transacciones con los bancos emisores de tarjetas y otros proveedores financieros.
- El Panel de Control del Comerciante ofrece a los vendedores la posibilidad de gestionar ventas, transacciones y reembolsos.
- Seguridad y Prevención de Fraude monitorea las transacciones y asegura la integridad de los datos.

### Diagrama de Flujo
```mermaid
graph TD
    %% Inicio del flujo
    Start((Inicio))

    %% Interacciones del usuario
    Start --> A[Usuario accede a la plataforma]
    A --> B{¿Transacción Online o Presencial?}
    
    %% Transacción online
    B -->|Online| C[Pasarela de Pago]
    C --> D[Autenticación de Usuario]
    D --> E[Validar Método de Pago]

    %% Opciones de medios de pago
    E --> F{¿Método de Pago?}
    F -->|Tarjeta de Crédito/Débito| G[Validar Tarjeta con Banco Emisor]
    F -->|Transferencia Bancaria| H[Procesar Transferencia]
    F -->|Efectivo| I[Generar Código de Pago]
    F -->|Mercado Crédito| J[Validar Crédito Disponible]

    %% Validación y procesamiento de pago
    G --> K[Autorización del Pago]
    H --> K
    I --> K
    J --> K
    
    %% Transacción presencial
    B -->|Presencial| L[Pago con Mercado Pago Point]
    L --> M[Conexión con Smartphone/Tablet]
    M --> E

    %% Confirmación de transacción
    K --> N{¿Pago Exitoso?}
    N -->|Sí| O[Notificar a Usuario y Comercio]
    N -->|No| P[Mostrar Error de Transacción]

    %% Opciones post-pago
    O --> Q{¿Generar Recibo?}
    Q -->|Sí| R[Generar y Enviar Recibo Digital]
    Q -->|No| S[Fin del Proceso]

    %% Fin del flujo
    P --> S[Fin del Proceso]
    R --> S
```

#### Descripción del diagrama de flujo:
- Inicio del Flujo: El usuario accede a la plataforma de Mercado Pago (app o web).
- Decisión Inicial: Se determina si la transacción es online (en una tienda web) o presencial (en un comercio físico usando Mercado Pago Point).
    - Si es online, el proceso se dirige a la pasarela de pago, donde se autentica al usuario y se valida el método de pago.
    - Si es presencial, se usa Mercado Pago Point, conectándose a un dispositivo móvil.
- Validación del Método de Pago: El flujo sigue según el método de pago elegido:
    - Tarjeta de Crédito/Débito: Se valida la tarjeta con el banco emisor.
    - Transferencia Bancaria: Se procesa la transferencia.
    - Efectivo: Se genera un código de pago que el usuario puede usar para pagar en un punto autorizado.
    - Mercado Crédito: Se valida si el usuario tiene crédito disponible.
- Procesamiento del Pago: Todos los métodos de pago llevan al mismo punto donde se autoriza la transacción.
- Confirmación del Pago: Si el pago es exitoso, el usuario y el comercio reciben una notificación. Si falla, se muestra un error.
- Opciones Post-pago: Se decide si se genera un recibo digital. Si se genera, se envía al usuario.
- Fin del Flujo: El proceso finaliza, ya sea tras el pago exitoso o un error de transacción.

## Diagrama de Secuencia
```mermaid
sequenceDiagram
    participant Usuario
    participant App/Plataforma
    participant PasarelaPago as Pasarela de Pago
    participant Autenticacion as Autenticación/Seguridad
    participant Validador as Validador de Pago
    participant Banco as Banco/Entidad Financiera
    participant MercadoCredito as Mercado Crédito
    participant Comercio
    participant Point as Mercado Pago Point
    participant Billetera as Billetera Digital
    participant Notificacion as Sistema de Notificación

    %% Flujo de interacción del usuario
    Usuario->>App/Plataforma: Acceder a la plataforma
    App/Plataforma->>PasarelaPago: Solicitar inicio de transacción
    PasarelaPago->>Autenticacion: Validar credenciales del usuario
    Autenticacion-->>PasarelaPago: Credenciales válidas

    %% Decisión de tipo de pago
    PasarelaPago->>Usuario: Mostrar opciones de pago
    Usuario->>PasarelaPago: Seleccionar método de pago

    %% Validación del método de pago
    PasarelaPago->>Validador: Validar el método de pago
    Validador->>Usuario: Solicitar detalles del pago (tarjeta, transferencia, etc.)
    Usuario-->>Validador: Enviar detalles de pago

    %% Opciones de validación de medios de pago
    alt Pago con Tarjeta de Crédito/Débito
        Validador->>Banco: Validar tarjeta con banco emisor
        Banco-->>Validador: Respuesta de validación
    end
    alt Pago con Transferencia Bancaria
        Validador->>Banco: Procesar transferencia
        Banco-->>Validador: Confirmar transferencia
    end
    alt Pago con Efectivo
        Validador->>PasarelaPago: Generar código de pago
        PasarelaPago-->>Usuario: Enviar código para pago en efectivo
    end
    alt Pago con Mercado Crédito
        Validador->>MercadoCredito: Validar crédito disponible
        MercadoCredito-->>Validador: Confirmar crédito disponible
    end
    alt Pago con Billetera Digital
        Validador->>Billetera: Verificar saldo en la billetera
        Billetera-->>Validador: Confirmar saldo disponible
    end

    %% Resultado de validación y procesamiento
    Validador-->>PasarelaPago: Confirmación de validación del pago
    PasarelaPago-->>Comercio: Notificar pago procesado
    Comercio-->>PasarelaPago: Confirmar recepción del pago

    %% Confirmación de transacción
    PasarelaPago->>Notificacion: Generar notificación de pago exitoso
    Notificacion-->>Usuario: Notificación de pago exitoso
    Notificacion-->>Comercio: Notificación de pago recibido

    %% Flujo de transacción presencial
    Usuario->>Point: Procesar pago presencial con Mercado Pago Point
    Point->>App/Plataforma: Conectar con la aplicación
    App/Plataforma->>Validador: Iniciar validación del pago presencial
    Validador->>Banco: Validar tarjeta o método de pago
    Banco-->>Validador: Confirmación de pago presencial
    Validador-->>Point: Confirmar transacción exitosa
    Point-->>Usuario: Notificar pago exitoso
```

#### Descripción del diagrama de secuencia:
- Usuario accede a la plataforma de Mercado Pago (a través de la app o navegador) y comienza una transacción.
- Pasarela de Pago se encarga de la comunicación inicial y valida las credenciales del usuario mediante el sistema de Autenticación/Seguridad.
- El usuario selecciona su método de pago (tarjeta, transferencia, efectivo, crédito, o billetera digital), y la Pasarela de Pago envía esta solicitud al Validador de Pago.
- Dependiendo del método de pago seleccionado:
    - Se valida con un Banco (tarjeta o transferencia),
    - Se genera un código de pago (efectivo),
    - Se valida el saldo de la Billetera Digital,
O se comprueba el crédito disponible mediante Mercado Crédito.
- El Validador de Pago confirma la transacción y notifica tanto al Comercio como al Usuario sobre el estado del pago.
- Si es una transacción presencial, el pago se realiza a través de Mercado Pago Point, que interactúa con la app y pasa por un proceso similar de validación de pago, conectando con los sistemas relevantes para verificar la transacción.
- El sistema de Notificación informa tanto al usuario como al comercio sobre el éxito de la transacción.

## Diagrama de Estados
```mermaid
stateDiagram-v2
    [*] --> InicioSesion : Usuario accede a la plataforma

    state InicioSesion {
        [*] --> VerificarCredenciales : Solicitar credenciales
        VerificarCredenciales --> CredencialesValidas : Credenciales correctas
        VerificarCredenciales --> CredencialesInvalidas : Credenciales incorrectas
        CredencialesInvalidas --> [*] : Terminar sesión
        CredencialesValidas --> SeleccionarMetodoPago
    }

    SeleccionarMetodoPago --> ValidarMetodo : Usuario selecciona método de pago

    state ValidarMetodo {
        [*] --> ValidarTarjeta : Tarjeta de Crédito/Débito
        ValidarTarjeta --> ConfirmarPago : Validar con Banco

        [*] --> ValidarTransferencia : Transferencia Bancaria
        ValidarTransferencia --> ConfirmarPago : Validar con Banco

        [*] --> GenerarCodigoEfectivo : Pago en Efectivo
        GenerarCodigoEfectivo --> ConfirmarPago : Generar código de pago

        [*] --> ValidarMercadoCredito : Mercado Crédito
        ValidarMercadoCredito --> ConfirmarPago : Validar crédito disponible

        [*] --> ValidarBilleteraDigital : Billetera Digital
        ValidarBilleteraDigital --> ConfirmarPago : Validar saldo disponible
    }

    ConfirmarPago --> PagoExitoso : Validación exitosa
    ConfirmarPago --> PagoFallido : Validación fallida

    PagoExitoso --> NotificarUsuario : Notificar a usuario
    PagoExitoso --> NotificarComercio : Notificar a comercio
    PagoFallido --> [*] : Mostrar error al usuario

    NotificarUsuario --> GenerarRecibo : Generar recibo digital
    GenerarRecibo --> Finalizar : Enviar recibo al usuario
    NotificarComercio --> Finalizar : Fin del proceso

    Finalizar --> [*] : Proceso completado
```

#### Explicación del diagrama de estados:
- Inicio del Estado: El diagrama comienza con el inicio de sesión del usuario en la plataforma de Mercado Pago. El sistema verifica las credenciales del usuario.
- Selección del Método de Pago: Una vez autenticado, el usuario selecciona un método de pago. El sistema pasa a la fase de validación del método.
- Validación de Métodos de Pago:
	- Si el usuario selecciona tarjeta de crédito/débito, el sistema valida con el banco.
	- Si selecciona transferencia bancaria, se verifica la transacción.
	- En el caso de efectivo, el sistema genera un código de pago.
	- Si es Mercado Crédito, se valida el crédito disponible.
	- Si se usa la billetera digital, se verifica el saldo disponible.
- Confirmación de Pago: Según los resultados de la validación del método de pago, el estado puede ir a:
	- Pago Exitoso, lo que desencadena la notificación al usuario y al comercio.
	- Pago Fallido, en cuyo caso se muestra un error y el proceso termina.
	- Notificación: En el caso de un pago exitoso, el sistema genera un recibo digital y lo envía al usuario, finalizando el proceso.
	- Finalización: Una vez que todas las partes han sido notificadas y el recibo ha sido enviado, el proceso se marca como completado.

Este diagrama de estados muestra el ciclo de vida de una transacción dentro de Mercado Pago, desde el inicio de sesión hasta la finalización, incluyendo la - selección y validación de métodos de pago, y las notificaciones correspondientes.