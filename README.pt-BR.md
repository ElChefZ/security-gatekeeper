<div align="center">

# 🛡️ Security Gatekeeper

### Sua última linha de defesa antes de apertar "publicar".

**Uma skill gratuita para o Claude que audita seu projeto como um atacante faria e diz com clareza se é seguro lançar: GO ou NO-GO.**

![Licença: Apache-2.0](https://img.shields.io/badge/licen%C3%A7a-Apache--2.0-blue) ![Preço: Grátis](https://img.shields.io/badge/pre%C3%A7o-gr%C3%A1tis-brightgreen) ![Sem scanners de terceiros](https://img.shields.io/badge/scanners%20de%20terceiros-nenhum-blue) ![Claude Skill](https://img.shields.io/badge/Claude-skill-orange)

[English](README.md) · **🌐 Português (BR)** · [Español](README.es.md)

</div>

---

## 💥 Uma chave vazada pode custar mais que o projeto inteiro

Você construiu rápido, com IA e com prazo de verdade. Em algum lugar pode estar:

- uma **chave da OpenAI ou do Stripe** dentro do bundle do frontend, pronta para qualquer um copiar
- um `.env` que foi apagado mas continua no **histórico do Git**
- uma checagem de "premium" que só roda **no navegador**
- um endpoint em que trocar `?id=41` por `?id=42` **mostra os dados de outro usuário**

Bots varrem repositórios públicos do GitHub atrás desses erros 24 horas por dia. **O Security Gatekeeper encontra antes.**

## ✅ O que você recebe

| | |
|---|---|
| 🔑 **Caça a secrets** | Chaves de API (OpenAI, Anthropic, Stripe, AWS, Supabase…), tokens e chaves privadas no código, no **histórico do Git**, nos builds e nos source maps |
| 🌐 **Exposição no frontend e builds** | Variáveis públicas (`VITE_*`, `NEXT_PUBLIC_*`…), bundles, instaladores, cookies, armazenamento do navegador |
| 🔓 **Ataques a app e API** | Controle de acesso quebrado, IDOR, injection, XSS, SSRF, CSRF, falta de rate limit |
| 💸 **Abuso de lógica de negócio** | Abuso de cupons, trials e créditos, race conditions, licença checada só no cliente |
| 👤 **Privacidade** | Dados pessoais em logs, telemetria ou enviados a provedores de IA |
| 📦 **Supply chain** | CVEs conhecidas, typosquatting, scripts postinstall maliciosos, GitHub Actions sem SHA |
| ☁️ **Infra, mobile e desktop** | Docker, RLS do Supabase, regras do Firebase, Electron, code signing, security headers |
| 🧩 **Checklists por stack** | Next.js, Supabase, Firebase, Electron e apps com IA/LLM: o que verificar e como corrigir |
| 🎯 **Threat modeling** | *Cadeias* de ataque reais (STRIDE, OWASP Top 10, API Top 10, LLM Top 10), não só uma lista de alertas |

## 📋 Como é o relatório

Toda auditoria termina num veredito claro, sem um mar de ruído. *(Exemplo ilustrativo.)*

```
Scorecard                 Status   Críticos  High  Medium  Low
Secrets & Credentials     🔴        1         0     0       0
Access Control / Auth     🟡        0         1     0       0
Supply Chain              🟢        0         0     0       2

VEREDITO FINAL: NO-GO
Motivo: chave secreta do Stripe em produção em dist/assets/index.js (sk_l…9f).
Revogue e rotacione antes de qualquer outra coisa.
```

Depois ela oferece uma **fase de correção assistida**: mostra cada alteração antes de aplicar e checa de novo depois de cada correção.

## 🧠 Por que ela é diferente

- **Pensa como atacante, não como scanner de palavras-chave.** Segue o caminho dos dados no seu app e como uma pessoa real exploraria isso.
- **Seu código não vai para scanners de terceiros.** A análise roda no próprio Claude; auditores de dependências (`npm audit`, `osv-scanner`) recebem só nomes e versões de pacotes.
- **Menos alarme falso.** Antes de dar nota High ou Critical, ela argumenta contra o próprio achado e calibra a severidade.
- **Só leitura por padrão.** Não mexe em nenhum arquivo sem o seu OK explícito.
- **Honesta por design.** Os achados vêm marcados como *Confirmado*, *Provável* ou *Potencial*, e ela lista o que *não* conseguiu checar. Uma boa nota geral nunca esconde um problema crítico.
- **Credenciais sempre mascaradas** no relatório (`sk-ab…9f`).
- **Usa ferramentas profissionais quando você tem** (`gitleaks`, `trufflehog`, `semgrep`, `trivy`, `osv-scanner`, `npm audit`, `pip-audit`…) e cai para análise manual quando não tem.

## ⚡ Instale em 60 segundos

**Claude.ai / app desktop:** Configurações → Capabilities → Skills → envie esta pasta (ou um `.zip`) com o `SKILL.md`.

**Claude Code:** copie a pasta para `~/.claude/skills/security-gatekeeper/` (ou para `.claude/skills/` dentro do projeto).

## 🚀 Use

É só pedir:

> "Roda uma auditoria de segurança neste projeto"
> "Está pronto para publicar? Checa a segurança"
> "Vou subir no GitHub, verifica se tem algo sensível"

Ela também percebe quando um projeto parece pronto e **oferece** a auditoria antes do lançamento.

## ❓ Perguntas frequentes

**É grátis mesmo?** Sim. Licença Apache-2.0, sem plano pago, sem pegadinha.

**Em que idioma ela responde?** Em português do Brasil, por padrão.

**Substitui um pentest profissional?** Não. Ela pega os erros comuns e caros antes do lançamento. Para sistemas de alto risco, contrate um profissional. Ela também não certifica conformidade jurídica (LGPD/GDPR).

**Funciona em que tipo de projeto?** Apps web, SaaS, APIs, apps mobile e desktop, extensões de navegador, scripts e até outras skills do Claude. Ela auditou a si mesma antes desta publicação.

## 💛 Apoie o projeto

O Security Gatekeeper é grátis e vai continuar grátis. Se ele te salvou de uma chave vazada (ou de uma noite ruim), uma doação ajuda a manter novas ferramentas saindo:

| Moeda | Rede | Endereço |
|---|---|---|
| **Bitcoin (BTC)** | Bitcoin (Native SegWit) | `bc1qnkpm79xsymwn0w6gyq7hthrhd247r9pcysqs2w` |
| **Ethereum (ETH)** | Ethereum / ERC-20 | `0xaaee7cd8a131bca4372ef14823a9dfe12f2108e3` |

Envie só a moeda certa na rede certa. Uma ⭐ no repositório também ajuda!

**Outras ferramentas gratuitas minhas:** [CleanPano](https://github.com/CleanPano/CleanPano), um limpador de PC · [CleanWinVista](https://github.com/CleanPano/CleanWinVista), um dock para o Windows

## 📄 Licença

[Apache-2.0](LICENSE). Use, faça fork e lance com mais segurança.

Inclui material adaptado de projetos open source de terceiros; veja [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
