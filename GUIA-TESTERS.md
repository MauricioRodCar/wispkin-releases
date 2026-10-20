# Guía para testers de la beta privada de Wispkin

¡Gracias por probar Wispkin! Esta guía te lleva de la instalación a tu primer reporte en unos 15 minutos.

## Qué es Wispkin

Wispkin pone a tu asistente de IA en el escritorio, con cara: **Chispa**, un pequeño fuego fatuo azul. Flota sobre tus ventanas, reacciona a lo que hace la IA (pensar, trabajar, pedir permiso, terminar) y, al darle clic, abre un globo para conversar.

- Con **Claude** (tu propia clave de API), el asistente puede leer y editar archivos y ejecutar comandos en tu equipo, **siempre pidiéndote permiso antes**.
- Con **Ollama**, conversa con modelos que corren en tu PC, gratis y sin que nada salga de tu equipo. En esta versión solo conversa.
- Chispa tiene energía y humor, crece con las tareas que terminas y desbloquea variantes. Nunca enferma ni te culpa por no usarlo; si no lo usas, descansa.

Es una **beta**: algo va a fallar, y eso es justo lo que queremos encontrar contigo.

## Antes de empezar

- Windows 10 (1809 o posterior) u 11, de 64 bits.
- Para Claude: una cuenta en la consola de Anthropic con saldo y una clave de API. El uso se cobra a **tu** cuenta; una conversación normal cuesta céntimos, pero las tareas largas con archivos pueden costar más.
- Para Ollama: idealmente una tarjeta gráfica con 6–8 GB de VRAM o más. Sin GPU funciona, pero lento.
- Te recomendamos probar en una **carpeta de prueba** (o un proyecto con Git), no en tus documentos importantes.

## 1. Instalar

1. Descarga `Wispkin-Setup-0.1.0-beta.1.exe` del enlace que te enviamos (<https://github.com/MauricioRodCar/wispkin-releases/releases>).
2. Ábrelo. Como el instalador **todavía no está firmado** con un certificado, Windows mostrará un aviso azul: *"Windows protegió tu PC"*. Es esperable en una beta de un desarrollador independiente.
   - Haz clic en **Más información** y luego en **Ejecutar de todas formas**.
   - Si tu antivirus lo bloquea, cuéntanoslo en un reporte (con el nombre del antivirus).
   - Si prefieres comprobar el archivo: su SHA-256 está en las notas de la versión. En PowerShell: `Get-FileHash .\Wispkin-Setup-0.1.0-beta.1.exe`.
3. Al terminar, Chispa aparece en tu escritorio y un icono en la bandeja del sistema (junto al reloj; a veces dentro de la flecha `^`).

Wispkin se actualizará solo cuando publiquemos una versión nueva de la beta.

## 2. Elegir el cerebro

Dale clic a Chispa. La primera vez verás **"Elige tu cerebro"**.

### Opción A: Claude con tu clave

1. Entra en la consola de Anthropic ([console.anthropic.com](https://console.anthropic.com)) → *API Keys* → crea una clave **solo para Wispkin** (por ejemplo, llámala `wispkin-beta`).
2. **Pon un límite de gasto** en la consola (*Limits*), por ejemplo USD 5–10 al mes para la beta. Así, pase lo que pase, no te llevas sorpresas. Además, en Wispkin verás lo gastado hoy junto a la carpeta del globo, y puedes fijar un **tope diario** en ⚙ (tarjeta de Claude).
3. En Wispkin, elige **Claude**, pega la clave y pulsa **Usar Claude**.

Por qué una clave aparte: si en algún momento apruebas un comando que muestra las variables de entorno (como `set` o `printenv`), el asistente podría ver la clave. Con una clave dedicada y con límite, el riesgo queda acotado y puedes revocarla en un clic.

Tu clave se guarda cifrada con el cifrado de Windows, solo en tu equipo.

### Opción B: Ollama, gratis y local

1. Instala Ollama desde [ollama.com/download](https://ollama.com/download). Queda abierto en la bandeja.
2. Abre una terminal y descarga un modelo:
   - Con poca VRAM o sin GPU: `ollama pull llama3.2`
   - Con 8–12 GB de VRAM: `ollama pull qwen3:8b` o `ollama pull gemma3:12b` (este último responde muy bien en español)
3. En Wispkin, elige **Ollama** y el modelo, y pulsa **Usar Ollama**.

Si no eliges ninguno, Wispkin usa un **chat simulado** para que puedas ver el avatar y la interfaz igualmente.

## 3. Qué probar

No hace falta probarlo todo; lo que más nos ayuda es que **lo uses en tu día a día** y nos cuentes qué pasa.

**Lo básico**
- [ ] Arrastrar a Chispa por la pantalla; cerrar y abrir la app: ¿recuerda dónde estaba?
- [ ] Con varios monitores: moverlo de una pantalla a otra.
- [ ] El atajo **Ctrl+Alt+P** para abrir y cerrar el globo.
- [ ] La bandeja: Mostrar/Ocultar, **No molestar**, Avatar, Salir.
- [ ] Hacerle clic a Chispa varias veces y mirar cómo reacciona.

**Con Claude**
- [ ] Una pregunta normal: ¿el texto aparece poco a poco y Chispa cambia de estado?
- [ ] Pedirle algo con archivos, en una carpeta de prueba: "crea un archivo notas.txt con una lista de la compra". ¿Te pide permiso antes? ¿Se entiende qué va a hacer?
- [ ] Rechazar un permiso. Y probar "Aprobar siempre".
- [ ] Interrumpir una respuesta larga.
- [ ] El costo que se muestra al terminar cada respuesta: ¿coincide más o menos con tu consola?
- [ ] Si usas Claude Code: **Abrir en Claude Code** y seguir la misma conversación.

**Con Ollama**
- [ ] Una conversación de varios mensajes.
- [ ] Cerrar Ollama a mitad y ver qué dice Wispkin.

**El alma de Chispa**
- [ ] Abrir la ficha: nivel, energía, humor, logros.
- [ ] Usarlo varios días: ¿sube de nivel? ¿se desbloquean Brasa y Nebulosa?
- [ ] ¿Alguna vez te hizo sentir culpa, presión o que te "exigía" atención? **Esto es muy importante para nosotros: avísanos.**
- [ ] Apagar el alma con el interruptor.

**Avatares**
- [ ] Si tienes un Codex Pet o un Shimeji: bandeja → **Importar avatar…** y elegir su carpeta. (Usa avatares que tengas derecho a usar.)

**En tu equipo**
- [ ] ¿Cuánta CPU y memoria usa en reposo? (Administrador de tareas.)
- [ ] ¿Molesta en pantalla completa, en juegos o en videollamadas?

## 4. Cómo reportar

### Un fallo

Abre un *issue* en https://github.com/MauricioRodCar/wispkin-releases/issues o escríbenos a wispkin.app@gmail.com con esta plantilla. **Los issues son públicos: nunca pegues tu clave, y tapa rutas o nombres que no quieras mostrar.**

```markdown
**Qué pasó**
(Una o dos frases.)

**Qué esperabas que pasara**

**Pasos para repetirlo**
1.
2.
3.

**¿Pasa siempre?** Siempre / A veces / Solo una vez

**Cerebro:** Claude (modelo: ___) / Ollama (modelo: ___) / Simulado
**Versión de Wispkin:** 0.1.0-beta.1 (la del instalador que descargaste)
**Windows:** 10 / 11, versión ___
**Pantallas:** número y escala (100 %, 125 %, 150 %…)
**Antivirus:** (si aplica)

**Capturas o video**
(Si puedes. Revisa que no salga tu clave ni información privada.)
```

### Tu opinión

Una vez por semana, o cuando te apetezca, contesta este formulario corto (<https://forms.gle/bBhzJXpousYvmrnL9>):

1. Del 1 al 5, ¿qué tan útil te resultó Wispkin esta semana?
2. ¿Qué fue lo que más te gustó?
3. ¿Qué te molestó o te frustró?
4. ¿Qué le falta para que lo uses todos los días?
5. ¿Algo de Chispa te pareció pesado, insistente o culposo? (Sí / No; ¿qué?)
6. ¿Algo más?

Además, te escribiremos **a los 3 y a los 10 días** con una encuesta un poco más larga (5 minutos). Son las que más nos ayudan a decidir si Wispkin está listo.

## 5. Qué NO recogemos

- Wispkin **no tiene telemetría ni analítica**: no sabemos cuándo lo abres, qué le preguntas ni qué hace. Por eso tus reportes y encuestas son tan valiosos.
- Wispkin no tiene servidores propios: tu configuración, tu clave (cifrada) y el estado de Chispa viven en `%APPDATA%\wispkin`, en tu equipo.
- Tus conversaciones con Claude van directamente de tu equipo a Anthropic con tu clave; las de Ollama no salen de tu PC.
- Solo recibimos lo que tú nos envíes (reportes, encuestas, correos), y lo usamos para mejorar Wispkin y darte el Pro.

Detalles en la [política de privacidad](privacidad.md) y los [términos de uso](terminos.md).

## 6. Tu agradecimiento: Pro gratis para siempre

Cuando exista **Wispkin Pro** (panel grande, historial y varias conversaciones, más proveedores, personalización…), quienes participen en la beta lo tendrán **gratis y para siempre**. Para que cuente, basta con instalarlo y contestar al menos una de las encuestas de los días 3 y 10.

Lo esencial del asistente y la seguridad nunca serán de pago.

## Si quieres dejar la beta

Bandeja → **Salir**, desinstala Wispkin desde *Configuración → Aplicaciones* y, si quieres borrarlo todo, borra la carpeta `%APPDATA%\wispkin`. Revoca la clave de Wispkin en la consola de Anthropic. Y si nos cuentas por qué lo dejaste, nos ayudas muchísimo.

¡Gracias por acompañarnos! ✦
