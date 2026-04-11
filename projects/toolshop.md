---
layout: page
title: Framework de Automatización Toolshop
subtitle: E2E, UI & API Testing con Playwright y JavaScript
---

[⬅️ Volver a Proyectos](/projects)

---

## 📋 Información General

![Captura 1](/assets/img/toolshop/Toolshop site.png)
![Captura 2](/assets/img/toolshop/Toolshop site 2.png)
![Captura 3](/assets/img/toolshop/Toolshop site 3.png)

**Proyecto:** Framework de Automatización E2E/UI/API - Toolshop  
**Periodo:** Septiembre 2025 - Marzo 2026 (Completado - 100%)  
**Programa:** EPAM UpSkill - Specialization in Automated Testing with JavaScript  
**Repositorio:** [github.com/josgralagu/toolshop-automation-playwright](https://github.com/josgralagu/toolshop-automation-playwright)

---

## 🎯 Contexto y Objetivo del Proyecto

### El Problema

Durante mi especialización en EPAM, necesitaba desarrollar un framework de automatización profesional que cubriera:
- Testing end-to-end de una aplicación e-commerce completa
- Validación de APIs REST con esquemas robustos
- Código mantenible y escalable siguiendo mejores prácticas de la industria
- Reportes visuales y configurables para stakeholders

### El Objetivo

Crear un **framework integral y production-ready** que demuestre:
- Dominio de herramientas modernas de automatización (Playwright)
- Aplicación correcta de patrones de diseño (Page Object Model + Factory Pattern)
- Testing de API con validación de contratos (Joi schemas)
- Configuración profesional de código (ESLint, Prettier)
- Generación de reportes empresariales (Mochawesome)

---

## 🛠️ Stack Tecnológico Completo

### Core Testing
- **Playwright** - Framework principal para automatización UI
- **Mocha** - Test runner y framework de testing
- **Chai** - Biblioteca de assertions
- **Supertest** - Testing de API HTTP
- **Joi** - Validación de esquemas de API
- **Cucumber (BDD)** - Pruebas basadas en escenarios Gherkin

### Lenguaje y Patrones
- **JavaScript (ES Modules)** - Sintaxis moderna ES6+
- **TypeScript** - Tipado estático y mejor mantenibilidad
- **Page Object Model (POM)** - Patrón de diseño principal
- **Factory Pattern** - Para instanciación dinámica de page objects
- **Async/Await** - Manejo de promesas

### Code Quality & Tooling
- **ESLint** - Linter para mantener código consistente
- **Prettier** - Formateador automático de código
- **npm scripts** - 9 scripts personalizados para diferentes flujos

### CI/CD
- **Jenkins** - Pipeline de integración continua (implementado)

### Reporting
- **Mochawesome** - Reportes HTML interactivos
- **Spec Reporter** - Output detallado en consola
- **JSON Reporter** - Integración con CI/CD

---

## ⚙️ Arquitectura del Framework

### Estructura de Carpetas
```
toolshop-automation-playwright/
├── framework/
│   ├── pages/              # Page Objects (Login, Home, Cart, etc.)
│   ├── components/         # Componentes reutilizables (Header, Footer, Modals)
│   ├── api/                # Helpers para testing de API
│   ├── utils/              # Utilidades comunes
│   └── config/             # Configuraciones del framework
├── tests/
│   ├── ui/                 # 20 test suites para UI
│   │   ├── auth/          # Tests de autenticación
│   │   ├── cart/          # Tests de carrito
│   │   ├── checkout/      # Tests de checkout
│   │   ├── favorites/     # Tests de favoritos
│   │   ├── filters/       # Tests de filtros avanzados
│   │   └── profile/       # Tests de perfil de usuario
│   └── api/                # 7 test suites para API
│       └── booking/        # Tests CRUD de Booking API
├── reports/                # Reportes generados
├── test-results/          # Resultados de ejecución
└── config/                 # Configuraciones de Playwright
```

### Principios de Diseño Aplicados

1. **Separation of Concerns:** Separación clara entre lógica de test, page objects y configuración
2. **DRY (Don't Repeat Yourself):** Componentes reutilizables para evitar duplicación
3. **Single Responsibility:** Cada clase/módulo tiene una responsabilidad única
4. **Modularity:** Framework organizado en módulos independientes y reutilizables

---

## 🧪 Cobertura de Testing

### UI Testing (20 Test Suites)

| Área Funcional | Test Suites | Casos de Prueba | Características Probadas |
|----------------|-------------|-----------------|--------------------------|
| **Autenticación** | 3 | 15+ | Login, registro, logout, validaciones |
| **Carrito de Compras** | 4 | 20+ | Agregar/eliminar items, actualizar cantidades |
| **Checkout** | 3 | 12+ | Flujo de pago, validación de formularios |
| **Perfil de Usuario** | 3 | 10+ | Edición de perfil, cambio de contraseña |
| **Favoritos** | 2 | 8+ | Agregar/eliminar de favoritos |
| **Filtros y Búsqueda** | 3 | 15+ | Filtros por categoría, precio, marca |
| **Multilenguaje** | 2 | 6+ | Soporte 6 idiomas, traducciones |
| **Total UI** | **20** | **85+** | **~80% cobertura funcional** |

### API Testing (7 Test Suites)

| Endpoint | Métodos | Validaciones |
|----------|---------|--------------|
| **/booking** | GET, POST, PUT, DELETE | CRUD completo + validación de esquemas |
| **Auth** | POST | Autenticación y manejo de tokens |
| **Health Check** | GET | Disponibilidad del servicio |

**Validaciones con Joi:**
- ✅ Estructura de respuesta correcta
- ✅ Tipos de datos apropiados
- ✅ Campos obligatorios presentes
- ✅ Formato de fechas válido
- ✅ Status codes correctos (200, 201, 400, 404)

---

## 🚀 Implementación y Características Clave

### 1. Page Object Model Avanzado

**40+ funciones reutilizables** organizadas por página:
```javascript
// Ejemplo: LoginPage.js
class LoginPage {
  constructor(page) {
    this.page = page;
    this.emailInput = page.locator('#email');
    this.passwordInput = page.locator('#password');
    this.loginButton = page.locator('button[type="submit"]');
  }

  async login(email, password) {
    await this.emailInput.fill(email);
    await this.passwordInput.fill(password);
    await this.loginButton.click();
  }

  async verifyLoginSuccess() {
    await expect(this.page.locator('.user-menu')).toBeVisible();
  }
}
```

### 2. Factory Pattern para Page Objects

Instanciación dinámica y centralizada:
```javascript
// pageFactory.js
class PageFactory {
  static getPage(pageName, page) {
    const pages = {
      login: () => new LoginPage(page),
      home: () => new HomePage(page),
      cart: () => new CartPage(page)
    };
    return pages[pageName]();
  }
}
```

### 3. Testing de API con Validación de Esquemas
```javascript
// Ejemplo: API test con Joi
const bookingSchema = Joi.object({
  bookingid: Joi.number().required(),
  booking: Joi.object({
    firstname: Joi.string().required(),
    lastname: Joi.string().required(),
    totalprice: Joi.number().required()
  })
});

describe('Booking API Tests', () => {
  it('should create booking with valid schema', async () => {
    const response = await request(baseURL)
      .post('/booking')
      .send(bookingData);
    
    const { error } = bookingSchema.validate(response.body);
    expect(error).to.be.undefined;
  });
});
```

### 4. Ejecución Multi-navegador Paralela

Configuración en `playwright.config.js`:
```javascript
projects: [
  { name: 'chromium', use: { ...devices['Desktop Chrome'] } },
  { name: 'firefox', use: { ...devices['Desktop Firefox'] } },
  { name: 'webkit', use: { ...devices['Desktop Safari'] } }
]
```

**Resultado:** Tests ejecutados simultáneamente en 3 navegadores, reduciendo tiempo total.

### 5. Reporting Profesional con Mochawesome

Reportes HTML interactivos con:
- ✅ Gráficas de distribución de tests (passed/failed)
- ✅ Duración de cada test suite
- ✅ Stack traces detallados en fallos
- ✅ Screenshots automáticos en errores
- ✅ Filtrado por status (passed, failed, pending)

---

## 📊 Resultados y Métricas

### Estadísticas del Proyecto

| Métrica | Valor |
|---------|-------|
| **Total de Test Suites** | 27 (20 UI + 7 API) |
| **Total de Test Cases** | 120+ |
| **Cobertura Funcional** | ~80% de funcionalidad crítica |
| **Líneas de Código** | 3,500+ |
| **Funciones Reutilizables** | 40+ |
| **Tiempo de Ejecución** | ~8 min (paralelo en 3 navegadores) |
| **Tasa de Éxito** | 100% en entorno local |

### Code Quality

- ✅ **0 warnings** de ESLint después de configuración
- ✅ **Código formateado** automáticamente con Prettier
- ✅ **Commits organizados** con mensajes descriptivos
- ✅ **README completo** con instrucciones de instalación y uso

---

## 🎓 Aprendizajes Clave

### Técnicos

1. **Arquitectura Escalable**
   - Aprendí la importancia de planificar la estructura del framework desde el inicio
   - Un framework bien arquitecturado facilita el mantenimiento y la extensión

2. **Page Object Model Avanzado**
   - El factory pattern mejora significativamente la mantenibilidad
   - La modularización de componentes (header, footer, modals) reduce duplicación

3. **Async/Await Mastery**
   - Dominio del manejo correcto de promesas en Playwright
   - Comprensión profunda de esperas implícitas vs explícitas

4. **API Schema Validation**
   - Joi es extremadamente poderoso para prevenir regresiones en contratos de API
   - La validación de esquemas detecta cambios no documentados en el backend

5. **Code Quality desde el Inicio**
   - Implementar ESLint y Prettier desde el día 1 evita deuda técnica
   - Scripts npm bien organizados mejoran la productividad del equipo

### Profesionales

1. **Pensamiento en Producción**
   - No basta con que los tests funcionen, deben ser mantenibles
   - La documentación es tan importante como el código

2. **Colaboración**
   - Un framework bien estructurado facilita el trabajo en equipo
   - Los reportes visuales mejoran la comunicación con stakeholders

3. **Mejora Continua**
   - Refactorizar constantemente mejora la calidad del código
   - Cada test es una oportunidad para optimizar el framework

---

## 🔗 Enlaces y Recursos

- **📁 Repositorio Completo:** [github.com/josgralagu/toolshop-automation-playwright](https://github.com/josgralagu/toolshop-automation-playwright)
- **📄 README Detallado:** [Ver documentación](https://github.com/josgralagu/toolshop-automation-playwright#readme)
- **🎥 Demo en Video:** *(Próximamente)*

---

## 🚀 Próximos Pasos

Este framework está en constante evolución. Próximas mejoras planeadas:

- [x] **CI/CD con Jenkins (entorno local)** - Pipeline implementado y funcional
- [ ] **CI/CD con GitHub Actions** - Ejecución automática en cada push
- [ ] **Docker containerization** - Ambiente consistente para todos los desarrolladores
- [ ] **Visual regression testing** - Detección de cambios visuales con Playwright
- [ ] **Performance testing** - Integración con Lighthouse
- [ ] **Allure reporting** - Reportes aún más avanzados

---

[⬅️ Volver a Proyectos](/projects) | [Ver siguiente proyecto: Urban Scooter →](/projects/urban-scooter)

---

## 📬 ¿Preguntas sobre este proyecto?

Si quieres discutir detalles de implementación o mejores prácticas:

- 📧 **Email:** [josgralagu@hotmail.com](mailto:josgralagu@hotmail.com)
- 💼 **LinkedIn:** [linkedin.com/in/josegralagu](https://linkedin.com/in/josegralagu)
- 🐙 **GitHub:** [github.com/josgralagu](https://github.com/josgralagu)
