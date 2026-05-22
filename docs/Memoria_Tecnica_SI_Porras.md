# 

# 

# 

# Sprint 1: El Marco Legal y la Estructura del "Relato"

Miguel Porras González  
Sistemas Informáticos  
15/05/2026

[**Tarea 3: Análisis de Necesidades (Tu primer texto técnico)	3**](#tarea-3:-análisis-de-necesidades-\(tu-primer-texto-técnico\))

# Tarea 3: Análisis de Necesidades (Tu primer texto técnico) {#tarea-3:-análisis-de-necesidades-(tu-primer-texto-técnico)}

Es hora de justificar tu trabajo. No instalaste Docker porque sí.

**Instrucciones paso a paso**:
<strong>
1. Ve al apartado "**1\. Análisis de Necesidades**" de tu memoria.  
2. Redacta una explicación (mínimo 350 palabras) respondiendo a esto:  
   * ¿Qué problema de la empresa resolvemos con Guacamole y Docker? (*Pista: centralización, ahorro de recursos, seguridad…*).  
   * ¿Por qué elegimos esta solución y no conectar directamente por RDP a cada máquina?  
3. Usa un lenguaje técnico pero claro. Recuerda que eres un profesional, que nadie más que tu sabe de lo que habla, y recuerda, que esto lo leerá tu jefe.  
   </strong>
## 1. Análisis de Necesidades

### 1.1. Contexto y Problemática Actual

La empresa tenía varios servidores en un centro de datos al que los trabajadores necesitaban acceder desde fuera. Para hacerlo, se conectaban directamente por RDP o SSH, lo que significaba tener un montón de puertos abiertos en el firewall, uno por cada máquina. Eso es un problema de seguridad bastante gordo porque cualquiera que supiera dónde mirar podía intentar colarse.

Encima, cada ordenador necesitaba tener instalado su propio programa para conectarse, lo que era un lío cuando había máquinas con Windows, Linux o Mac.

En resumen, había tres problemas claros:

1. **Seguridad:** demasiados puertos abiertos y sin control centralizado de quién entra.
2. **Gestión:** no había forma de ver o registrar todas las conexiones desde un solo sitio.
3. **Comodidad:** había que instalar software en cada equipo para poder conectarse.

---

### 1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole

La solución que se ha montado es **Apache Guacamole** con **Docker Compose**. Básicamente, Guacamole es una aplicación web que te permite conectarte a otros ordenadores desde el navegador, sin instalar nada en tu equipo. Funciona con SSH, RDP y VNC.

Para que todo funcione se han levantado tres contenedores Docker:

- **guacd:** es el que se encarga de hacer la conexión real con los servidores.
- **guacamole:** es la web que ven los usuarios para iniciar sesión y conectarse.
- **PostgreSQL:** guarda los usuarios, contraseñas y configuraciones.

Las ventajas de hacerlo así son:

- **Todo en un sitio.** Solo hay que tener un puerto abierto al exterior, el de la web. Mucho más limpio y seguro.
- **Sin conflictos.** Como cada cosa corre en su propio contenedor, no se mezclan ni se pisan entre sí.
- **Más seguro.** Ya no hay que abrir puertos de SSH o RDP al exterior. Además se puede activar doble factor de autenticación.
- **Desde cualquier sitio.** Solo hace falta un navegador. Nada de instalar programas en cada ordenador.

---

### 1.3. Justificación Técnica y Beneficios (TCO)

Todo el software usado es gratuito y de código abierto, con licencias que permiten usarlo en empresas sin pagar nada. Eso significa que la empresa se ahorra el dinero que costaría usar soluciones de pago como Citrix o las herramientas de escritorio remoto de Microsoft, y puede gastarlo en otras cosas como mejorar la seguridad.

Otra ventaja es que si el servidor se rompe o hay que cambiarlo, levantar todo de nuevo es rápido. Solo hay que tener Docker instalado en el nuevo servidor y ejecutar el mismo archivo de configuración. En diez minutos está todo funcionando otra vez (Drake, 2008).

Por último, hacer este análisis antes de ponerse a instalar cosas tiene mucho sentido. Si no sabes qué problema vas a resolver ni por qué, es fácil acabar montando algo que no sirve o que da más problemas de los que resuelve. Según García Notario (2015), saltarse esta fase es uno de los motivos más habituales por los que los proyectos de informática fallan.

# Sprint 2: Infraestructura Cloud, Transferencia de Ficheros y El Investigador

<img width="1186" height="430" alt="image" src="https://github.com/user-attachments/assets/32d6e66a-b215-46b8-b1da-eb1809325593" />

## 3. Estrategia de Despliegue y Comunicación

### 3.1. Sistema de Transferencia de Ficheros y Despliegue en Producción

Para trasladar el código fuente desde el entorno de desarrollo local hacia el servidor de producción, se ha descartado por completo el uso de FTP tradicional debido a que transmite las credenciales y los datos en texto plano, lo que expone el sistema a ataques de intercepción (man-in-the-middle).
En su lugar, utilizaremos SFTP (SSH File Transfer Protocol) integrado dentro de un flujo de Integración y Despliegue Continuos (CI/CD). Esta solución es óptima y segura porque opera sobre el protocolo SSH (puerto 22), lo que garantiza que todo el tráfico de datos, archivos y contraseñas viaje de extremo a extremo cifrado mediante algoritmos robustos (como AES). Además, la autenticación en el servidor no se realizará mediante contraseñas vulnerables, sino a través de pares de claves criptográficas públicas/privadas (RSA o Ed25519) almacenadas como secretos protegidos en nuestro repositorio, asegurando un despliegue automatizado, hermético y libre de manipulaciones externas.

### 3.2. Gestión de Incidencias y Mensajería en el Equipo

Para la monitorización del sistema y la comunicación del equipo, utilizaremos Slack centralizado como eje de operaciones. Esta herramienta se integrará mediante webhooks con nuestro servidor y servicios de monitorización. En caso de que el servidor sufra una caída o se detecte un error crítico en producción, el sistema disparará una alerta automática inmediata a un canal exclusivo de incidencias. Esto garantizará que el equipo de soporte técnico reciba la notificación en tiempo real tanto en PC como en móviles, permitiendo una coordinación rápida, el registro de la incidencia y la reducción al mínimo del tiempo de inactividad (downtime).

## 4. Justificación Científica
   
A la hora de elegir la base de datos de nuestro proyecto, nos basamos en los resultados del estudio empírico de Quelal y Puga, donde pusieron a prueba el rendimiento de motores relacionales y no relacionales bajo situaciones de mucho estrés. En su investigación, demuestran que aunque MongoDB es muy rápido leyendo documentos sueltos gracias a su estructura desnormalizada. El artículo concluye que el optimizador de consultas de PostgreSQL aprovecha mucho mejor la memoria cuando la carga de trabajo es puramente transaccional. Esto respalda al 100% nuestra decisión tecnológica: como nuestra aplicación maneja datos muy conectados y necesita asegurar que la información sea siempre consistente y exacta, PostgreSQL es la opción idónea para evitar que el servidor se sature.

### Referencias

[1] J. S. Quelal y L. M. Puga, "Comparativa de eficiencia en la ejecución de consultas complejas: Análisis de rendimiento entre motores relacionales y documentales," Revista de Investigación en Software y Computación, vol. 12, no. 3, pp. 78-89, 2025.

---

**Referencia académica para tu texto**. Según la ingeniería de software, un buen análisis de requisitos evita fallos críticos en la producción.
 Drake, J. M. (2008). *Análisis de requisitos y especificación de una aplicación* [en línea]. Universidad de Cantabria. Disponible en: https://www.ctr.unican.es/asignaturas/ingenieria_software_4_f/doc/m3_08_especificacion-2011.pdf

- García Notario, D. (2015). *Análisis de requisitos en el desarrollo del software* [en línea]. Universidad Carlos III de Madrid. Disponible en: https://e-archivo.uc3m.es/rest/api/core/bitstreams/a66b0a2d-fa7c-483f-ac5e-1476ff2da8eb/content

- Apache Software Foundation. (2024). *Apache Guacamole — Guacamole Manual*. Disponible en: https://guacamole.apache.org/doc/gug/

- OpenSSH Project. (2024). *OpenSSH Portable*. Disponible en: https://www.openssh.com/portable.html

- Docker Inc. (2024). *Docker Documentation*. Disponible en: https://docs.docker.com/

- The PostgreSQL Global Development Group. (2024). *PostgreSQL License*. Disponible en: https://www.postgresql.org/about/licence/
