# Secure Web Lab | Landing Page com Foco em Cibersegurança & Hardening

Repositório desenvolvido para estruturação de páginas web seguras (Landing Pages e Portfólios), unindo design minimalista/dark ao rigor técnico de segurança ofensiva (*Red Team*) e defensiva (*Blue Team*).

---

## 🛡️ Camadas de Segurança Implementadas (Hardening)

O projeto foi construído mitigando vetores comuns de ataques web desde a sua fundação estrutural:

1. **Content Security Policy (CSP):** 
   * *Objetivo:* Restringe a execução de scripts ao próprio domínio, mitigando vetores de injeção de código (`XSS`).
2. **Proteção contra Clickjacking (`X-Frame-Options: DENY`):**
   * *Objetivo:* Bloqueia a renderização da página em `iframes` externos, prevenindo ataques de sequestro de cliques.
3. **MIME-sniffing Defense (`X-Content-Type-Options: nosniff`):**
   * *Objetivo:* Força o navegador a respeitar estritamente o tipo de arquivo declarado, evitando a execução de payloads maliciosos disfarçados.
4. **Isolamento de Links Externos (`rel="noopener noreferrer"`):**
   * *Objetivo:* Neutraliza ataques de *Tabnabbing*, impedindo que páginas externas abertas via link obtenham referência de controle (`window.opener`) sobre a aba original.

---

## 🚀 Arquitetura e Padrão de Desenvolvimento Seguro

Metodologia adotada na concepção estrutural deste projeto:

### Etapa 1: Estruturação Base (`index.html`)
* Implementação mandatória de cabeçalhos de segurança (*Security Headers*) na tag `<head>` para *hardening* nativo do navegador.
* Aplicação de atributos de isolamento em todos os redirecionamentos externos.

### Etapa 2: Estilização (`style.css`)
* Padronização de identidade visual direcionada (paleta dark/cinematográfica).
* Validação de dependências para garantir integridade e priorização de protocolos criptografados (HTTPS).

### Etapa 3: Versionamento e Controle (Git)
* Histórico de commits estruturado com foco em engenharia de software e segurança:
  ```bash
  git init
  git add .
  git commit -m "feat: implementacao inicial com hardening estrutural"
  git push origin main