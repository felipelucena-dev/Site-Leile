# 🛡️ Meu Laboratório de Segurança Web & Landing Page: Do Zero ao Deploy | Autora Jéssica Almeida

Este repositório é o meu laboratório prático e o resultado direto de como construí a Landing Page e o site oficial da escritora Jéssica Almeida do absoluto zero. Aqui, decidi unir o melhor dos dois mundos: um design editorial imersivo com uma forte camada de Cibersegurança, Hardening de Aplicações Web e Boas Práticas de Defesa.

Se você quiser criar um site idêntico ao meu seguindo exatamente o meu raciocínio e os passos que tomei, preparei este guia prático em formato de passo a passo.

---

## 📋 O Que Eu Fiz (Meu Sumário)

* **Fase 1:** Minha Arquitetura e Planejamento Seguro (Seguro por Design)
* **Fase 2:** Como Construí a Estrutura Base (HTML5 & CSS3)
* **Fase 3:** O Sistema SPA e a Navegação por Abas que Desenvolvi (JavaScript)
* **Fase 4:** O Hardening que Apliquei nos Formulários e a Mitigação de XSS (Leitor VIP)
* **Fase 5:** Como Blindei meus Links Externos contra Ataques de Terceiros
* **Fase 6:** Meu Controle de Versão, Auditoria e Deploy no GitHub
* **Fase 7:** O Ajuste de Hoje – Correção de Layout e Alinhamento de Capas

---

## 🛠️ Meu Guia Passo a Passo: Como Reproduzir Este Projeto Exatamente Como Eu Fiz

### Fase 1: Minha Arquitetura e Planejamento Seguro

Antes de digitar qualquer linha de código, precisei pensar em como manter meu site seguro contra invasões e vulnerabilidades comuns:

**Minha Escolha de Arquitetura:** Decidi não usar CMS pesados (como WordPress), pois eles costumam abrir brechas para plugins vulneráveis e SQL Injection. Optei por uma SPA (Single Page Application) estática e limpa.

**Como organizei minhas pastas:**

```text
/site-irma
├── index.html       # Minha página principal com todas as views
├── style.css        # Minha estilização e tema escuro personalizado
└── assets/images    # Minhas imagens tratadas localmente


## Fase 2: Como Construí a Estrutura Base (HTML5 & CSS3)

Desenvolvi a base visual focando em uma identidade escura e elegante, usando as fontes **Cinzel** (títulos) e **Plus Jakarta Sans** (textos):

**Cabeçalho Fixo:** Criei um cabeçalho fixo no meu HTML com um logotipo interativo que sempre me leva de volta à aba de início (`mudarAba('inicio')`).

**Seções e IDs:** Dividi o conteúdo em seções delimitadas por IDs para que cada aba do site funcionasse de forma fluida.
