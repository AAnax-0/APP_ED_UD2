# README - Proyecto de Desarrollo de Software: FoodieMatch

> **Asignatura:** Entorno de Desarrollo 
> **Alumno/a:** Alvaro Gonzalez Medina 
> **Enlace al repositorio:** [URL de este repositorio de GitHub]  
> **Enlace a la presentación (Vídeo):** [Enlace a YouTube - Público / Oculto]  

---

## 1. Selección de la aplicación

Para este proyecto he elegido el desarrollo de **FoodieMatch**, una aplicación inteligente de gestión de despensa y planificación de menús semanales enfocada en reducir el desperdicio de alimentos en los hogares.

### Justificación teórica
* **Modelo de Desarrollo Ágil (Scrum/Kanban):** La elección de un modelo ágil es idónea para este proyecto porque la aplicación requiere validar rápidamente el valor que aporta al usuario final mediante un Producto Mínimo Viable (MVP). Dado que las necesidades de los usuarios en la gestión del hogar pueden cambiar y es fundamental iterar según el *feedback* (por ejemplo, incorporando sugerencias de recetas o integraciones con supermercados), el desarrollo incremental nos permite lanzar versiones funcionales desde las primeras fases del ciclo de vida del software.
* **Identificación de Usuarios Principales:** Siguiendo los principios de análisis de usuarios vistos en clase, la aplicación responde a un perfil heterogéneo pero bien definido: desde jóvenes estudiantes que buscan ahorrar hasta familias con poco tiempo para planificar comidas. Diseñar considerando estos roles desde la fase de análisis inicial evita desviaciones en el alcance del proyecto.

---

## 2. Listado de características

A continuación se enumeran 10 funcionalidades clave de la aplicación, clasificadas de forma preliminar en Requisitos Funcionales (**RF**) y Requisitos No Funcionales (**RNF**):

1. **Gestión de inventario de despensa (RF):** Permite registrar, modificar y eliminar alimentos con sus fechas de caducidad.
2. **Generación automática de recetas (RF):** Sugiere platos combinando exclusivamente los ingredientes disponibles en la despensa.
3. **Planificador semanal de menús (RF):** Organiza desayunos, comidas y cenas en un calendario interactivo.
4. **Lista de la compra automatizada (RF):** Añade automáticamente los ingredientes faltantes al planificar un menú.
5. **Notificaciones de caducidad (RF):** Envia alertas push al dispositivo cuando un alimento esté próximo a caducar.
6. **Autenticación e inicio de sesión seguro (RF):** Permite el registro mediante correo electrónico, Google o Apple ID.
7. **Rendimiento de búsqueda (RNF):** El buscador de recetas debe devolver resultados en menos de 1,5 segundos.
8. **Seguridad y privacidad de datos (RNF):** Cifrado de credenciales de usuario y cumplimiento del Reglamento General de Protección de Datos (RGPD).
9. **Usabilidad accesible (RNF):** Interfaz intuitiva y limpia, apta para usuarios con baja experiencia tecnológica.
10. **Disponibilidad del sistema (RNF):** El servicio web y las API deben garantizar un *uptime* mínimo del 99,5%.

---

## 3. Documentación inicial

* **Nombre de la aplicación:** FoodieMatch
* **Descripción breve:** Aplicación móvil y web para el control de inventario de alimentos domésticos, generación de menús personalizados basados en existencias y reducción del desperdicio de comida.
* **Objetivos (Problema que resuelve):**
  * Resolver la falta de organización en la compra de alimentos que genera gasto económico innecesario.
  * Disminuir el desperdicio de comida en el hogar aprovechando los ingredientes antes de su caducidad.
  * Facilitar la planificación nutricional diaria a personas con poco tiempo.
* **Usuarios principales (Roles):**
  * **Usuario Estándar:** Planifica las comidas de su hogar y gestiona su despensa.
  * **Usuario Premium:** Accede a planes nutricionales avanzados y estadísticas de ahorro.
  * **Administrador del Sistema:** Gestiona la base de datos global de recetas, modera contenidos y supervisa métricas del servicio.
* **Plataforma/s:**
  * **Móvil (Android / iOS):** Mediante desarrollo multiplataforma (Flutter / React Native).
  * **Web:** Panel de administración y versión accesible de la app.
* **Modelo de desarrollo sugerido:** **Modelo Ágil (Scrum)**.
  * *Justificación:* Permite trabajar en sprints cortos (2 semanas), entregando valor continuo (un MVP inicial con inventario y notificaciones, agregando progresivamente recetas e integraciones). Reduce el riesgo del proyecto al permitir adaptar los requisitos en función de las pruebas de usabilidad reales.

---

## 4. Análisis de requisitos

### Requisitos Funcionales (RF)

1. **RF1 - Registro y gestión de la despensa:** El usuario debe poder dar de alta productos escaneando el código de barras o introduciéndolos manualmente con su fecha de caducidad.
   * *Importancia:* Es el requisito núcleo de la aplicación; sin la toma de datos de los alimentos no es posible ejecutar las funciones avanzadas del sistema.
2. **RF2 - Algoritmo de recomendación de recetas:** El sistema debe cruzar los ingredientes disponibles con la base de datos de recetas para ofrecer alternativas ordenadas por caducidad próxima.
   * *Importancia:* Aporta la propuesta de valor diferencial al usuario, conectando directamente el inventario con una solución práctica e inmediata.
3. **RF3 - Generación de lista de la compra dinámica:** La app debe generar automáticamente la lista de ingredientes faltantes en función de las recetas seleccionadas para el menú semanal.
   * *Importancia:* Evita errores humanos en la planificación y ahorra tiempo al usuario en el proceso de compra.
4. **RF4 - Sistema de alertas de caducidad:** El sistema enviará notificaciones push configurables (ej. 3 días antes) informando sobre productos en riesgo de caducar.
   * *Importancia:* Es la funcionalidad directa para cumplir el objetivo de negocio: reducir el desperdicio de alimentos.
5. **RF5 - Gestión de roles y perfiles de usuario:** El sistema debe diferenciar el acceso y permisos entre un Usuario Estándar, un Usuario Premium y un Administrador.
   * *Importancia:* Garantiza el control de acceso y permite estructurar el modelo de negocio o monetización del software.

### Requisitos No Funcionales (RNF)

1. **RNF1 - Usabilidad (Facilidad de uso):** La interfaz debe requerir un máximo de 3 clics o toques para realizar cualquier tarea principal (añadir producto, ver menú del día).
   * *Importancia:* Como se vio en clase, la usabilidad es crucial cuando el público objetivo incluye usuarios novatos o con poca paciencia digital; una curva de aprendizaje alta provocaría el abandono de la app.
2. **RNF2 - Seguridad y Protección de Datos:** Las contraseñas se almacenarán mediante cifrado fuerte (BCrypt/Argon2) y los datos personales cumplirán con la normativa RGPD.
   * *Importancia:* La seguridad es un pilar fundamental para proteger la privacidad de los usuarios y evitar sanciones legales por filtración de datos sensibles.
3. **RNF3 - Rendimiento y Tiempo de Respuesta:** La API backend debe responder a las peticiones del cliente en un tiempo promedio inferior a 200 ms con una carga normal de usuarios.
   * *Importancia:* Un rendimiento deficiente degrada la experiencia de usuario (QoE) y puede provocar una percepción de mala calidad del software.
4. **RNF4 - Portabilidad y Multiplataforma:** La aplicación móvil debe ejecutar con el mismo código fuente en Android (versión 8.0 o superior) e iOS (versión 14 o superior).
   * *Importancia:* Maximiza el alcance del mercado reduciendo los costes de mantenimiento y desarrollo de código nativo por separado.
5. **RNF5 - Escalabilidad y Disponibilidad:** La arquitectura backend estará desplegada en servicios Cloud con autoescalado para soportar un incremento del 300% de usuarios simultáneos en horas punta sin caída del servicio.
   * *Importancia:* Asegura la continuidad de negocio durante picos de tráfico (por ejemplo, a la hora de preparar la cena).

---

## 5. Entrega en GitHub y presentación

* **Repositorio de GitHub:** `https://github.com/tu-usuario/FoodieMatch`
* **Vídeo de presentación en YouTube:** `https://www.youtube.com/watch?v=ejemplo` *(Asegúrate de ajustar la privacidad a Público u Oculto)*

* **Palabra del dia:** 29