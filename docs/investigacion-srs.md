# Investigación sobre SRS/ERS

## Resumen

Un SRS, llamado ERS en español, es una **especificación de requisitos de software**. Es un documento que explica qué debe hacer un programa, qué límites tiene y cómo comprobar que cumple lo acordado. Ayuda a evitar malentendidos, funciones olvidadas y trabajo que después hay que rehacer. En nuestro videojuego del ODS 14 servirá para que el equipo tenga claro qué desarrollar y qué probar (IEEE, 1998).

El esquema de IEEE 830 organiza el documento en tres partes principales:

1. **Introducción:** explica el propósito, el alcance, los términos usados, las referencias y cómo está organizado el documento.
2. **Descripción general:** presenta el contexto del producto, sus funciones generales, los usuarios, las restricciones y los supuestos o dependencias.
3. **Requisitos específicos:** detalla las funciones, las interfaces, el rendimiento y otras condiciones que debe cumplir el software. Se pueden agregar anexos cuando hagan falta (IEEE, 1998).

Un buen requerimiento debe ser **correcto**: responder a una necesidad real; **no ambiguo**: entenderse de una sola manera; **completo**: incluir la información necesaria; **consistente**: no contradecir otros requisitos; **factible**: poder realizarse con los recursos disponibles; y **verificable**: permitir comprobar si se cumple (NASA, s. f.).

**Ejemplo malo:** “El juego debe cargar rápido”. No dice cuánto tiempo se permite ni cómo medirlo. **Ejemplo bueno:** “En la computadora de prueba acordada por el equipo, cada escena principal debe cargar en un máximo de 5 segundos”. Para comprobarlo, se registra la computadora y la versión del juego y se mide cada escena tres veces. Es un ejemplo propuesto; el equipo todavía debe confirmar que ese límite es viable.

Podemos usar el esquema de IEEE 830 o adaptarlo a fichas de requisitos. Para escribirlo sirven un editor de texto o el editor de GitHub; guardarlo en Markdown facilita revisar los cambios. GitHub permite crear, editar y subir estos archivos al repositorio mediante commits (GitHub, s. f.). **Elegimos una plantilla de tres secciones: Introducción, Descripción general y Requerimientos**, con fichas de ID, título, descripción, prioridad y criterio de aceptación. Es sencilla, cumple la actividad y permite relacionar cada RF con su Issue. IEEE 830 se usa como referencia histórica: fue sustituida por ISO/IEC/IEEE 29148:2011, según su ficha oficial (IEEE, s. f.).

## Referencias en APA 7

GitHub. (s. f.). *Managing files*. GitHub Docs. https://docs.github.com/en/repositories/working-with-files/managing-files

Institute of Electrical and Electronics Engineers. (1998). *IEEE recommended practice for software requirements specifications* (IEEE Std 830-1998). https://www.cse.chalmers.se/~feldt/courses/reqeng/papers/ieee_1998_std830_sw_req_spec.pdf

Institute of Electrical and Electronics Engineers. (s. f.). *IEEE 830-1998*. IEEE Standards Association. https://standards.ieee.org/ieee/830/1222/

National Aeronautics and Space Administration. (s. f.). *Appendix C: How to write a good requirement*. https://www.nasa.gov/reference/appendix-c-how-to-write-a-good-requirement/

## Uso de IA y revisión de fuentes

Se usó ChatGPT para organizar la investigación, simplificar la redacción y proponer ejemplos y criterios de aceptación. Las explicaciones se contrastaron con el esquema de IEEE 830, la guía de NASA y la documentación de GitHub.
