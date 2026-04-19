# 💰 Natillera LA FORTUNA

> Sistema integral de gestión para natilleras familiares: aportes, préstamos, abonos, actividades y liquidación equitativa de fin de año.

![Versión](https://img.shields.io/badge/versión-12.0-c8a55b?style=flat-square)
![Estado](https://img.shields.io/badge/estado-producción-2d7a4a?style=flat-square)
![Licencia](https://img.shields.io/badge/licencia-Propietaria-0f1419?style=flat-square)
![Hecho en](https://img.shields.io/badge/hecho_en-Colombia_🇨🇴-yellow?style=flat-square)

**Desarrollada por [Vibras Positivas HM](https://vibraspositivashm.com)** — Derechos de Autor Reservados.

---

## 📖 Descripción

**Natillera LA FORTUNA** es una aplicación web de archivo único (single-file HTML) diseñada para que cualquier grupo familiar o comunitario lleve de forma ordenada, transparente y sin complicaciones técnicas toda la contabilidad de una natillera durante el año.

Permite registrar socios, ingresar aportes periódicos, otorgar préstamos a asociados y terceros, controlar abonos y cuotas, registrar actividades (ventas, rifas, eventos) y calcular automáticamente la liquidación de fin de año en partes iguales.

---

## ✨ Características principales

### 👥 Gestión de socios
- Registro con nombre, cédula y WhatsApp (validación a 10 dígitos sin +57).
- Edición y eliminación segura con confirmación.
- Prevención de cédulas duplicadas.
- Contador de aportes por socio en la tabla.

### 💵 Aportes
- Registro de aportes con fecha personalizable.
- **Constancia automática por WhatsApp** al socio con el formato oficial.
- Recibo imprimible en PDF (vía impresión nativa del navegador).
- Historial ordenado cronológicamente.

### 🏦 Préstamos
- Dos tipos de tasa: **5% mensual** para socios y **10% mensual** para externos.
- Plazos de 1 a 4 meses con cuotas iguales.
- Registro de codeudor/fiador.
- **Semáforo de estado**: al día (verde), por vencer (amarillo), en mora (rojo), cancelado (gris).
- **Plan de cuotas detallado** con fechas de vencimiento y estado individual.

### 📥 Abonos
- Registro con validación automática contra saldo.
- Recálculo instantáneo del saldo del préstamo.
- **Doble notificación WhatsApp**: al deudor (con saldo actualizado) y al administrador (copia).
- Confirmación si el abono supera el saldo pendiente.
- Recibo imprimible por cada abono.

### 🎉 Actividades
- Registro de ventas, rifas, bingos, bazares, etc.
- Cálculo automático de utilidad (ingreso − gasto).
- La utilidad se suma al fondo común de reparto.

### 🧮 Liquidación de fin de año
- Reparto automático **en partes iguales** entre socios.
- Fórmula: `Utilidad por socio = (Intereses causados + Utilidad actividades) ÷ N° socios`.
- Total a recibir por socio = aportes propios + utilidad equitativa.
- Tabla con totales al pie y exportable a Excel.

### ⚙️ Respaldo y seguridad
- **Copia de seguridad JSON** descargable con un clic.
- **Restauración** desde archivo JSON.
- Zona peligrosa con borrado total (doble confirmación).
- WhatsApp del administrador configurable para reportes y copias.

### 📱 Reporte mensual por WhatsApp
Genera y envía al administrador un resumen completo con un solo clic:
- Número de socios
- Aportes acumulados
- Préstamos activos
- Abonos recibidos
- Intereses causados
- Utilidad de actividades y total
- Utilidad por socio
- Saldo en caja

### 📊 Exportación a Excel
Informe completo con 7 hojas: Resumen, Liquidación, Socios, Aportes, Préstamos, Abonos, Actividades.

---

## 🚀 Instalación y uso

### Opción 1: Netlify (recomendada)
1. Descarga `index.html`.
2. Ve a [app.netlify.com/drop](https://app.netlify.com/drop).
3. Arrastra el archivo. Listo, en segundos tendrás tu URL pública.

### Opción 2: GitHub Pages
1. Clona este repositorio.
2. Activa GitHub Pages desde `Settings → Pages → Deploy from branch → main`.
3. Accede a `https://tu-usuario.github.io/nombre-del-repo/`.

### Opción 3: Uso local
Simplemente abre `index.html` con doble clic. Funciona sin servidor ni conexión a internet (excepto para el envío por WhatsApp).

---

## 🛠️ Stack técnico

| Componente | Tecnología |
|---|---|
| **Frontend** | HTML5, CSS3, JavaScript vanilla |
| **Persistencia** | `localStorage` del navegador |
| **Exportación Excel** | [SheetJS](https://sheetjs.com/) v0.20.1 (CDN) |
| **Tipografía** | Fraunces + Manrope (Google Fonts) |
| **Impresión PDF** | API de impresión nativa del navegador |
| **Notificaciones** | WhatsApp Web API (`wa.me`) |
| **Zona horaria** | `America/Bogota` (UTC-5) nativo |

**Sin dependencias de backend. Sin base de datos externa. Sin APIs de terceros (excepto CDN de SheetJS y Google Fonts).**

---

## 📂 Estructura del proyecto

```
natillera-la-fortuna/
├── index.html                         # Aplicación completa (single-file)
├── Manual_Natillera_LA_FORTUNA.docx   # Manual de usuario para la secretaria
└── README.md                          # Este archivo
```

---

## 🔐 Almacenamiento de datos

Todos los datos se guardan **localmente** en el navegador bajo la clave `laFortuna_v12` de `localStorage`. Esto significa:

✅ **Ventajas**
- Privacidad total: nada se envía a servidores externos.
- Funciona sin internet (excepto envío de WhatsApp).
- Sin costos de servidor ni base de datos.

⚠️ **Precauciones**
- Los datos están atados al navegador/dispositivo.
- Si se limpia la caché o se cambia de equipo, se pierden.
- **Por eso el respaldo JSON semanal es OBLIGATORIO.**

---

## 🧾 Ejemplo de mensaje de WhatsApp

### Al registrar un aporte:
```
*LA FORTUNA — RECIBO DE APORTE*

📝 Tipo: Aporte
🤝 Socio: María González
💰 Valor: $50.000
📅 Fecha: 19/04/2026

_Constancia generada por Natillera La Fortuna_
```

### Al registrar un abono:
```
*LA FORTUNA — RECIBO DE PAGO*

👤 Deudor: Juan Pérez
💸 Abono: $200.000
📉 Saldo: $375.000
📅 Fecha: 19/04/2026

_Constancia generada por Natillera La Fortuna_
```

---

## 📐 Fórmulas financieras

### Cálculo de préstamo
```
Interés total = Capital × Tasa mensual × Número de cuotas
Total a pagar = Capital + Interés total
Valor cuota   = Total a pagar ÷ Número de cuotas
```

### Saldo real en caja
```
Saldo = Aportes + Abonos recibidos + Ingresos actividades
      − Gastos actividades
      − Capital prestado pendiente de recuperar
```

### Interés causado
Por cada abono recibido, la parte proporcional que corresponde a interés:
```
Interés del abono = Monto abono × (Interés total préstamo ÷ Total a pagar)
```

### Liquidación equitativa
```
Utilidad total    = Intereses causados + Utilidad actividades
Utilidad por socio = Utilidad total ÷ Número de socios
Total socio        = Sus aportes + Utilidad por socio
```

---

## 🎨 Paleta de diseño

| Color | HEX | Uso |
|---|---|---|
| Dorado champán | `#c8a55b` | Acentos, marca, estados |
| Dorado profundo | `#a88640` | Firma, detalles |
| Tinta negra | `#0f1419` | Texto principal, botones |
| Crema fondo | `#faf8f2` | Fondo de la app |
| Verde | `#2d7a4a` | Estados positivos |
| Rojo | `#b23b3b` | Alertas, mora |
| Ámbar | `#d08c1a` | Advertencias |
| WhatsApp | `#25d366` | Botones de constancia |

**Tipografía:** Fraunces (display, serif) + Manrope (body, sans).

---

## 📋 Requisitos del navegador

- Chrome / Edge / Brave **96+**
- Firefox **95+**
- Safari **15+**
- Navegador del celular moderno (Android / iOS)

La app es **100% responsive** y se adapta a pantallas desde 320px.

---

## 🗺️ Roadmap

- [ ] PIN de acceso para la secretaria
- [ ] Gráfico de evolución de aportes por socio
- [ ] Préstamos con cuotas quincenales
- [ ] Envío automático de recordatorios de cuotas vencidas
- [ ] Importación masiva de socios desde CSV
- [ ] Soporte para múltiples natilleras en la misma instalación

---

## 📝 Changelog

### v12.0 — Abril 2026
- 🎨 Rediseño completo con paleta dorado/tinta y tipografía Fraunces + Manrope
- ✅ Bugs corregidos: `adminWA` indefinido, columnas desalineadas, aportes sin ID
- 🆕 Plan de cuotas detallado con estados individuales
- 🆕 Semáforo de mora en préstamos (verde/amarillo/rojo/gris)
- 🆕 Recibos imprimibles en PDF
- 🆕 Backup/Restore JSON completo
- 🆕 Reporte mensual por WhatsApp
- 🆕 Edición y borrado seguro con modales de confirmación
- 🆕 WhatsApp automático al socio en aportes y abonos
- 🆕 Copia automática al admin en cada abono
- 🆕 Saldo real considera capital prestado pendiente
- 🆕 Liquidación con totales al pie
- 🆕 Zona horaria `America/Bogota` en todo

### v11.0 (anterior)
- Versión base: socios, aportes, préstamos, abonos, actividades, Excel.

---

## 👨‍💻 Autor y soporte

**Harold Marín** — Vibras Positivas HM
📱 WhatsApp: [311 770 0431](https://wa.me/573117700431)
🌎 Caucasia, Antioquia — Colombia
🐙 GitHub: [@haroldco45](https://github.com/haroldco45)

---

## 📜 Licencia

Software propietario. © 2026 Vibras Positivas HM. Todos los derechos reservados.

Uso autorizado únicamente bajo licencia. Queda prohibida su redistribución, modificación o comercialización sin autorización expresa y por escrito del autor.

---

<div align="center">

**💰 Natillera LA FORTUNA**

*Ordenada. Transparente. Confiable.*

Desarrollada con ❤️ por **Vibras Positivas HM**

</div>
