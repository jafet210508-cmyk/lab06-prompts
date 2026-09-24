# Tarea: Mi prompt profesional

## Funcionalidad elegida
Registro y gestión básica de productos para una tienda en Java Swing (CRUD básico).

## Version 1: prompt basico

` ` `text
Hazme un codigo para registrar productos.
` ` `

* **Qué cambié:** Es la consulta inicial sin especificar contexto, lenguaje ni formato.
* **Por qué:** Para evaluar la respuesta inicial de la IA de forma libre.
* **Qué mejoró / Resultado:** La respuesta entregó un código genérico en la consola sin interfaz gráfica y sin estructura definida.

## Version 2

` ` `text
Actua como desarrollador Java. Crea un formulario en Java Swing para registrar productos con los campos: Codigo, Nombre y Precio. Muestra el resultado organizado en clases.
` ` `

* **Qué cambié:** Se definió un rol (desarrollador Java), la tecnología (Java Swing), los campos exactos del formulario y la indicación de organizar por clases.
* **Por qué:** Para evitar que la IA elija un entorno web o de consola y asegurar el uso de Java Swing.
* **Qué mejoró:** El código generado incluyó una ventana funcional con etiquetas y cajas de texto, pero carecía de validación de datos de entrada y de mensajes de confirmación.

## Version 3: prompt final

` ` `text
Actua como un arquitecto de software senior especializado en Java. Redacta el codigo completo para un formulario de registro de productos en una aplicacion de escritorio usando Java Swing.

El formulario debe solicitar: Codigo de Producto, Nombre del Producto y Precio.

Aplica las siguientes restricciones estrictas:
1. No utilices librerias externas (solo componentes nativos de javax.swing y java.awt).
2. Valida que el Precio sea un numero decimal positivo mayor a cero.
3. Valida que el Codigo de Producto contenga al menos 4 caracteres.
4. Muestra los mensajes de confirmacion o error utilizando JOptionPane.showMessageDialog.

Estructura tu respuesta en dos partes:
1. Una breve explicacion de la estructura de las clases.
2. El codigo fuente completo y comentado.

Usa el siguiente estilo para los nombres de los metodos y atributos: getPrecio(), setPrecio(double precio), txtCodigo, txtNombre, txtPrecio y btnGuardar.
` ` `

* **Qué cambié:** Se especificó un rol senior, restricciones estrictas (validación numérica de precio, validación de código, no librerías externas), convención de nombres y un formato de salida de dos partes.
* **Por qué:** Para asegurar un código robusto, sin dependencias externas, con validaciones de entrada y estructurado profesionalmente.
* **Qué mejoró:** La respuesta entregó una explicación clara de la arquitectura seguida de un código en Java Swing listo para ejecutar, con validación de tipos de datos, manejo de excepciones (`NumberFormatException`) y alertas de diálogo con `JOptionPane`.

## Componentes del prompt final

| Componente | Texto exacto en mi prompt final |
|---|---|
| **Rol** | `Actua como un arquitecto de software senior especializado en Java.` |
| **Instrucción** | `Redacta el codigo completo para un formulario de registro de productos en una aplicacion de escritorio usando Java Swing.` |
| **Contexto** | `El formulario debe solicitar: Codigo de Producto, Nombre del Producto y Precio.` |
| **Ejemplo** | `Usa el siguiente estilo para los nombres de los metodos y atributos: getPrecio(), setPrecio(double precio), txtCodigo, txtNombre, txtPrecio y btnGuardar.` |
| **Formato** | `Aplica las siguientes restricciones estrictas: 1. No utilices librerias externas... 2. Valida que el Precio sea... 3. Valida que el Codigo... 4. Muestra los mensajes... Estructura tu respuesta en dos partes: 1. Una breve explicacion... 2. El codigo fuente...` |

## Evaluacion del resultado

| Criterio de Evaluación | Cumple (Sí / No) |
|---|:---:|
| ¿Está escrito en Java Swing sin utilizar librerías externas? | Sí |
| ¿Solicita los datos indicados (Código, Nombre y Precio)? | Sí |
| ¿Valida correctamente que el precio sea un número positivo y el código tenga al menos 4 caracteres? | Sí |
| ¿Muestra alertas con `JOptionPane` y sigue la estructura solicitada? | Sí |

## Errores que evite

1. **Ser demasiado general:** En la versión 1 no especifiqué el lenguaje de programación ni la plataforma (web/escritorio). Lo evité definiendo el rol de desarrollador Java y seleccionando explícitamente la librería Java Swing desde la versión 2.
2. **No indicar el formato ni dar contexto de validaciones:** En las primeras versiones la IA omitía validaciones de tipos de datos. Lo evité agregando en el prompt final una sección de restricciones explícitas donde ordené validar que el precio fuera decimal y mostrar errores con `JOptionPane`.