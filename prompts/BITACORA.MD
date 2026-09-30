# Bitacora de tecnicas avanzadas 
 
Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: (escribe aqui cual usaste) 
 
## Ejercicio 2: Zero-shot, one-shot y few-shot 
 | Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) | 
|------|-----------------|-------------------------|-----------------------------------| 
| Zero-shot |5|Etiqueta + explicación entre ()|Si| 
| One-shot |5|Lista numerada con texto -> Etiqueta|Si| 
| Few-shot |5|Texto entre comillas -> Etiqueta|Si| 

## Ejercicio 3: Chain of Thought 
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) | 
|--------|--------------------|---------------------------|------------------| 
| Directo |318.60|No|Si| 
| Paso a paso |El cliente paga en total S/ 318.60.|Si|SI| 
 
## Ejercicio 4: Role prompting 
 | Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas | 
|---------|-------------------------------|-----------------------|---------------------| 
| A. Sin rol |Intermedio|Si|Principiantes| 
| B. Rol docente |Sencillo|SI|Principiantes y Estudiantes| 
| C. Rol senior |Tecnico|Si|Estudiantes y Programadores| 

## Ejercicio 5: Descomposicion 
-Paso 1: La IA entregó los 5 requisitos principales del sistema de inventario. 
    -> Comparación: El resultado cumplió exactamente con el pedido al listar de forma clara los requisitos solicitados.

-Paso 2: La IA entregó el diseño de las 5 clases necesarias con sus respectivos atributos y tipos de dato. 
    -> Comparación: El resultado se ajustó perfectamente a lo pedido, relacionando cada clase con los requisitos definidos previamente.

-Paso 3: La IA entregó el código Java de la clase Producto con sus atributos, un constructor y los métodos get y set. 
    -> Comparación: El resultado entregó exactamente el código estructurado en Java tal como fue solicitado.

-Paso 4: La IA entregó tres mejoras concretas para la clase Producto. 
    -> Comparación: El resultado cumplió con el pedido al proponer optimizaciones prácticas y orientadas a buenas prácticas de programación.
 
## Ejercicio 6: Prompt estructurado y autocritica 
 | Qué revisar  | Cumple (Sí / No)  | 
|------|-----------------| 
| ¿Tiene las 4 columnas pedidas?  |Sí|
| ¿Incluye el bloqueo después de 3 intentos?  |Sí|
| ¿Incluye casos con campos vacíos?  |Sí|
| ¿Indica qué casos agregó en la autocrítica?   |Sí|
| ¿Hay algún caso repetido o que no tenga sentido?   |No|

```text 
Prompt estructurado: 
<rol>Actua como analista de pruebas de software.</rol> 
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto> 
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea> 
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato> 

Autocritica:
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste. 
 ```