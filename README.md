# Bitacora de prompts
 
Laboratorio 06: Fundamentos de Ingenieria de Prompts.
 
Herramienta de IA usada: (escribe aqui cual usaste)
 
## Ejercicio 2: Tokens y ventana de contexto
 | Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en Java. | 35 | 7 |
| The students program in Java. | 29 | 6 |
| desafortunadamente | 18 | 6 |

Al preguntar por TiendaTec en el mismo chat, la IA respondió correctamente porque los datos previos estaban dentro de su ventana de contexto. Al abrir un chat nuevo y hacer la misma pregunta, la IA no supo responder porque la ventana de contexto inició vacía y no tenía historial acumulado.

## Ejercicio 3: Temperatura
 | Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|-------------|----------------|---------------------------|
| 0 | 100.0% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 68.3% | BiblioTec, LibroYa, BiblioTec, PrestaLibro, BiblioTec |
| 1.0 | 44.0% | BiblioTec, PrestaLibro, LectoGo, BiblioTec, LectoGo |
| 1.8 | 32.1% | LectoGo, NubeDeTinta, PrestaLibro, BiblioTec, PaginaLibre |

Al subir la temperatura las probabilidades entre opciones se igualan, haciendo que las respuestas sean más variadas y creativas. El simulador nunca inventa un nombre nuevo porque la temperatura solo cambia la forma de seleccionar entre un arreglo fijo de opciones predefinidas, sin añadir nuevo conocimiento.

## Ejercicio 4: Prompt vago vs estructurado
 | Criterio | Prompt vago | Prompt estructurado |
|----------|-------------|---------------------|
| Menciona el objetivo del sistema | No | Sí |
| Menciona a los usuarios principales | No | Sí |
| Tiene exactamente 3 funcionalidades | No | Sí |
| Esta en 3 parrafos | No | Sí |
| Lo usaria en un informe real | No | Sí |

## Ejercicio 5: Anatomia de un prompt
 | Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java. |
| Instruccion | Crea un programa en Java para gestionar los productos de una tienda usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | Sistema de gestion de productos para una tienda local. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |

Cambios observados por nivel:
- Nivel 1: Generó un código básico genérico sin estructura definida.
- Nivel 2 (+Rol): Adoptó la perspectiva de un programador profesional mejorando las buenas prácticas.
- Nivel 3 (+Contexto): Centró el código específicamente en el dominio de una tienda comercial.
- Nivel 4 (+Instrucción): Agregó la clase Producto exacta con sus cuatro atributos requeridos.
- Nivel 5 (+Formato y Ejemplo): Organizó la respuesta separando la explicación textual del bloque de código y aplicando las convenciones de nombres indicadas.

## Ejercicio 6: Del prompt basico al profesional
### Tabla de Evaluación del Prompt Profesional

| Qué revisar | Cumple (Sí / No) |
| ----------- | ---------------- |
| ¿Está escrito en Java y usa Swing? | Sí |
| ¿Pide correo y contraseña? | Sí |
| ¿Explica el funcionamiento antes o después del código? | Sí |
| ¿El código está organizado en clases? | Sí |
| ¿Valida los datos que ingresa el usuario? | Sí (tras la interacción con JOptionPane) |

### Prompts Guardados

```text
Prompt Profesional:
Actua como desarrollador Java. Crea un ejemplo de login para una aplicacion de escritorio utilizando Swing. El usuario debe ingresar correo y contrasena. Explica brevemente el funcionamiento y presenta el codigo organizado por clases.

Prompt de Mejora (Iteracion):
Mejora el codigo anterior con estas restricciones: no uses librerias externas, valida que el correo contenga @ y que la contrasena tenga al menos 8 caracteres, y muestra los mensajes con JOptionPane.

- [Tarea: mi prompt profesional](prompts/TAREA.md)