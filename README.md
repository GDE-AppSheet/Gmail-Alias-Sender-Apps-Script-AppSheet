# Gmail Alias Sender (Apps Script)

Pequeño utilitario de **Google Apps Script** para:
- Listar los alias disponibles en tu cuenta de Gmail.
- Enviar correos **desde** un alias validando antes que exista en **Enviar como**.

> ⚠️ Este repositorio NO incluye correos reales ni nombres personales. Usa *placeholders* (`alias@tu-dominio.com`, `destinatario@ejemplo.com`, `Tu Equipo`).

## Características

- ✅ `listAliases()` — imprime y retorna todos los alias configurados en tu cuenta.
- ✅ `sendFromAliasIfAvailable(...)` — envía un correo desde un alias si está disponible; lanza error si no.
- ✅ `canSendFrom(alias)` — helper para validación rápida.
- 🧪 `__test_sendFromAlias()` — función de prueba opcional con *placeholders*.

## Requisitos

1. **Alias configurado en Gmail**  
   Gmail → ⚙️ Configuración → **Cuentas e importación** → *Enviar correo como* → Agregar otra dirección de correo.  
   Debe quedar verificado para poder usarlo.

2. **Apps Script (GmailApp)**  
   Este proyecto usa `GmailApp` (no necesitas habilitar APIs avanzadas).

3. **Permisos / Scopes**  
   Al ejecutar por primera vez, Apps Script solicitará los permisos típicos de Gmail:
   - `https://www.googleapis.com/auth/gmail.send`
   - `https://www.googleapis.com/auth/gmail.readonly` *(implícito para leer alias)*

## Instalación

### Opción A: Editor de Apps Script (rápido)
1. Ve a [script.google.com](https://script.google.com) y crea un proyecto nuevo.
2. Crea el archivo `Code.gs` y pega el contenido del repositorio.
3. Guarda.

### Opción B: `clasp` (opcional)
Si gestionas el código con Git:
```bash
npm i -g @google/clasp
clasp login
clasp create --title "gmail-alias-sender" --type standalone
# Copia Code.gs
clasp push
