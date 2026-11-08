# Dependencias vulnerables de prueba

**Solo para probar escáneres de dependencias** (Dependency-Check, Trivy, npm audit).
Son versiones viejas de librerías populares con vulnerabilidades conocidas.

- **No ejecute `npm install`** acá ni use estas versiones en ningún sistema: los
  escáneres solo necesitan leer `package.json` y `package-lock.json`.
- El `package-lock.json` se generó con `npm install --package-lock-only --ignore-scripts`:
  sin descargar ni ejecutar el código de las librerías.

Resultado esperado de `npm audit --package-lock-only`: 19 paquetes vulnerables
(4 críticos, 11 altos, 1 medio y 3 bajos). Dependency-Check y Trivy informan cada CVE
por separado, así que van a mostrar más hallazgos que esa cuenta de paquetes.

| Librería | Versión | Ejemplos de vulnerabilidades |
|---|---|---|
| ejs | 3.1.6 | Inyección de plantillas con ejecución de código |
| handlebars | 4.5.3 | Ejecución de código y contaminación de prototipos |
| minimist | 1.2.0 | Contaminación de prototipos |
| axios | 0.21.0 | SSRF y ReDoS |
| express | 4.17.1 | Redirecciones abiertas y XSS (también trae qs, body-parser y path-to-regexp vulnerables) |
| jsonwebtoken | 8.5.1 | Validación débil de firmas y claves |
| lodash | 4.17.15 | Contaminación de prototipos e inyección de comandos |
| moment | 2.29.1 | Recorrido de rutas y ReDoS |
| node-fetch | 2.6.0 | Filtración de cabeceras a otro dominio |
| serialize-javascript | 2.1.1 | Ejecución de código |
| jquery | 3.4.1 | XSS |
| ws | 7.4.5 | ReDoS y denegación de servicio |
