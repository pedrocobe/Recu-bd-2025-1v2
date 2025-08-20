# Recu-bd-2025-1v2

# Examen Final de Recuperación - Base de Datos 3B SOFTWARE

Este repositorio contiene el enunciado visual del examen final de recuperación. A partir de las capturas de pantalla presentadas (`rent.png` y `dashboard.png`), los estudiantes deberán diseñar e implementar completamente una base de datos relacional que soporte todas las funcionalidades de un **sistema de rentas de propiedades inmobiliarias**.

---

## 🏢 Contexto del Sistema

El sistema que debes desarrollar maneja **rentas de propiedades inmobiliarias** (apartamentos, casas, oficinas, etc.) con funcionalidades completas de gestión de inquilinos, propietarios, contratos de arrendamiento y reportes financieros.

---

## 🖼️ Interfaces Proporcionadas

![Registro de Renta](./src/rent.png)
*Formulario para registrar un nuevo contrato de arrendamiento de propiedad*

![Dashboard Gerencial](./src/dashboard.png)
*Panel de control con reportes y métricas clave del sistema inmobiliario*

---

## 🎯 Objetivo General

**Actúa como un desarrollador de software en un proyecto real.** A partir únicamente de las imágenes proporcionadas, debes:

1. **Interpretar las necesidades del negocio** analizando los formularios y reportes
2. **Diseñar una base de datos robusta** que soporte todas las funcionalidades visibles
3. **Implementar lógica de negocio completa** usando las mejores prácticas de SQL
4. **Crear un sistema seguro** con diferentes niveles de acceso
5. **Generar reportes analíticos** que alimenten las visualizaciones del dashboard

### 🔍 Metodología de Trabajo

1. **Analiza detalladamente cada imagen:**
   - ¿Qué campos aparecen en los formularios?
   - ¿Qué entidades puedes identificar?
   - ¿Qué relaciones existen entre los datos?
   - ¿Qué métricas se muestran en el dashboard?

2. **Infiere la lógica de negocio:**
   - ¿Cómo se relacionan inquilinos con propiedades?
   - ¿Qué estados pueden tener los contratos?
   - ¿Cómo se calculan los reportes financieros?

3. **Diseña considerando escalabilidad:**
   - Piensa en un sistema que maneje miles de propiedades
   - Considera diferentes tipos de usuarios del sistema
   - Planifica para reportes complejos de múltiples dimensiones

---

## 📋 Actividades Requeridas

### 1. **Modelo Relacional** (15%)
- **Identificar mínimo 6 entidades** basándote en los formularios y reportes
- **Entidades sugeridas a considerar:** Propiedades, Inquilinos, Propietarios, Contratos, Pagos, Tipos de Propiedad
- **Incluir:**
  - Nombres descriptivos de atributos
  - Tipos de datos apropiados (VARCHAR, DECIMAL, DATE, etc.)
  - Llaves primarias y foráneas
  - Restricciones (NOT NULL, UNIQUE, CHECK)
  - Relaciones 1:N y N:M según corresponda
- **Documentar:** Justificación de cada decisión de diseño

### 2. **Procedimientos Almacenados** (20%)
- **Implementar CRUD completo para 3 entidades principales**
- **Cada procedimiento debe:**
  - Recibir parámetros de entrada
  - Validar datos antes de INSERT/UPDATE
  - Verificar dependencias antes de DELETE
  - Manejar excepciones con mensajes informativos
  - Usar RAISE NOTICE para retroalimentación
- **Incluir procedimientos especiales:**
  - Renovación automática de contratos
  - Cálculo de multas por pagos tardíos
  - Liberación de propiedades al finalizar contrato

### 3. **Generación de Datos** (10%)
- **Insertar mínimo 1000 registros** distribuidos proporcionalmente
- **Usar funciones PostgreSQL:**
  - `generate_series()` para secuencias
  - `random()` para valores aleatorios
  - `date_trunc()` y `interval` para fechas
  - Arrays y `unnest()` para datos categóricos
- **Crear datos realistas:**
  - Nombres y apellidos variados
  - Direcciones coherentes
  - Rangos de precios por tipo de propiedad
  - Fechas de contratos distribuidas en los últimos 2 años

### 4. **Consultas SQL y Reportes** (20%)
**Basándote en los gráficos del dashboard, crear consultas para:**
- **Ingresos mensuales por tipo de propiedad**
- **Ocupación de propiedades por zona geográfica**
- **Top de inquilinos con mayor historial de pagos**
- **Análisis de morosidad por mes**
- **Propiedades más rentables del portafolio**

**Requisitos técnicos:**
- Uso de JOINs complejos (INNER, LEFT, RIGHT)
- Funciones de agregación (SUM, AVG, COUNT, MAX, MIN)
- GROUP BY con HAVING
- Subconsultas correlacionadas
- CASE WHEN para lógica condicional
- Funciones de ventana (ROW_NUMBER, RANK, LEAD/LAG)

### 5. **Vistas** (15%)
**Crear 3 vistas estratégicas:**
- **Vista operativa:** `v_contratos_activos` - Contratos vigentes con detalles completos
- **Vista financiera:** `v_ingresos_mensuales` - Resumen financiero por mes y tipo
- **Vista gerencial:** `v_dashboard_metricas` - KPIs principales para el dashboard

### 6. **Seguridad y Permisos** (10%)
**Crear roles diferenciados:**
- **`rol_gerente`:** Acceso completo a consultas y vistas
- **`rol_operador`:** Solo ejecución de procedimientos almacenados
- **`rol_inquilino`:** Acceso limitado a sus propios datos

### 7. **Documentación y Organización** (10%)
**Crear archivo `DOCUMENTACION.md` con:**
- Diagrama Entidad-Relación (puede ser textual)
- Justificación del modelo de datos
- Explicación de consultas complejas
- Manual de uso de procedimientos almacenados
- Casos de uso del sistema

---

## 📦 Estructura de Entrega (sugerida)

```
proyecto/
├── 01_modelo/
│   ├── tablas.sql
│   └── restricciones.sql
├── 02_procedimientos/
│   ├── crud_propiedades.sql
│   ├── crud_inquilinos.sql
│   └── crud_contratos.sql
├── 03_datos/
│   └── insercion_masiva.sql
├── 04_consultas/
│   └── reportes_dashboard.sql
├── 05_vistas/
│   └── vistas_negocio.sql
├── 06_seguridad/
│   └── usuarios_permisos.sql
├── DOCUMENTACION.md
└── script_completo.sql
```

---

## 🧠 Criterios de Evaluación

### Excelencia Técnica
- **Modelo normalizado** sin redundancias
- **Consultas optimizadas** con índices apropiados
- **Procedimientos robustos** con manejo de errores
- **Seguridad implementada** correctamente

### Razonamiento de Negocio
- **Interpretación correcta** de las interfaces visuales
- **Lógica de negocio coherente** con el dominio inmobiliario
- **Anticipación de casos de uso** no explícitos en las imágenes

### Profesionalismo
- **Código limpio** y bien documentado
- **Nombres descriptivos** en tablas y columnas
- **Organización clara** de archivos
- **Documentación completa** del proyecto

---

## ⚠️ Advertencias Importantes

1. **Trabajo Individual:** Cada solución debe ser única. Estructuras idénticas serán penalizadas.
2. **Análisis Visual:** Solo puedes basarte en las imágenes proporcionadas, no en especificaciones adicionales.
3. **Pensamiento Crítico:** Debes inferir funcionalidades que no son evidentes pero son necesarias.
4. **Calidad Profesional:** El código debe estar listo para un entorno de producción.

---

## 🚀 ¿Cómo Comenzar?

1. **Clona el repositorio:**
```bash
git clone [URL_del_repositorio]
cd Recu-bd-2025-1v2
```

2. **Examina las imágenes detenidamente:**
```bash
# Abre las imágenes en tu navegador para análisis detallado
"$BROWSER" src/rent.png
"$BROWSER" src/dashboard.png
```

3. **Crea tu estructura de trabajo:**
```bash
mkdir -p {01_modelo,02_procedimientos,03_datos,04_consultas,05_vistas,06_seguridad}
```

4. **Inicia con el modelo de datos** y avanza secuencialmente por cada módulo.

---

## ✨ Consejos para el Éxito

- **Piensa como un Product Manager:** ¿Qué funcionalidades necesita realmente un sistema inmobiliario?
- **Considera el ciclo de vida completo:** Desde que se publica una propiedad hasta que termina el contrato
- **Diseña para el futuro:** Tu base de datos debe soportar nuevos tipos de propiedades y servicios
- **Documenta tus decisiones:** Explica por qué elegiste cierta estructura o restricción

**¡El objetivo es demostrar que puedes desarrollar software de calidad profesional a partir de requisitos visuales!**

### ⚠️ Advertencia

No se aceptarán trabajos que presenten estructuras idénticas entre compañeros. Cada estudiante debe **modelar, justificar y ejecutar su solución individualmente**. Cualquier copia parcial o total será considerada plagio.

---

## ✅ Evaluación según rúbrica (100%)

| Criterio                           | Peso |
|------------------------------------|------|
| Modelo Relacional                  | 15%  |
| Procedimientos Almacenados (CRUD)  | 20%  |
| Generación de Datos Aleatorios     | 10%  |
| Consultas SQL y Reportes           | 20%  |
| Vistas                             | 15%  |
| Seguridad y Permisos               | 10%  |
| Documentación y Organización       | 10%  |

---

## 🛠️ ¿Cómo trabajar el examen?

Puedes clonar este repositorio para tener acceso a las imágenes:

```bash
git clone https://github.com/usuario/repositorio-examen-recuperacion.git
cd repositorio-examen-recuperacion