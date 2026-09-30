# Tarea: Mi prompt avanzado 
 
## Tarea elegida 
Diseñar y estructurar un conjunto exhaustivo de casos de prueba para el módulo de registro de usuarios de una aplicación web, abarcando tanto flujos de éxito como validaciones de campos obligatorios, formatos de correo, seguridad de contraseñas y manejo de duplicados.

## Version 1: prompt basico 
 ```text
Diseña las clases para un sistema de notas de un colegio.
```

## Version 2 
  | Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) | 
|------|-----------------|-------------------------|-----------------------------------| 
| Zero-shot |5|Texto narrativo con viñetas y explicaciones detalladas|No| 
| One-shot |5|Lista estructurada con sintaxis|Si| 
| Few-shot |5|Línea por línea siguiendo la estructura|Si| 

## Version 3: prompt final 
| Parte del Prompt (Etiqueta / Bloque) | Contenido del Prompt | Técnica Aplicada | Qué aporta a la respuesta |
| :--- | :--- | :--- | :--- |
| Rol | `Actúa como analista de pruebas de software experto en Quality Assurance (QA).` | Role prompting | Establece un perfil profesional técnico para que la IA responda con vocabulario especializado de QA. |
| Contexto | `Sistema de registro de usuarios web que solicita nombre completo, correo electrónico y contraseña. Reglas de negocio: todos los campos son obligatorios, el correo debe tener sintaxis válida y no estar registrado previamente, la contraseña debe tener al menos 8 caracteres, un número y un carácter especial.` | Contextualización | Delimita las reglas del sistema para que los casos de prueba sean específicos a los requerimientos reales del formulario. |
| Ejemplos | `Ejemplo: ID: TC-REG-01 \| Escenario: Registro exitoso \| Resultado esperado: Usuario registrado y correo enviado.` | Few-shot | Proporciona un patrón o plantilla estandarizada para que la IA replique de forma exacta la sintaxis y el nivel de detalle deseado. |
| Tarea | `Piensa paso a paso en todos los posibles fallos del sistema y genera una tabla completa con al menos 8 casos de prueba.` | Chain of Thought + Descomposición | Fuerza al modelo a razonar la lógica de fallos paso a paso antes de listar los escenarios, garantizando que no olvide validaciones complejas. |
| Formato | `Presenta el resultado exclusivamente en una tabla con las columnas: ID, Escenario, Datos de Entrada, Resultado Esperado.` | Prompt estructurado | Define la presentación visual exacta para evitar texto explicativo innecesario y facilitar el copiado de datos. |
| Autocrítica | `Una vez generada la tabla, revísala críticamente y agrega casos de inyección de código o campos vacíos si faltasen.` | Autocrítica | Obliga a la IA a auditar su propio trabajo en una segunda pasada para detectar omisiones de seguridad o casos límite complejos. |
## Evaluacion del resultado 
| Criterio de Evaluación  | Cumple (Sí / No)  | 
|------|-----------------| 
| ¿El prompt final incluye un rol específico y un formato definido?  |Sí|
| ¿Contiene al menos tres técnicas avanzadas combinadas?  |Sí|
| ¿La tabla generada cuenta con las columnas solicitadas y casos límite?  |Sí|
| ¿Se evidencia el proceso de iteración desde la versión 1 hasta la versión 3?   |Sí|

## Por que elegi estas tecnicas 
Seleccioné esta combinación porque el registro de usuarios es una funcionalidad crítica en cualquier desarrollo web donde los errores de validación suelen pasar desapercibidos. El uso de Role prompting garantiza rigor técnico, mientras que el Prompt estructurado y Few-shot eliminan la dispersión y aseguran una estructura limpia apta para documentación. Añadir Chain of Thought y Autocrítica resulta indispensable en QA para forzar al modelo a pensar en escenarios de fallo complejos (como inyecciones o datos vacíos) que un enfoque superficial pasaría por alto.