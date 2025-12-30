---
layout: page
title: Proyecto Final Urban Scooter
subtitle: Testing Full-Cycle - Web, Móvil y API
---

[⬅️ Volver a Proyectos](/projects)

---

## 📋 Información General

**Proyecto:** Proyecto Final Integral - Urban Scooter  
**Periodo:** Noviembre 2025 - Diciembre 2025  
**Programa:** TripleTen Bootcamp - QA Engineer  
<!-- **Documentación:** [Ver en Google Sheets](https://docs.google.com/spreadsheets/d/1hcPTj0ihEfBKw27yNTDFU5dLAAQKUniR/edit?usp=sharing&ouid=114728704284228093213&rtpof=true&sd=true) -->

---

## 🎯 Contexto y Objetivo del Proyecto

### El Problema

Como proyecto final del bootcamp de QA Engineer en TripleTen, necesitaba demostrar dominio integral de:
- **Testing manual** con diseño de casos de prueba complejos
- **Testing web** multi-navegador y multi-resolución
- **Testing móvil** en Android (emulador y dispositivo real)
- **Testing de API** con validación exhaustiva
- **Gestión de defectos** en JIRA con evidencia profesional
- **Análisis de requisitos** con visualización de flujos complejos

### El Objetivo

Ejecutar un **proyecto full-cycle de QA** para Urban Scooter (aplicación de alquiler de scooters eléctricos) que demuestre:
- Capacidad de analizar requisitos complejos e identificar zonas grises
- Diseño de estrategias de prueba efectivas con técnicas de partición
- Ejecución de pruebas en múltiples plataformas y entornos
- Documentación profesional de defectos con reproducibilidad clara
- Pensamiento crítico sobre la viabilidad de release del producto

---

## 🛠️ Stack Tecnológico Completo

### Testing Web
- **Google Chrome** - Resolución 800x600
- **Mozilla Firefox** - Resolución 1920x1080
- **DevTools** - Inspección de elementos y debugging
- **Figma** - Análisis de diseños y comparación con implementación

### Testing Móvil
- **Android Studio** - Emulador Android
- **Dispositivo físico Android** - Testing en dispositivo real
- **Logcat** - Análisis de logs del sistema
- **ADB (Android Debug Bridge)** - Comandos para debugging

### Testing de API
- **Postman** - Cliente REST para testing de API
- **Apidoc** - Documentación de endpoints
- **JSON** - Formato de datos
- **cURL** - Testing de endpoints desde línea de comandos

### Análisis y Documentación
- **Draw.io** - Mapas mentales y diagramas de flujo
- **Google Sheets** - Casos de prueba y checklists
- **Google Docs** - Documentación de análisis
- **JIRA** - Gestión de defectos y tracking

### Bases de Datos
- **SQL** - Validación de datos en base de datos
- **PostgreSQL** - Motor de base de datos utilizado

---

## 📊 Estructura del Proyecto Final

### Tarea 1: Teoría de Testing (15% del proyecto)

Evaluación teórica cubriendo:
- Niveles de testing (unitarias, integración, sistema, aceptación)
- Tipos de testing (funcional, no funcional, caja negra, caja blanca)
- Ciclo de vida del bug
- Metodologías ágiles aplicadas a QA
- Técnicas de diseño de pruebas

**Resultado:** Demostración sólida de fundamentos teóricos de QA.

---

### Tarea 2: Testing Web - Urban Scooter (50% del proyecto)

#### Análisis de Requisitos

**Mapa Mental del Formulario de Pedido:**
- Visualización completa de la interfaz (elementos, campos, botones)
- Mapeo de funcionalidad (flujos, validaciones, interacciones)
- Identificación de **5+ zonas grises** críticas en requisitos:
  - Comportamiento no especificado para campos vacíos
  - Validaciones faltantes en formato de teléfono
  - Ambigüedad en mensajes de error
  - Falta de claridad en tiempos de timeout
  - Requisitos contradictorios entre diseño y documentación

#### Diseño de Pruebas

**Lista de Comprobación - Pantalla "Estado del Pedido":**
- 25+ validaciones de diseño (ortografía, layout, colores)
- 15+ validaciones de funcionalidad (transiciones, botones, modales)
- Pruebas en 2 entornos: Chrome 800x600 y Firefox 1920x1080

**Tabla de Validación - Pantalla "Hacer Pedido":**
- Aplicación de **partición de clases de equivalencia**
- **Análisis de valores límite** para campos numéricos
- 30+ casos de prueba (positivos y negativos)
- Validaciones de campos: nombre, apellido, dirección, teléfono, fecha

#### Ejecución de Pruebas

**Cobertura alcanzada:**

| Área Probada | Casos Diseñados | Casos Ejecutados | Bugs Encontrados |
|--------------|-----------------|------------------|------------------|
| Diseño UI | 40+ | 40 | 8 |
| Formulario de pedido | 30+ | 30 | 5 |
| Flujo de pago | 20+ | 20 | 3 |
| Estado del pedido | 15+ | 15 | 2 |
| **Total** | **105+** | **105** | **18** |

**Defectos críticos reportados:**
- 🐛 **Bug #1:** Botón "Confirmar" no se habilita con datos válidos (BLOCKER)
- 🐛 **Bug #2:** Campo teléfono acepta letras (CRÍTICO)
- 🐛 **Bug #3:** Modal de confirmación no se cierra correctamente (GRAVE)
- 🐛 **Bug #4:** Inconsistencia de colores entre Firefox y Chrome (MENOR)

---

### Tarea 3: Testing Móvil - Urban Scooter App (15% del proyecto)

#### Configuración del Entorno

**Android Studio Setup:**
- Emulador configurado: Pixel 6, Android 13 (API 33)
- Testing en dispositivo físico: Samsung Galaxy A52, Android 12
- Recolección de logs con Logcat
- Screenshots y screen recording para evidencia

#### Casos de Prueba Móviles

**Funcionalidades probadas:**

| Funcionalidad | Escenarios | Resultado |
|---------------|------------|-----------|
| Registro de usuario | 8 casos | ✅ 7 PASS, ❌ 1 FAIL |
| Login/Logout | 6 casos | ✅ 6 PASS |
| Búsqueda de scooters | 10 casos | ✅ 8 PASS, ❌ 2 FAIL |
| Alquiler de scooter | 12 casos | ✅ 10 PASS, ❌ 2 FAIL |
| Historial de viajes | 5 casos | ✅ 5 PASS |
| **Total** | **41** | **36 PASS (88%)** |

**Defectos específicos móviles:**
- 🐛 **Bug #M1:** App crashea al rotar pantalla durante alquiler (CRÍTICO)
- 🐛 **Bug #M2:** Mapa no carga en conexión lenta (GRAVE)
- 🐛 **Bug #M3:** Botón "Finalizar viaje" requiere múltiples taps (MENOR)

#### Análisis de Logs
```
// Ejemplo de log capturado - Crash al rotar pantalla
E/AndroidRuntime: FATAL EXCEPTION: main
    Process: com.urbanscooter.app, PID: 12345
    java.lang.NullPointerException: Attempt to invoke virtual method
    at com.urbanscooter.RentalActivity.onConfigurationChanged
```

---

### Tarea 4: Testing de API (20% del proyecto)

#### Análisis de Endpoints

**API de Urban Scooter probada:**

| Endpoint | Método | Funcionalidad | Casos de Prueba |
|----------|--------|---------------|-----------------|
| `/api/v1/users` | POST | Crear usuario | 8 |
| `/api/v1/auth/login` | POST | Login | 6 |
| `/api/v1/scooters` | GET | Listar scooters | 5 |
| `/api/v1/rentals` | POST | Iniciar alquiler | 10 |
| `/api/v1/rentals/{id}` | PUT | Finalizar alquiler | 7 |
| `/api/v1/rentals/{id}` | GET | Consultar alquiler | 5 |
| **Total** | - | - | **41** |

#### Técnicas de Testing Aplicadas

**Partición de Clases de Equivalencia:**
- Validación de formato de email (válido, inválido, vacío)
- Validación de longitud de contraseña (< 8, 8-20, > 20 caracteres)
- Validación de ID de scooter (existente, inexistente, formato inválido)

**Análisis de Valores Límite:**
- Duración de alquiler: 0 min, 1 min, 59 min, 60 min, 1440 min
- Precio: $0.00, $0.01, $999.99, $1000.00
- Radio de búsqueda: 0 km, 0.1 km, 5 km, 10 km, 50 km

#### Validaciones Realizadas

**Checklist de validación para cada endpoint:**
- ✅ Status code correcto (200, 201, 400, 404, 500)
- ✅ Estructura de respuesta según documentación
- ✅ Tipos de datos correctos (string, number, boolean)
- ✅ Campos obligatorios presentes
- ✅ Validaciones de negocio cumplidas
- ✅ Tiempos de respuesta aceptables (< 2 segundos)
- ✅ Manejo correcto de errores

**Defectos de API reportados:**
- 🐛 **Bug #A1:** POST /rentals retorna 200 en lugar de 201 (MENOR)
- 🐛 **Bug #A2:** GET /scooters no filtra por disponibilidad correctamente (GRAVE)
- 🐛 **Bug #A3:** Error 500 al enviar campo "duration" como string (CRÍTICO)

---

## 🎓 Aprendizajes Clave

### Técnicos

1. **Análisis de Requisitos**
   - Las zonas grises son comunes en requisitos del mundo real
   - Un buen QA debe identificarlas proactivamente y escalarlas
   - La visualización con mapas mentales ayuda a detectar inconsistencias

2. **Testing Multi-plataforma**
   - El mismo bug puede manifestarse diferente en web vs móvil
   - La resolución de pantalla impacta significativamente la UI
   - Los logs son esenciales para debugging en móvil

3. **Testing de API**
   - La documentación de API puede estar desactualizada
   - Validar status codes no es suficiente, hay que validar payloads completos
   - Postman collections facilitan regresión de API

4. **Gestión de Defectos**
   - Un bug bien documentado se resuelve más rápido
   - La evidencia multimedia (screenshots, videos, logs) es crucial
   - La severidad debe considerarse desde perspectiva de usuario y negocio

### Profesionales

1. **Pensamiento Crítico**
   - No todos los bugs bloquean un release
   - La priorización debe considerar impacto real en usuarios
   - A veces hay que recomendar "no lanzar" basado en evidencia

2. **Comunicación Efectiva**
   - Los reportes de testing deben ser claros para no-técnicos
   - Cuantificar resultados ayuda en toma de decisiones
   - Las conclusiones deben ser objetivas, no opiniones personales

3. **Gestión del Tiempo**
   - En proyectos con deadline ajustado, hay que priorizar pruebas críticas
   - No se puede probar todo - enfoque en flujos de negocio principales
   - Automatización ahorra tiempo en regresión (lección para futuros proyectos)

---

## 📊 Resumen Ejecutivo del Proyecto

### Estadísticas Finales

| Métrica | Valor |
|---------|-------|
| **Duración del proyecto** | 4 semanas |
| **Horas invertidas** | ~80 horas |
| **Casos de prueba diseñados** | 187 |
| **Casos de prueba ejecutados** | 187 |
| **Bugs encontrados** | 23 |
| **Bugs críticos/bloqueadores** | 5 |
| **Plataformas probadas** | 3 (Web, Móvil, API) |
| **Entornos de prueba** | 4 (2 navegadores + 2 dispositivos móviles) |

### Conclusión del Análisis

**¿Es viable lanzar Urban Scooter a producción?**

**Recomendación: NO lanzar en estado actual**

**Justificación:**
1. **Bugs bloqueadores pendientes:** 2 bugs críticos que impiden flujos principales
2. **Estabilidad móvil:** App crashea en escenario común (rotación de pantalla)
3. **Problemas de API:** Error 500 en endpoint crítico de alquiler
4. **Experiencia de usuario:** Inconsistencias entre navegadores afectan usabilidad

**Requisitos mínimos para release:**
- ✅ Resolver 5 bugs críticos/bloqueadores
- ✅ Ejecutar regresión completa después de fixes
- ✅ Validar estabilidad de app móvil con testing de estrés
- ✅ Confirmar que API maneja correctamente todos los edge cases

**Timeline recomendado:** 2 semanas adicionales de desarrollo + 1 semana de regresión.

---

## 🔗 Enlaces y Recursos

<!-- - **📄 Documentación Completa:** [Ver en Google Docs](https://docs.google.com/document/d/1lnPj-oKeF1fiQpKZ0rttDw1jGCRSCKNm/edit?usp=sharing) -->
<!-- - **🐛 Reporte de Bugs en JIRA:** *(Requiere acceso al proyecto)* -->
- **📊 Test Cases y Checklists:** [Ver en Google Sheets](https://docs.google.com/spreadsheets/d/1hcPTj0ihEfBKw27yNTDFU5dLAAQKUniR/edit?usp=sharing&ouid=114728704284228093213&rtpof=true&sd=true)

---

## 🎯 Impacto del Proyecto

Este proyecto final consolidó mi formación como QA Engineer al:

1. **Demostrar versatilidad:** Capacidad de probar web, móvil y API
2. **Aplicar metodologías:** Uso efectivo de técnicas de diseño de pruebas
3. **Pensar como negocio:** Recomendaciones basadas en impacto real
4. **Documentar profesionalmente:** Entregables listos para stakeholders
5. **Priorizar efectivamente:** Enfoque en lo crítico bajo presión de tiempo

---

[⬅️ Volver a Proyectos](/projects) | [Ver proyecto anterior: Toolshop ←](/projects/toolshop)

---

## 📬 ¿Preguntas sobre este proyecto?

Si quieres discutir estrategias de testing o enfoques de QA full-cycle:

- 📧 **Email:** [josgralagu@hotmail.com](mailto:josgralagu@hotmail.com)
- 💼 **LinkedIn:** [linkedin.com/in/josegralagu](https://linkedin.com/in/josegralagu)
- 🐙 **GitHub:** [github.com/josgralagu](https://github.com/josgralagu)
