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

### 🔍 Fase 1: Minha Arquitetura e Planejamento Seguro

Antes de digitar qualquer linha de código, precisei pensar em como manter meu site seguro contra invasões e vulnerabilidades comuns. Decidi não usar CMS pesados (como WordPress), pois eles costumam abrir brechas para plugins vulneráveis e SQL Injection. Optei por uma SPA (Single Page Application) estática e limpa.

---

### 🧱 Fase 2: Como Construí a Estrutura Base (HTML5 & CSS3)

Desenvolvi a base visual focando em uma identidade escura e elegante, usando as fontes **Cinzel** (títulos) e **Plus Jakarta Sans** (textos):

**Cabeçalho Fixo:** Criei um cabeçalho fixo no meu HTML com um logotipo interativo que sempre me leva de volta à aba de início (`mudarAba('inicio')`).

**Seções e IDs:** Dividi o conteúdo em seções delimitadas por IDs para que cada aba do site funcionasse de forma fluida.

---

### 💻 Fase 3: O Sistema SPA e a Navegação por Abas que Desenvolvi

Para evitar que a página ficasse recarregando e para controlar o fluxo de navegação do usuário de forma limpa, criei minha própria lógica em JavaScript:

**Função de Navegação:** Escrevi esta função no meu script:

```javascript
function mudarAba(nomeAba) {
    const abas = document.querySelectorAll('.aba-conteudo');
    abas.forEach(aba => aba.classList.remove('ativa'));

    const abaAtiva = document.getElementById('aba-' + nomeAba);
    if (abaAtiva) {
        abaAtiva.classList.add('ativa');
    }
    window.scrollTo({ top: 0, behavior: 'smooth' });
}
```

---

### 🔒 Fase 4: O Hardening que Apliquei nos Formulários e a Mitigação de XSS

Para proteger o meu formulário de captação de leads (Leitor VIP) contra injeções de códigos maliciosos (XSS) e garantir que os dados chegassem limpos, configurei validações rígidas:

**Atributos Defensivos:** Utilizei os atributos nativos do HTML de forma defensiva (`type`, `required`, `placeholders` orientativos):

```html
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
```

---

### 🛡️ Fase 5: Como Blindei meus Links Externos contra Ataques de Terceiros

Como o meu site redireciona leitores para plataformas externas (como a Amazon e a livraria Unicorn Books), eu tomei o cuidado de me proteger contra ataques do tipo Tabnabbing e roubo de sessão:

**Segurança de Links:** Adicionei os atributos de segurança defensiva em todos os meus links externos:

```html
<a href="https://www.amazon.com.br/stores/author/B0CVVC7432/allbooks" target="_blank" rel="noopener noreferrer">Amazon</a>
```

---

### 📦 Fase 6: Meu Controle de Versão, Auditoria e Deploy no GitHub

Para garantir que eu não perdesse nenhuma alteração e mantivesse o histórico auditável do meu código, segui estes comandos no meu terminal:

**Inicialização e Adição:** Inicializei o repositório e adicionei meus arquivos:

```bash
git init
git add .
```

**Commit Estruturado:** Fiz o commit detalhado do meu progresso:

```bash
git commit -m "feat: implementa hardening de formulários e estrutura SPA do meu site"
```

**Envio para o Repositório:** Enviei tudo para o meu repositório remoto no GitHub:

```bash
git push origin main
```

---

### 🎨 Fase 7: O Ajuste – Correção de Layout e Alinhamento de Capas

Hoje identifiquei e resolvi um problema visual importante na grade de livros: as capas de tamanhos variados quebravam o alinhamento das caixas e geravam espaços vazios indesejados.

**A Solução Técnica Aplicada:** Defini uma altura fixa padronizada para os containers e utilizei a propriedade de CSS `object-fit: cover` combinada com `object-position: center`.

**Código Implementado no CSS:**

```css
.capa-container {
    width: 100%;
    height: 350px; 
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 15px;
    background: #050505;
}

.capa-container img {
    width: 100%;
    height: 100%;
    object-fit: cover; 
    object-position: center;
    transition: transform 0.5s ease;
}
```
