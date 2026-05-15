# UD07. Elaboración de documentación técnica y uso de aplicaciones de propósito general

## Sprint 1: El Marco Legal y la Estructura del "Relato"

* **Fecha:** 15 de mayo de 2026  
* **Modalidad**: individual

**RA7**. Elabora documentación valorando y utilizando aplicaciones informáticas de propósito general.

**CE**:

1) Se ha clasificado software en función de su licencia y propósito.  
2) Se han analizado las necesidades específicas de software asociadas al uso de sistemas informáticos en diferentes entornos productivos.

Tabla de contenidos

[**1\. El Reto de Hoy	1**](#1.-el-reto-de-hoy)

[**2\. Tarea 1: El Escudo Legal	1**](#2.-tarea-1:-el-escudo-legal)

[**3\. Tarea 2: La Memoria Técnica (Estructura Ofimática)	2**](#3.-tarea-2:-la-memoria-técnica-\(estructura-ofimática\))

[**4\. Tarea 3: Análisis de Necesidades (Tu primer texto técnico)	2**](#4.-tarea-3:-análisis-de-necesidades-\(tu-primer-texto-técnico\))

[**5\. ¿Cuándo he terminado? (Checklist de Salida)	3**](#5.-¿cuándo-he-terminado?-\(checklist-de-salida\))

[**ANEXO I: Plantilla y Ejemplo de Análisis de Necesidades	4**](#anexo-i:-plantilla-y-ejemplo-de-análisis-de-necesidades)

[1\. Análisis de Necesidades	4](#1.-análisis-de-necesidades)

[1.1. Contexto y Problemática Actual	4](#1.1.-contexto-y-problemática-actual)

[1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole	4](#1.2.-solución-propuesta:-infraestructura-híbrida-docker-guacamole)

[1.3. Justificación Técnica y Beneficios (TCO)	4](#1.3.-justificación-técnica-y-beneficios-\(tco\))

# 1\. El Reto de Hoy {#1.-el-reto-de-hoy}

La semana pasada fuisteis técnicos: montasteis contenedores, configurasteis SSH y pusisteis en marcha Guacamole. **Hoy vais a empezar a ser profesionales**. La diferencia es sencilla: un técnico hace que funcione; un profesional sabe explicar por qué funciona, bajo qué ley opera y lo deja documentado para que el siguiente no pierda el tiempo.

Hoy trabajaremos sobre vuestro repositorio de la **Bitácora 4** para convertirlo en el inicio de vuestro Proyecto Final de Documentación.

# 2\. Tarea 1: El Escudo Legal {#2.-tarea-1:-el-escudo-legal}

(El archivo LICENSES.md)

No podemos usar software en una empresa sin saber si es legal hacerlo. Y no, "es gratis" no es una categoría legal.

**Instrucciones paso a paso**:

1. Entra en la carpeta raíz de tu repositorio de la Bitácora 4\.  
2. Crea un nuevo archivo llamado LICENSES.md.  
3. Investiga y redacta en ese archivo qué licencia tiene cada pieza de tu infraestructura. Para cada una, debes indicar el nombre del software, su licencia y un enlace a la fuente oficial.  
   1. **Ejemplo**: *PostgreSQL se distribuye bajo la Licencia PostgreSQL (una licencia permisiva de tipo open source similar a la BSD o MIT)*.  
4. Debes incluir **obligatoriamente**: Apache Guacamole y OpenSSH.

**¿Por qué hacemos esto?** Porque según el CE a), debes ser capaz de clasificar el software según su propósito y su licencia.

# 3\. Tarea 2: La Memoria Técnica (Estructura Ofimática) {#3.-tarea-2:-la-memoria-técnica-(estructura-ofimática)}

Vamos a crear el documento donde contaréis vuestra "hazaña" técnica. No vale un documento plano; queremos nivel profesional.

**Instrucciones paso a paso**:

1. En tu repositorio, crea una carpeta llamada docs.  
2. Abre tu procesador de textos (Google Docs) y crea un archivo llamado Memoria\_Tecnica\_SI\_Apellido.md  
3. **Configura el esqueleto**:  
   * **Portada**. Título del proyecto, tu nombre, ciclo y fecha.  
   * **Índice Automático**. No lo escribas a mano. Usa la herramienta de "Tabla de contenidos".  
   * **Jerarquía de títulos**. Configura el "Título 1" para las secciones principales y el "Título 2" para los apartados; el “Título 3”, sólo si lo consideras necesario.  
4. Guarda el archivo dentro de la carpeta docs de tu repositorio (mientras lo terminas puedes utilizar Google Drive).

# 4\. Tarea 3: Análisis de Necesidades (Tu primer texto técnico) {#4.-tarea-3:-análisis-de-necesidades-(tu-primer-texto-técnico)}

Es hora de justificar tu trabajo. No instalaste Docker porque sí.

**Instrucciones paso a paso**:

1. Ve al apartado "**1\. Análisis de Necesidades**" de tu memoria.  
2. Redacta una explicación (mínimo 350 palabras) respondiendo a esto:  
   * ¿Qué problema de la empresa resolvemos con Guacamole y Docker? (*Pista: centralización, ahorro de recursos, seguridad…*).  
   * ¿Por qué elegimos esta solución y no conectar directamente por RDP a cada máquina?  
3. Usa un lenguaje técnico pero claro. Recuerda que eres un profesional, que nadie más que tu sabe de lo que habla, y recuerda, que esto lo leerá tu jefe.

**Referencia académica para tu texto**. Según la ingeniería de software, un buen análisis de requisitos evita fallos críticos en la producción.

# 5\. ¿Cuándo he terminado? (Checklist de Salida) {#5.-¿cuándo-he-terminado?-(checklist-de-salida)}

Antes de irte de clase, asegúrate de que tu repositorio en GitHub tiene:

- [ ] El archivo LICENSES.md con las licencias identificadas.  
- [ ] La carpeta docs con tu memoria técnica inicializada.  
- [ ] El índice de la memoria funcionando y el análisis de necesidades redactado.  
- [ ] Has hecho un ***Commit*** con el mensaje: feat: Sprint 1 completado \- UD07.  
- [ ] Has entregado la actividad en Classroom, recuerda que seguirás trabajando en el repositorio, así que, ¿Qué más da si la entregas?

# ANEXO I: Plantilla y Ejemplo de Análisis de Necesidades {#anexo-i:-plantilla-y-ejemplo-de-análisis-de-necesidades}

*Este documento es una guía. No debes copiar el texto palabra por palabra, sino usarlo como base para redactar tu propia justificación técnica basándote en lo que hiciste en el laboratorio.*

## 1\. Análisis de Necesidades {#1.-análisis-de-necesidades}

### 1.1. Contexto y Problemática Actual {#1.1.-contexto-y-problemática-actual}

**\[Instrucción: Explica en qué situación se encuentra la empresa antes de tu intervención\]**

La empresa objeto de este proyecto, una startup de desarrollo multiplataforma, requería que sus técnicos accedieran a servidores de bases de datos y desarrollo ubicados en un centro de datos remoto. La situación inicial presentaba riesgos de seguridad críticos, ya que se dependía de la apertura de múltiples puertos en el firewall para protocolos RDP y SSH directos, lo que aumentaba la superficie de ataque del sistema.

### 1.2. Solución Propuesta: Infraestructura Híbrida Docker-Guacamole {#1.2.-solución-propuesta:-infraestructura-híbrida-docker-guacamole}

**\[Instrucción: Describe qué has montado y por qué esa tecnología exacta\]** 

Tras analizar los requerimientos de accesibilidad y seguridad (RA6), se ha optado por implementar una solución basada en **Apache Guacamole** desplegada mediante **Docker Compose**. Esta arquitectura permite:

* **Centralización**. Un único punto de acceso vía web (puerto 8080/443) para todos los servicios internos.  
* **Aislamiento**. Gracias a los contenedores, cada servicio (PostgreSQL, Guacamole, SSH) opera en su propio entorno estanco, evitando conflictos de dependencias.  
* **Seguridad**. Se elimina la necesidad de clientes externos pesados, permitiendo una auditoría centralizada de las conexiones.

### 1.3. Justificación Técnica y Beneficios (TCO) {#1.3.-justificación-técnica-y-beneficios-(tco)}

**\[Instrucción: Convence al lector de que tu solución es rentable y profesional\]**

La elección de esta solución responde a la necesidad de optimizar el **Coste Total de Propiedad (TCO)**. Al utilizar software bajo licencias permisivas (Apache y PostgreSQL License), la empresa evita costes de licenciamiento recurrentes, pudiendo reinvertir ese capital en la seguridad de la infraestructura.

Además, la portabilidad que ofrece Docker garantiza que el tiempo de recuperación ante desastres (DRP) sea mínimo, cumpliendo con los requisitos no funcionales de disponibilidad que todo sistema informático profesional debe garantizar.

**Consejos para tu redacción**:

1. **Habla en tercera persona**. Evita el "yo he puesto" o "nosotros hemos hecho". Usa "se ha implementado", "se observa", "la solución permite".  
2. **Usa conectores**. Palabras como "*por consiguiente*", "*en consecuencia*", "*asimismo*" o "*no obstante*" le dan a tu texto un aire de ingeniero que te va a venir muy bien en el futuro.  
3. **Cita siempre (IEEE)**. Si dices que el software libre es mejor, di quién lo apoya o en qué norma se basa.

**Buenos ejemplos**:

* Drake, J. M. (2008). **Análisis de requisitos y especificación de una aplicación** \[en línea\] Disponible en: https://www.ctr.unican.es/asignaturas/ingenieria\_software\_4\_f/doc/m3\_08\_especificacion-2011.pdf  
* García Notario, D. (2015). **Análisis de requisitos en el desarrollo del software**  \[en línea\] Disponible en: https://e-archivo.uc3m.es/rest/api/core/bitstreams/a66b0a2d-fa7c-483f-ac5e-1476ff2da8eb/content