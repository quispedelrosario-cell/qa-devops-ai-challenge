# Test Plan - QA Store

## 📋 Objetivo
Validar que la aplicación QA Store cumpla con estándares de calidad mínimos antes de permitir cambios en producción.

---

## 📊 Quality Gates Definidos

Los siguientes criterios **DEBEN cumplirse** para aprobar un Pull Request:

### 1️⃣ Pruebas Automatizadas
- **Criterio**: 100% de pruebas deben pasar
- **Umbral**: 0 fallos permitidos
- **Acción si falla**: ❌ BLOQUEAR Pull Request
- **Justificación**: Asegurar que el código no rompe funcionalidad existente

### 2️⃣ Performance
- **Criterio**: Tiempo promedio de respuesta
- **Umbral**: < 500ms promedio, p95 < 500ms
- **Acción si falla**: ❌ BLOQUEAR Pull Request
- **Justificación**: Mantener experiencia de usuario rápida

### 3️⃣ Error Rate en Pruebas de Carga
- **Criterio**: Porcentaje de errores bajo carga
- **Umbral**: < 1% de errores
- **Acción si falla**: ❌ BLOQUEAR Pull Request
- **Justificación**: Aplicación debe ser estable bajo carga

### 4️⃣ Seguridad Básica
- **Criterio**: No expongas secretos o credenciales
- **Umbral**: 0 secretos detectados
- **Acción si falla**: ❌ BLOQUEAR Pull Request
- **Justificación**: Proteger datos sensibles

### 5️⃣ Artefactos Generados
- **Criterio**: Evidencia y reportes disponibles
- **Umbral**: Mínimo reportes de pruebas
- **Acción si falla**: ⚠️ ADVERTENCIA (puede proceerse con aprobación)
- **Justificación**: Tener trazabilidad de ejecuciones

---

## 📋 Casos de Prueba Iniciales

### Caso 1: Login de Usuario
**Objetivo**: Validar que usuarios pueden iniciar sesión

- **Precondición**: Usuario existe en base de datos
- **Pasos**:
  1. Navegar a página de login
  2. Ingresar credenciales válidas
  3. Click en botón "Ingresar"
- **Resultado esperado**: Redirección a dashboard
- **Criterio de aceptación**: ✅ Login exitoso en < 500ms

---

### Caso 2: Búsqueda de Productos
**Objetivo**: Validar función de búsqueda

- **Precondición**: Base de datos con mínimo 5 productos
- **Pasos**:
  1. Navegar a sección productos
  2. Ingresar término de búsqueda
  3. Click en buscar
- **Resultado esperado**: Productos filtrados mostrados
- **Criterio de aceptación**: ✅ Búsqueda en < 300ms

---

### Caso 3: Agregar al Carrito
**Objetivo**: Validar que se puede agregar productos al carrito

- **Precondición**: Usuario autenticado, producto disponible
- **Pasos**:
  1. Seleccionar producto
  2. Click en "Agregar al carrito"
  3. Verificar carrito actualizado
- **Resultado esperado**: Producto agregado al carrito
- **Criterio de aceptación**: ✅ Acción completada en < 400ms

---

### Caso 4: Consulta de API
**Objetivo**: Validar que API responde correctamente

- **Precondición**: API disponible y accesible
- **Pasos**:
  1. Realizar GET request a `/api/products`
  2. Verificar status code 200
  3. Validar estructura de respuesta
- **Resultado esperado**: JSON válido con productos
- **Criterio de aceptación**: ✅ Status 200 en < 500ms

---

### Caso 5: Flujo de Compra
**Objetivo**: Validar flujo completo de compra

- **Precondición**: Usuario autenticado, carrito con productos
- **Pasos**:
  1. Ir a carrito
  2. Click en "Proceder al pago"
  3. Ingresar datos de envío
  4. Confirmar compra
- **Resultado esperado**: Compra completada, confirmación recibida
- **Criterio de aceptación**: ✅ Flujo completo en < 3 segundos

---

## 🔍 Métricas a Monitorear

| Métrica | Umbral | Herramienta |
|---------|--------|-------------|
| Pruebas pasadas | 100% | GitHub Actions |
| Tiempo respuesta | < 500ms | K6, JMeter |
| Error rate | < 1% | K6, JMeter |
| Secrets | 0 detectados | GitHub Actions |
| Coverage | > 70% | Jest/Pytest |

---

## ✅ Criterios de Aprobación

Un Pull Request **SOLO puede mergearse a main si**:

- ✅ Todos los Quality Gates se cumplen
- ✅ Mínimo 1 revisor aprueba
- ✅ No hay conflictos con main
- ✅ CI/CD pipeline PASA completamente
- ✅ Documentación está actualizada

---

## ❌ Motivos para RECHAZAR un PR

- ❌ Tests fallando
- ❌ Performance degradada
- ❌ Error rate > 1%
- ❌ Secretos expuestos
- ❌ Falta documentación
- ❌ Cambios sin pruebas

---

## 📅 Próximas Pruebas

- [ ] Día 3: K6 load testing
- [ ] Día 3: JMeter stress testing
- [ ] Día 3: AI system testing

---

**Última actualización**: 23 de Junio, 2026