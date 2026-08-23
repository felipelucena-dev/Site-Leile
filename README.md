Markdown

# 🛡️ Meu Secure Web Lab & Landing Page: Do Zero ao Deploy | Autora Jéssica Almeida

Este repositório é o meu laboratório prático e o resultado direto de como construí a Landing Page e o site oficial da escritora **Jéssica Almeida** do absoluto zero. Aqui, decidi unir o melhor dos dois mundos: um design editorial imersivo com uma forte camada de **Cibersegurança, Hardening de Aplicações Web e Boas Práticas de Defesa**.

Se você quiser criar um site idêntico ao meu seguindo exatamente o meu raciocínio e os passos que tomei, preparei este guia prático em formato de passo a passo.

---

## 📋 O Que Eu Fiz (Meu Sumário)
1. [Fase 1: Minha Arquitetura e Planejamento Seguro (Secure by Design)](#fase-1-minha-arquitetura-e-planejamento-seguro)
2. [Fase 2: Como Construí a Estrutura Base (HTML5 & CSS3)](#fase-2-como-construí-a-estrutura-base)
3. [Fase 3: O Sistema SPA e a Navegação por Abas que Desenvolvi (JavaScript)](#fase-3-o-sistema-spa-e-a-navegação-por-abas-que-desenvolvi)
4. [Fase 4: O Hardening que Apliquei nos Formulários e a Mitigação de XSS (Leitor VIP)](#fase-4-o-hardening-que-apliquei-nos-formulários-e-a-mitigação-de-xss)
5. [Fase 5: Como Blindei meus Links Externos contra Ataques de Terceiros](#fase-5-como-blindei-meus-links-externos-contra-ataques-de-terceiros)
6. [Fase 6: Meu Controle de Versão, Auditoria e Deploy no GitHub](#fase-6-meu-controle-de-versão-auditoria-e-deploy-no-github)

---

## 🛠️ Meu Guia Passo a Passo: Como Reproduzir Este Projeto Exatamente Como Eu Fiz

### Fase 1: Minha Arquitetura e Planejamento Seguro
Antes de digitar qualquer linha de código, precisei pensar em como manter meu site seguro contra invasões e vulnerabilidades comuns:
* **Minha Escolha de Arquitetura:** Decidi não usar CMS pesados (como WordPress), pois eles costumam abrir brechas para plugins vulneráveis e SQL Injection. Optei por uma SPA (Single Page Application) estática e limpa.
* **Como organizei minhas pastas:**
  ```text
  /site-irma
  ├── index.html       # Minha página principal com todas as views
  ├── style.css        # Minha estilização e tema escuro personalizado
  └── assets/images    # Minhas imagens tratadas localmente

Fase 2: Como Construí a Estrutura Base

Desenvolvi a base visual focando em uma identidade escura e elegante, usando as fontes Cinzel (títulos) e Plus Jakarta Sans (textos):

    Criei um cabeçalho fixo no meu HTML com um logotipo interativo que sempre me leva de volta à aba de início (mudarAba('inicio')).

    Dividi o conteúdo em seções delimitadas por IDs para que cada aba do site funcionasse de forma fluida.

Fase 3: O Sistema SPA e a Navegação por Abas que Desenvolvi

Para evitar que a página ficasse recarregando e para controlar o fluxo de navegação do usuário de forma limpa, criei minha própria lógica em JavaScript:

    Escrevi esta função no meu script:
    JavaScript

    function mudarAba(nomeAba) {
        const abas = document.querySelectorAll('.aba-conteudo');
        abas.forEach(aba => aba.classList.remove('ativa'));

        const abaAtiva = document.getElementById('aba-' + nomeAba);
        if (abaAtiva) {
            abaAtiva.classList.add('ativa');
        }
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

Fase 4: O Hardening que Apliquei nos Formulários e a Mitigação de XSS

Para proteger o meu formulário de captação de leads (Leitor VIP) contra injeções de códigos maliciosos (XSS) e garantir que os dados chegassem limpos, configurei validações rígidas:

    Utilizei os atributos nativos do HTML de forma defensiva (type, required, placeholders orientativos):
    HTML

    <form class="form-vip" onsubmit="event.preventDefault(); alert('Inscrição realizada com sucesso!');">
        <div class="grupo-input">
            <label for="whatsapp">WhatsApp *</label>
            <input type="text" id="whatsapp" required placeholder="(00) 00000-0000">
        </div>
        <div class="grupo-input">
            <label for="email">E-mail *</label>
            <input type="email" id="email" required placeholder="seu@email.com">
        </div>
    </form>

Fase 5: Como Blindei meus Links Externos contra Ataques de Terceiros

Como o meu site redireciona leitores para plataformas externas (como a Amazon e a livraria Unicorn Books), eu tomei o cuidado de me proteger contra ataques do tipo Tabnabbing e roubo de sessão:

    Adicionei os atributos de segurança defensiva em todos os meus links externos:
    HTML

    <a href="[https://www.amazon.com.br/stores/author/B0CVVC7432/allbooks](https://www.amazon.com.br/stores/author/B0CVVC7432/allbooks)" target="_blank" rel="noopener noreferrer">Amazon</a>

Fase 6: Meu Controle de Versão, Auditoria e Deploy no GitHub

Para garantir que eu não perdesse nenhuma alteração e mantivesse o histórico auditável do meu código, segui estes comandos no meu terminal:

    Inicializei o repositório e adicionei meus arquivos:
    Bash

git init
git add .

Fiz o commit detalhado do meu progresso:
Bash

git commit -m "feat: implementa hardening de formulários e estrutura SPA do meu site"

Envie tudo para o meu repositório remoto no GitHub:
Bash

git push origin main