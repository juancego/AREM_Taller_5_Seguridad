# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
Taller 5: Evaluación de Seguridad con STRIDE

## 👥 Integrantes del equipo
- Juan David Cetina Gómez (juancego@unisabana.edu.co)
- Ana Lucía Quintero Vargas (anaquiva@unisabana.edu.co)
- Mariana Salas Gutiérrez (marianasalgu@unisabana.edu.co)

## 🧠 Descripción general del trabajo
Este informe tiene como objetivo analizar los riesgos de seguridad en una parte crítica del sistema usando el marco STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege). Como ejercicio introductorio se trabajó con un caso base (EdukIT, plataforma educativa virtual) para comprender la metodología, y luego se aplicó al cliente real (Zajana SAS), enfocado en el proceso de Fuentes de información y autorización. El análisis busca identificar amenazas, evaluar su nivel de riesgo y proponer controles de mitigación alineados con las necesidades del cliente.

## 🔧 Proceso de desarrollo
El punto de partida fue el diagrama BPMN previamente elaborado en draw.io, donde se representaron los actores principales: equipo de producto y responsable administrativo-financiero. A partir de este modelo se revisaron las actividades críticas del flujo, como el contacto inicial con la fuente prospecto, la elaboración del plan de negocio, la validación bajo gobierno de datos, la aprobación de oferta, la verificación documental y en listas restrictivas, y la firma del contrato.

Sobre esta base, se decidió aplicar el marco STRIDE y construir una tabla en Excel que documenta por cada paso las amenazas identificadas, el nivel de riesgo (alto, medio o bajo), el impacto potencial y los controles de mitigación. De esta manera, el análisis se centra en traducir el modelo de proceso en un instrumento práctico de seguridad.

## 🧩 Análisis del modelo propuesto
El análisis se sustenta en el proceso ya modelado y se expresa en la tabla Excel elaborada bajo STRIDE, lo que permite pasar de una visión descriptiva del flujo a una evaluación de riesgos de seguridad.

- **¿Cómo se estructura el modelo entregado?**
    El entregable es una tabla de análisis de seguridad, donde se registran amenazas STRIDE para cada tarea, junto con el nivel de riesgo, el impacto y los controles recomendados con su justificación. Esto permite priorizar acciones de seguridad de manera clara.

- **¿Cómo representa las necesidades del cliente?**
    Responde a la necesidad del cliente de reforzar la seguridad en un proceso clave que maneja información sensible y autorizaciones. Al ubicar riesgos en puntos como el contacto inicial, la verificación documental o la firma del contrato, se generan recomendaciones prácticas alineadas con políticas de cumplimiento y gobierno de datos.

- **¿Qué supuestos se tomaron?**
    Se asumió que la infraestructura tecnológica actual (en particular los servicios de Azure) garantiza trazabilidad y consistencia en la automatización del proceso. No obstante, se contemplaron riesgos como suplantación de identidades, manipulación de documentos o filtración de información en el intercambio de datos.

## 📈 Excel final entregado
![Tabla de STRIDE](./tabla-stride-cliente.png)

📋 **Tabla de actores, entidades o componentes – Caso Zajana**

| Nombre del elemento        | Tipo                       | Descripción                                                                 | Proveedor       |
|-----------------------------|----------------------------|-----------------------------------------------------------------------------|-------------------|
| Cliente                     | Actor                      | Usuario externo que accede al sistema para solicitar o consultar certificados e información financiera. | Cliente           |
| Dispositivos Zajana         | Actor / Dispositivo        | Equipos de la empresa Zajana desde los cuales acceden administradores y analistas. | Zajana            |
| Administrador Zajana        | Actor                      | Usuario interno con permisos avanzados de gestión y emisión de certificados. | Zajana            |
| Backend (Azure Web App)     | Componente (Aplicación)    | Lógica de negocio que procesa solicitudes de usuarios y gestiona la emisión de certificados. | Zajana            |
| Azure APIM (API Gateway)    | Componente (Infraestructura) | Punto central de acceso a las APIs, controla seguridad, validación de tokens y rate limiting. | Azure    |
| Azure Front Door + Firewall | Componente (Infraestructura) | Protección contra ataques DDoS y control de tráfico global, con reglas de firewall para acceso seguro. | Azure             |
| Cosmos DB y SQL Database    | Componente (Base de Datos) | Bases de datos que almacenan información financiera, usuarios y registros de certificados. | Azure            |
| Azure Storage               | Componente (Repositorio)   | Almacenamiento de documentos digitales y respaldos de certificados. | Azure            |
| VPN Gateway                 | Componente (Infraestructura) | Conexión segura entre dispositivos de Zajana y la nube. | Zajana            |
| Defender for Cloud          | Servicio de seguridad      | Supervisión y protección continua contra amenazas en la nube. | Azure             |
| Microsoft Authenticator     | Servicio de autenticación  | Provee MFA para proteger el acceso de usuarios internos y externos. | Azure  |
| Azure Sentinel              | Servicio de monitoreo      | Correlaciona eventos de seguridad y genera alertas de incidentes. | Azure    |

## 🔍 Investigación complementaria
### Tema investigado:
Principios de seguridad STRIDE

### Resumen:
El modelo STRIDE, según sus siglas, Tampering, Repudiation, Information Disclosure, Denial of Service y Elevation of Privilege, es un modelo encargado de clasificar las amenazas a la seguridad de un sistema en estas seis categorías [1]. El modelo fue desarrollado por Microsoft para identificar riesgos de seguridad informática [1]. STRIDE funciona vinculando cada tipo de amenaza a la violación de una propiedad de seguridad: la Suplantación compromete la Autenticidad, la Manipulación ataca la Integridad, el Repudio explota la falta de No repudio, la Divulgación de información afecta la Confidencialidad, la Denegación de servicio compromete la Disponibilidad, y la Elevación de privilegios se relaciona con la Autorización [1].

La aplicación de STRIDE se basa en la descomposición de la aplicación en componentes clave para conocer su arquitectura [2]. Un elemento bastante importante es el Diagrama de Flujo de Datos, que muestra los flujos de información entre los componentes de la aplicación [2]. Una vez que se tiene el DFD, se utiliza el método STRIDE para determinar las amenazas en cada componente de la aplicación [1][2], repitiendo el proceso hasta alcanzar una situación cómoda con las amenazas restantes [2]. El objetivo final es identificar las vulnerabilidades y planificar estrategias de mitigación [1].
## 📚 Referencias
- [1] STRIDE-based Threat Modeling for Cyber-Physical Systems - Queen's University Belfast
- [2] MODELADO DE AMENAZAS, UNA TÉCNICA DE ANÁLISIS Y GESTIÓN DE RIESGO ASOCIADO A SOFTWARE Y APLICACIONES. - Universidad Piloto de Colombia


---

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
