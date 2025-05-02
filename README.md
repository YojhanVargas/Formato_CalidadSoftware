# Análisis de Calidad de Software

## Instrucciones y Preguntas
1. Analiza el fragmento de código original (`UserManagerOriginal.java`) y documenta al menos 5 problemas de calidad.
2. Para cada problema:
   - Explica por qué es un problema.
   - Cómo afecta a la calidad del software.
3. Propón una solución para cada problema.
4. Reescribe el código aplicando las mejoras propuestas.

---

## 1. Nombres crípticos e inespecíficos
- **Problema**: Métodos `a` y `p`, variable `u`.
- **Impacto**: Falta de legibilidad y mantenibilidad.
- **Solución**: Usar nombres descriptivos (`addUser`, `listUsers`, `username`).

## 2. Campos públicos y estáticos; falta de encapsulación
- **Problema**: `public static String[] users`, `public static int userCount`.
- **Impacto**: Pérdida de control sobre estado interno y problemas de concurrencia.
- **Solución**: Hacerlos `private`, usar `List<String>` y gestionar acceso.

## 3. Uso de tamaño fijo “10” (números mágicos)
- **Problema**: Límite codificado en varios lugares.
- **Impacto**: Difícil de cambiar requisitos y poco claro.
- **Solución**: Extraer a constante `MAX_USERS` o usar lista dinámica.

## 4. Mezcla de lógica de negocio con salida por consola
- **Problema**: `System.out.println` dentro de métodos.
- **Impacto**: Dificulta reutilización y pruebas unitarias.
- **Solución**: Quitar impresión, retornar resultados o usar logging.

## 5. Manejo de errores pobre y falta de validaciones adicionales
- **Problema**: Mensaje genérico `"Error"` y sin comprobación de duplicados.
- **Impacto**: Difícil diagnóstico y posibles inconsistencias.
- **Solución**: Lanzar excepciones específicas y validar duplicados.

---

## Código Original
Ver archivo `UserManagerOriginal.java`.

## Código Corregido
Ver archivo `UserManagerCorrected.java`.
