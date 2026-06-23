# QA DevOps & AI Challenge - QA Store 🚀

## 📝 Descripción
Proyecto práctico que implementa un flujo completo de calidad (QA) para una aplicación web llamada **QA Store**. 
Incluye automatización en CI/CD, pruebas de performance, testing de sistemas con IA y documentación profesional 
como parte de un portafolio moderno de QA.

---

## 🎯 Objetivo
Construir un flujo completo de calidad aplicando buenas prácticas de:
- Control de versiones con Git y GitHub
- Automatización en CI/CD con GitHub Actions
- Quality Gates y DevSecOps
- Pruebas de performance (K6, JMeter)
- Testing de sistemas con Inteligencia Artificial
- Documentación profesional y uso responsable de IA

---

## 🛠️ Herramientas Utilizadas
- **Git & GitHub** - Control de versiones y colaboración
- **GitHub Actions** - Integración y entrega continua (CI/CD)
- **K6** - Performance testing y load testing
- **JMeter** - Pruebas de carga y stress testing
- **Node.js / Python** - Ejecución de scripts y pruebas
- **IA (ChatGPT/Claude)** - Apoyo en documentación y análisis

---

## 📁 Estructura del Proyecto

Repositorio de qa-devops-ai-challenge
qa-devops-ai-challenge/
├── performance/
│   ├── k6/
│   └── jmeter/
├── tests/
├── docs/
├── .github/
│   └── workflows/
├── .gitignore
└── README.md

---

## ⚙️ Instalación

### Requisitos previos
- Git instalado ([descargar](https://git-scm.com/))
- Node.js v16+ o Python 3.8+ ([descargar](https://nodejs.org/))
- Cuenta en GitHub

### Pasos

```bash
# 1️⃣ Clonar repositorio
git clone https://github.com/tu-usuario/qa-devops-ai-challenge.git
cd qa-devops-ai-challenge

# 2️⃣ Instalar dependencias (Node.js)
npm install

# 3️⃣ Ejecutar pruebas
npm test

# 4️⃣ (Opcional) Instalar K6
# macOS
brew install k6

# Windows (con Choco)
choco install k6

# Linux
sudo apt-get install k6
```

---

## 🚀 Uso Rápido

### Ejecutar pruebas locales
```bash
npm test
```

### Ejecutar K6 performance test
```bash
cd performance/k6
k6 run load-test.js
```

### Ver resultados del pipeline
1. Ve a tu repositorio en GitHub
2. Click en la pestaña **"Actions"**
3. Selecciona el último workflow
4. Descarga los artefactos

---

## 📊 Quality Gates Definidos

Estos son los criterios mínimos que **deben cumplirse** para aprobar un Pull Request:

- ✅ **Pruebas**: 100% de pruebas automatizadas pasan (0 fallos)
- ✅ **Performance**: Tiempo promedio < 500ms (p95 < 500ms)
- ✅ **Error Rate**: < 1% de errores en pruebas de carga
- ✅ **Seguridad**: 0 secretos expuestos en el código
- ✅ **Artefactos**: Evidencia generada y disponible

**Si algún Quality Gate falla → El PR es bloqueado ❌**

---

## 📋 Plan de Pruebas

Ver documento completo: [Test Plan](docs/test-plan.md)

### Casos de Prueba Principales
1. **Login** - Validar acceso de usuarios
2. **Búsqueda de productos** - Funcionalidad de búsqueda
3. **Carrito de compras** - Flujo de compra simulado
4. **Performance** - Tiempos de respuesta bajo carga
5. **IA Assistant** - Respuestas de asistente virtual

---

## 🤖 Testing de Sistemas con IA

Ver análisis completo: [AI Analysis](docs/ai-analysis.md)

Se evalúan 5 casos de prueba de un asistente de IA para:
- ✅ Relevancia de respuestas
- ✅ Coherencia
- ✅ Detección de alucinaciones
- ✅ Recomendaciones de mejora
- ✅ Uso responsable de IA

---

## 📈 Resultados de Pruebas

### K6 - Load Testing
- **Estado**: ✅ APROBADO
- **Usuarios máximos**: 10
- **Tiempo promedio**: < 500ms
- **Error rate**: < 1%
- Detalles: [performance-k6-results.md](docs/performance-k6-results.md)

### JMeter - Stress Testing
- **Estado**: ✅ APROBADO
- **Usuarios**: 20
- **Iteraciones**: 3
- **Tiempo máximo aceptable**: 500ms
- Detalles: [performance-jmeter-results.md](docs/performance-jmeter-results.md)

---

## 🔄 CI/CD Pipeline

### ¿Cómo funciona?

1. **Push a rama feature** → Se ejecutan pruebas automáticamente
2. **Pull Request** → Workflow de GitHub Actions se dispara
3. **Validaciones**:
   - ✅ Checkout del código
   - ✅ Instalar dependencias
   - ✅ Ejecutar pruebas
   - ✅ Generar reportes
   - ✅ Guardar artefactos
4. **Quality Gates** → Se verifica que todo cumpla criterios
5. **Aprobación** → Si todo OK, se puede mergear a `main`

Ver workflow: [.github/workflows/qa-pipeline.yml](.github/workflows/qa-pipeline.yml)

---

## 📚 Documentación

| Documento | Descripción |
|-----------|-------------|
| [Test Plan](docs/test-plan.md) | Plan de pruebas y Quality Gates definidos |
| [AI Analysis](docs/ai-analysis.md) | Testing de sistemas IA y uso responsable |
| [K6 Results](docs/performance-k6-results.md) | Resultados de pruebas de performance con K6 |
| [JMeter Results](docs/performance-jmeter-results.md) | Resultados de stress testing con JMeter |

---

## 👥 Colaboración

### Rama de trabajo
- Crea una rama: `git checkout -b feature/tu-feature`
- Haz commits descriptivos: `git commit -m "feat: descripción"`
- Push a GitHub: `git push origin feature/tu-feature`
- Crea Pull Request y espera aprobación

### Convención de commits
