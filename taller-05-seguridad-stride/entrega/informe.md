# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
Taller 5: Evaluación de Seguridad con STRIDE

## 👥 Integrantes del equipo
- Juan David Cetina Gómez
- Ana Lucía Quintero Vargas
- Mariana Salas Gutiérrez

## 🧠 Descripción general del trabajo
Describa brevemente el objetivo del taller y cómo se desarrolló la actividad.

## 🔧 Proceso de desarrollo
Explique cómo realizaron el trabajo: qué decisiones tomaron, qué herramientas utilizaron, qué aspectos modelaron primero y cómo lo fueron ajustando.

## 🧩 Análisis del modelo propuesto
Incluya un análisis sobre:
- Cómo se estructura el modelo entregado
- Cómo representa las necesidades del cliente
- Qué supuestos se tomaron

## 📈 Diagrama final entregado
> (Inserte aquí una imagen o enlace al modelo-final.drawio / .asta / PDF)

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Ej: Paciente        | Actor | Usuario que agenda una cita médica | Cliente |

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
