<div align="center">

# 🛡️ Security Gatekeeper

### Tu última línea de defensa antes de pulsar "publicar".

**Una skill gratuita para Claude que audita tu proyecto como lo haría un atacante y te dice con claridad si es seguro lanzarlo: GO o NO-GO.**

![Licencia: Apache-2.0](https://img.shields.io/badge/licencia-Apache--2.0-blue) ![Precio: Gratis](https://img.shields.io/badge/precio-gratis-brightgreen) ![Sin escáneres de terceros](https://img.shields.io/badge/esc%C3%A1neres%20de%20terceros-ninguno-blue) ![Claude Skill](https://img.shields.io/badge/Claude-skill-orange)

[English](README.md) · [Português (BR)](README.pt-BR.md) · **🌐 Español**

</div>

---

## 💥 Una clave filtrada puede costarte más que todo el proyecto

Lo construiste rápido, con IA y con plazos reales. En algún lugar puede haber:

- una **clave de OpenAI o Stripe** dentro del bundle del frontend, lista para que cualquiera la copie
- un `.env` que borraste pero que sigue en el **historial de Git**
- una verificación "premium" que solo se ejecuta **en el navegador**
- un endpoint donde cambiar `?id=41` por `?id=42` **muestra los datos de otro usuario**

Hay bots que rastrean los repositorios públicos de GitHub buscando estos errores las 24 horas. **Security Gatekeeper los encuentra primero.**

## ✅ Qué obtienes

| | |
|---|---|
| 🔑 **Caza de secretos** | Claves de API (OpenAI, Anthropic, Stripe, AWS, Supabase…), tokens y claves privadas en tu código, el **historial de Git**, los builds y los source maps |
| 🌐 **Exposición en frontend y builds** | Variables públicas (`VITE_*`, `NEXT_PUBLIC_*`…), bundles, instaladores, cookies, almacenamiento del navegador |
| 🔓 **Ataques a apps y APIs** | Control de acceso roto, IDOR, inyección, XSS, SSRF, CSRF, falta de rate limiting |
| 💸 **Abuso de la lógica de negocio** | Abuso de cupones, pruebas gratuitas y créditos, race conditions, licencias verificadas solo en el cliente |
| 👤 **Privacidad** | Datos personales en logs, telemetría o enviados a proveedores de IA |
| 📦 **Cadena de suministro** | CVEs conocidos, typosquatting, scripts postinstall maliciosos, GitHub Actions sin fijar |
| ☁️ **Infra, móvil y escritorio** | Docker, RLS de Supabase, reglas de Firebase, Electron, firma de código, cabeceras de seguridad |
| 🧩 **Listas por stack** | Next.js, Supabase, Firebase, Electron y apps con IA/LLM: qué revisar y cómo corregirlo |
| 🎯 **Modelado de amenazas** | *Cadenas* de ataque reales (STRIDE, OWASP Top 10, API Top 10, LLM Top 10), no solo una lista de avisos |

## 📋 Cómo es el informe

Cada auditoría termina con un veredicto claro, no con un muro de ruido. *(Ejemplo ilustrativo.)*

```
Scorecard                 Estado   Críticos  High  Medium  Low
Secrets & Credentials     🔴        1         0     0       0
Access Control / Auth     🟡        0         1     0       0
Supply Chain              🟢        0         0     0       2

VEREDICTO FINAL: NO-GO
Motivo: clave secreta de Stripe en producción en dist/assets/index.js (sk_l…9f).
Revócala y rótala antes que cualquier otra cosa.
```

Después ofrece una **fase de corrección asistida**: te muestra cada cambio antes de aplicarlo y vuelve a comprobar tras cada corrección.

## 🧠 Por qué es diferente

- **Piensa como un atacante, no como un escáner de palabras clave.** Sigue el recorrido de los datos en tu app y cómo una persona real lo explotaría.
- **Tu código no se envía a escáneres de terceros.** El análisis se ejecuta dentro del propio Claude; los auditores de dependencias (`npm audit`, `osv-scanner`) solo reciben nombres y versiones de paquetes.
- **Menos falsas alarmas.** Antes de calificar algo como High o Critical, argumenta contra su propio hallazgo y calibra la severidad.
- **Solo lectura por defecto.** No toca ningún archivo sin tu OK explícito.
- **Honesta por diseño.** Los hallazgos se marcan como *Confirmado*, *Probable* o *Potencial*, y lista lo que *no* pudo revisar. Una buena nota global nunca oculta un problema crítico.
- **Credenciales siempre enmascaradas** en los informes (`sk-ab…9f`).
- **Usa herramientas profesionales si las tienes** (`gitleaks`, `trufflehog`, `semgrep`, `trivy`, `osv-scanner`, `npm audit`, `pip-audit`…) y recurre al análisis manual si no.

## ⚡ Instálala en 60 segundos

**Claude.ai / app de escritorio:** Configuración → Capabilities → Skills → sube esta carpeta (o un `.zip`) con el `SKILL.md`.

**Claude Code:** copia la carpeta a `~/.claude/skills/security-gatekeeper/` (o a `.claude/skills/` dentro de tu proyecto).

## 🚀 Úsala

Solo pide:

> "Haz una auditoría de seguridad de este proyecto"
> "¿Está listo para publicar? Revisa la seguridad"
> "Voy a subirlo a GitHub, revisa si hay algo sensible"

También detecta cuando un proyecto parece terminado y **ofrece** la auditoría antes del lanzamiento.

## ❓ Preguntas frecuentes

**¿De verdad es gratis?** Sí. Licencia Apache-2.0, sin plan de pago, sin trampa.

**¿En qué idioma responde?** Las instrucciones de la skill están en portugués de Brasil, así que por defecto responde en portugués. Solo añade "responde en español" a tu petición.

**¿Sustituye una prueba de penetración profesional?** No. Detecta los errores comunes y costosos antes del lanzamiento. Para sistemas de alto riesgo, contrata a un profesional. Tampoco certifica el cumplimiento legal (RGPD/LGPD/CCPA).

**¿Con qué tipo de proyectos funciona?** Apps web, SaaS, APIs, apps móviles y de escritorio, extensiones de navegador, scripts e incluso otras skills de Claude. Se auditó a sí misma antes de este lanzamiento.

## 💛 Apoya el proyecto

Security Gatekeeper es gratis y seguirá siéndolo. Si te salvó de una clave filtrada (o de una mala noche), una donación ayuda a que sigan saliendo nuevas herramientas:

| Moneda | Red | Dirección |
|---|---|---|
| **Bitcoin (BTC)** | Bitcoin (Native SegWit) | `bc1qnkpm79xsymwn0w6gyq7hthrhd247r9pcysqs2w` |
| **Ethereum (ETH)** | Ethereum / ERC-20 | `0xaaee7cd8a131bca4372ef14823a9dfe12f2108e3` |

Envía solo la moneda correcta en la red correcta. ¡Una ⭐ en el repositorio también ayuda!

**Más herramientas gratuitas mías:** [CleanPano](https://github.com/CleanPano/CleanPano), un limpiador de PC · [CleanWinVista](https://github.com/CleanPano/CleanWinVista), un dock para Windows

## 📄 Licencia

[Apache-2.0](LICENSE). Úsala, haz un fork y lanza con más seguridad.

Parte de las listas de verificación se adaptó de [Strix](https://github.com/usestrix/strix) (Apache-2.0, © OmniSecure Inc.); consulta [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Este proyecto no está afiliado ni respaldado por Strix.
