# Política de privacidad de Wispkin

> Versión para la beta privada de Wispkin. Puede cambiar antes de la versión 1.0; te avisaremos de los cambios importantes.

Última actualización: 20 de octubre de 2026

## En pocas palabras

- **Wispkin no tiene servidores que reciban tus datos.** No hay cuentas, ni telemetría, ni analítica, ni publicidad.
- Todo lo que Wispkin guarda vive **en tu equipo**, en `%APPDATA%\wispkin`.
- Cuando conversas con una IA en la nube (por ejemplo, Claude), tu conversación viaja **directamente desde tu equipo al proveedor que elegiste**, con **tu propia clave**. Wispkin no la ve pasar por ningún servidor propio.
- Con Ollama, la conversación no sale de tu equipo (salvo que tú configures un servidor de Ollama en otra máquina).

## 1. Quién es el responsable

Wispkin es un proyecto independiente desarrollado por Wisplight Studio, nombre comercial de Mauricio Rodríguez Carballo (persona física), con domicilio en Mérida, Yucatán, México ("nosotros"). Contacto para privacidad: wispkin.app@gmail.com.

## 2. Qué guarda Wispkin en tu equipo

Todo está en la carpeta de datos de la app: `%APPDATA%\wispkin` (por ejemplo, `C:\Users\<tú>\AppData\Roaming\wispkin`).

| Qué | Archivo o carpeta | Para qué |
|---|---|---|
| Configuración del cerebro | `brain.json` | Qué proveedor y modelo usas y la dirección de Ollama. |
| Claves de API | `brain-secrets.json` | Tus claves, **cifradas con el cifrado de Windows (DPAPI)**: solo tu usuario de Windows en ese equipo puede descifrarlas. Si el cifrado del sistema no está disponible, Wispkin no guarda la clave. |
| Alma de Chispa | `soul.json`, `soul-settings.json` | Energía, humor, nivel, racha de días, logros y si el alma está encendida. |
| Posición de la ventana | `window-state.json` | Dónde dejaste al avatar en la pantalla. |
| Avatares | `avatars\` | Los avatares que importas (Codex Pets, Shimeji) o instalas. |
| Puente con Claude Code | `bridge\inbox\` | Avisos pequeños del mod y del servidor MCP de Wispkin. Se borran en cuanto la app los lee (o a los 60 segundos). |

Además, **cuando usas Claude**, el componente oficial de Anthropic que Wispkin usa para hablar con Claude (el Claude Agent SDK) guarda el historial de cada conversación en tu carpeta de usuario (`%USERPROFILE%\.claude\projects\`), igual que Claude Code. Eso es lo que permite "Abrir en Claude Code" y retomar la misma conversación.

Las conversaciones con Ollama se guardan solo en memoria y se pierden al cerrar la app.

**Cómo borrarlo todo:** cierra Wispkin (bandeja → *Salir*), desinstálalo y borra la carpeta `%APPDATA%\wispkin`. Si usaste Claude y quieres borrar también ese historial, borra las conversaciones correspondientes en `%USERPROFILE%\.claude\projects\` (ojo: ahí también están tus conversaciones de Claude Code, si lo usas).

## 3. Qué sale de tu equipo y hacia dónde

Wispkin **no envía nada a Wispkin**. Lo que sí sale de tu equipo:

| Hacia | Qué | Cuándo |
|---|---|---|
| **El proveedor de IA que eliges** (hoy: Anthropic para Claude) | Lo que escribes, los archivos y resultados de comandos que el asistente lee o produce con tu aprobación, y tu clave para identificarte. | Solo mientras conversas con ese proveedor. |
| **Ollama** (en tu equipo, `127.0.0.1`) | La conversación. | Mientras conversas con Ollama. Si cambias la dirección a otra máquina, Wispkin te pide confirmarlo, porque la conversación viajaría a ese servidor. |
| **GitHub** (solo en la versión de descarga directa) | Una consulta para saber si hay una versión nueva, y la descarga de la actualización. GitHub ve tu dirección IP y la versión, como con cualquier descarga. | Al abrir la app y de vez en cuando. |
| **Microsoft Store** (solo en la versión de la Store) | Lo que la Store use para instalar y actualizar, según la política de privacidad de Microsoft. | Lo gestiona Windows. |

Cada proveedor trata tus datos según **sus propias condiciones y su política de privacidad**, que aceptaste al crear tu cuenta y tu clave con él. Wispkin no controla lo que el proveedor hace con tus conversaciones (por ejemplo, cuánto tiempo las guarda o si las revisa por seguridad). Te recomendamos leerlas:

- Anthropic: [política de privacidad](https://www.anthropic.com/legal/privacy) y [condiciones comerciales (uso de la API)](https://www.anthropic.com/legal/commercial-terms)
- Ollama: [política de privacidad](https://ollama.com/privacy) (los modelos locales no envían tus mensajes a Ollama)

El componente oficial de Anthropic (Claude Agent SDK) podría enviar **datos técnicos de funcionamiento** (métricas de uso, informes de error, encuestas). **Wispkin los desactiva**: el componente solo habla con Anthropic para la conversación en sí, y se identifica como "wispkin". Wispkin no recibe ninguno de esos datos.

## 4. Lo que Wispkin no hace

- No tiene telemetría, analítica, píxeles de seguimiento, publicidad ni informes de fallos automáticos.
- No te pide crear una cuenta.
- No vende, comparte ni "entrena" nada con tus datos: no los recibe.
- No lee tus archivos por su cuenta. El asistente solo lee, edita o ejecuta algo en tu equipo cuando tú lo apruebas (ver los Términos de uso).
- El alma de Chispa (energía, humor, nivel) se calcula en tu equipo y no sale de él.

## 5. Si nos escribes o participas en la beta

Si nos escribes por correo, abres un reporte en GitHub o respondes las encuestas de la beta, recibimos lo que tú nos mandes: tu correo o tu usuario de GitHub, tu mensaje, capturas y, en las encuestas, tus respuestas.

- Lo usamos solo para responderte, arreglar fallos y mejorar Wispkin, y para darte el Pro gratis si participaste en la beta.
- Las encuestas se responden con Google Forms (Google), que trata los datos según su propia política: https://policies.google.com/privacy.
- Los reportes en GitHub son **públicos**: no pegues tu clave, rutas con tu nombre ni información privada.
- Puedes pedirnos que borremos lo que nos mandaste escribiendo a wispkin.app@gmail.com.

## 6. Menores de edad

Wispkin **no está dirigido a menores de 18 años**. Para usar Claude necesitas una clave de API de Anthropic, y sus condiciones exigen ser mayor de edad; con otros proveedores aplican sus propias condiciones. No recabamos a sabiendas datos de menores; si crees que un menor nos mandó datos, escríbenos y los borramos.

## 7. Seguridad

- Las claves se cifran con DPAPI y nunca llegan a la parte visual de la app; solo el proceso principal las usa.
- Wispkin borra tu clave de cualquier mensaje o registro antes de mostrarlo.
- Riesgo que debes conocer: si apruebas un comando que muestra las variables de entorno (por ejemplo `printenv` o `set`), el asistente podría ver tu clave de Claude. Por eso recomendamos **una clave solo para Wispkin, con límite de gasto**, y revisar cada comando antes de aprobarlo.

## 8. Tus derechos

Como Wispkin no guarda tus datos en servidores propios, tú tienes el control: puedes ver, copiar o borrar la carpeta `%APPDATA%\wispkin` cuando quieras. Para lo que nos hayas enviado (sección 5), puedes pedir acceso, corrección, borrado u oposición escribiendo a wispkin.app@gmail.com. Respondemos en un máximo de 20 días hábiles.

## 9. Cambios a esta política

Si cambia algo importante (por ejemplo, si algún día hubiera una función opcional que envíe datos a Wispkin), lo diremos en las notas de la versión y aquí **antes** de que ocurra, y será opcional. La fecha de arriba indica la última versión.

## 10. Contacto

wispkin.app@gmail.com · https://github.com/MauricioRodCar/wispkin-releases/issues
