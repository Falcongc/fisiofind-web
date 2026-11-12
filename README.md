# FisioFind Web - Projeto de Design UX/UI e Arquitetura de Interface

Protótipo funcional desenvolvido para avaliação acadêmica de Design UX/UI, Acessibilidade (WCAG 2.1) e Arquitetura de Componentes Front-End.

## 1. Justificativa das Tecnologias Utilizadas
Embora o MVP mobile original do **FisioFind** tenha sido concebido em Flutter e Firebase, este protótipo web foi construído em **HTML5 Semântico, CSS3 (Design System com CSS Variables), Tailwind CSS e JavaScript Vanilla** para atender diretamente às exigências de inspeção estrutural de DOM, semântica web e validação prática das diretrizes de acessibilidade **WCAG 2.1**.

## 2. Arquitetura Modular e Independência de Microserviços
A interface foi dividida em componentes independentes (`<header>`, `<nav>`, `<main>`, `<section>` de Paciente, `<section>` de Catálogo e `<section>` de Agenda):
- **Auth & Patient Service:** Carrega os dados cadastrais e prontuário do paciente (Michel Maciel Falcão).
- **Catalog Service:** Renderiza os dados profissionais e registro CREFITO da especialista (Dra. Julia Henrique da Silva Falcão).
- **Booking Service (Isolamento de Falhas):** Possui tratamento de erro independente. Caso o microserviço de agendamento sofra queda (`HTTP 503`), um alerta local (*Fallback UI*) é exibido apenas no bloco da agenda, mantendo o catálogo e o prontuário 100% operacionais.

## 3. Identidade Visual (Design System no Código)
Centralizado no bloco `:root` via variáveis CSS:
- **Primária (Deep Teal):** `#0D5C75`
- **Secundária (Teal):** `#009688`
- **Destaque / Foco Acessível (Mint Green):** `#10B981`
- **Tipografia:** Inter (Google Fonts)

## 4. Acessibilidade (WCAG 2.1)
- Tags semânticas estruturais (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
- Atributos `aria-label`, `aria-live` e `role` configurados para leitores de tela.
- Navegabilidade 100% funcional via teclado (tecla `Tab`) com anel de foco visível e modo de **Alto Contraste** integrado no topo da aplicação.

## 5. Como Executar o Projeto
1. Acesse o link público do **GitHub Pages** ou baixe o arquivo **index.html**.
2. Abra o arquivo em qualquer navegador moderno.
3. Na tela de login, clique em **Entrar no FisioFind**.
4. Utilize a barra superior de demonstração para testar a queda da API de Agendamento (`HTTP 503`) e o modo de Alto Contraste WCAG.
