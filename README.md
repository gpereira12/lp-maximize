# 🚀 Maximize Digital — Landing Page

> Landing page de alta conversão para a **Maximize Digital**, consultoria especializada em captação de pacientes particulares para clínicas e consultórios através de Google Ads.

---

## 📌 Sobre o Produto

A **Maximize Digital** é uma consultoria de tráfego pago com foco exclusivo na área da saúde. O objetivo desta landing page é converter visitantes qualificados — médicos, psicólogos, nutricionistas e demais profissionais de saúde — em leads que iniciam contato direto via WhatsApp.

### Proposta de Valor

A página comunica, de forma clara e progressiva, que a Maximize Digital não é uma agência genérica: é uma consultoria especializada que entende a jornada de um paciente particular e utiliza essa compreensão para criar campanhas de Google Ads que atraem o perfil certo, com consistência e previsibilidade.

---

## 🗺️ Estrutura Narrativa da Página

A página foi construída seguindo o framework de copywriting **Problem → Agitation → Solution (PAS)**, adaptado para o mercado de saúde:

| # | Seção | Objetivo |
|---|---|---|
| 1 | **Hero** | Capturar atenção imediata com a proposta de valor central e CTA direto para WhatsApp |
| 2 | **Problema** | Identificar as dores do profissional de saúde: agenda vazia, leads desqualificados, dependência de indicações |
| 3 | **Público-Alvo** | Qualificar o visitante e confirmar que ele está no lugar certo |
| 4 | **Solução** | Apresentar a metodologia exclusiva da Maximize com diferenciação clara |
| 5 | **Como Funciona** | Simplificar o processo em etapas para reduzir objeções |
| 6 | **Resultados** | Prova social quantitativa: métricas reais de performance |
| 7 | **Depoimentos** | Prova social qualitativa: testemunhos reais de clientes |
| 8 | **Sobre** | Humanizar a marca apresentando Daniel Munhoz, o fundador |
| 9 | **CTA Final** | Fechamento sem atrito com contato direto via WhatsApp |

---

## 🛠️ Stack Técnica

| Tecnologia | Versão | Função |
|---|---|---|
| [Astro](https://astro.build) | `^6.3.1` | Framework principal — gera HTML 100% estático |
| Vanilla CSS | — | Estilização via design tokens (CSS Custom Properties) |
| TypeScript | — | Tipagem no frontmatter dos componentes Astro |
| Node.js | `>=22.12.0` | Runtime necessário para o ambiente de build |

**Por que Astro?**
- Output 100% estático: `0kB` de JavaScript enviado ao browser por padrão
- Performance máxima (Core Web Vitals excelentes nativamente)
- Componentes isolados com CSS scoped por padrão (sem conflitos de classe)
- Integração nativa com variáveis de ambiente via `import.meta.env`

---

## 📁 Estrutura do Projeto

```
lp-maximize/
├── public/
│   └── images/
│       ├── daniel.png          # Foto do fundador
│       └── logo/               # Assets de logo da marca
├── src/
│   ├── components/
│   │   ├── Hero.astro          # Seção 1: Headline principal + CTA
│   │   ├── Problem.astro       # Seção 2: Dores do profissional de saúde
│   │   ├── TargetAudience.astro# Seção 3: Para quem é esse serviço
│   │   ├── Solution.astro      # Seção 4: A metodologia Maximize
│   │   ├── Steps.astro         # Seção 5: Como funciona (passo a passo)
│   │   ├── Results.astro       # Seção 6: Métricas e resultados reais
│   │   ├── Testimonials.astro  # Seção 7: Depoimentos de clientes
│   │   ├── About.astro         # Seção 8: Sobre Daniel Munhoz
│   │   ├── CTASection.astro    # Seção 9: Fechamento + contato WhatsApp
│   │   └── Footer.astro        # Rodapé com informações legais
│   ├── layouts/
│   │   └── Layout.astro        # Layout base com GTM, meta tags e SEO
│   ├── pages/
│   │   └── index.astro         # Página principal (orquestra todos os componentes)
│   └── styles/
│       └── global.css          # Design System: tokens, reset, utilitários globais
├── .env                        # Variáveis de ambiente (NÃO commitar)
├── .env.example                # Template de variáveis para novos ambientes
├── astro.config.mjs            # Configuração do Astro
└── package.json
```

---

## ⚙️ Variáveis de Ambiente

Copie o `.env.example` para `.env` e preencha os valores:

```bash
cp .env.example .env
```

| Variável | Descrição | Exemplo |
|---|---|---|
| `PUBLIC_WHATSAPP_URL` | URL completa do WhatsApp com mensagem pré-preenchida | `https://wa.me/5511988829970?text=...` |
| `PUBLIC_GTM_ID` | ID do container do Google Tag Manager | `GTM-XXXXXXX` |

> **Importante:** O prefixo `PUBLIC_` é obrigatório no Astro para que variáveis sejam expostas ao browser. Variáveis sem esse prefixo ficam disponíveis apenas no build server-side.

> **Segurança:** O arquivo `.env` está no `.gitignore`. Nunca o commite. Em produção (Vercel), configure as variáveis pelo painel em **Settings → Environment Variables**.

---

## 🚀 Rodando Localmente

```bash
# 1. Instalar dependências
npm install

# 2. Criar arquivo de ambiente
cp .env.example .env
# Edite o .env com seus valores reais

# 3. Iniciar servidor de desenvolvimento
npm run dev
# Acesse: http://localhost:4321
```

### Comandos Disponíveis

| Comando | Ação |
|---|---|
| `npm run dev` | Inicia o servidor de desenvolvimento com HMR |
| `npm run build` | Gera o bundle de produção estático em `./dist/` |
| `npm run preview` | Pré-visualiza o build de produção localmente |

---

## ☁️ Deploy na Vercel

### Opção 1 — Via GitHub (Recomendada)

1. Faça push do repositório para o GitHub
2. Acesse [vercel.com/new](https://vercel.com/new) e importe o repositório
3. A Vercel detecta o Astro automaticamente — **nenhuma configuração adicional necessária**
4. Adicione as variáveis de ambiente no painel: **Settings → Environment Variables**
5. Todo `git push` na branch `main` dispara um redeploy automático

### Opção 2 — Via CLI

```bash
npx vercel --yes
```

---

## 🎨 Design System

A página utiliza um sistema de design baseado em **CSS Custom Properties** definidas em `global.css`:

- **Paleta:** Verde escuro primário (`#2C3E2A`) + Dourado accent (`#C5A880`) + Bege claro (`#E6DEC8`)
- **Tipografia:** [Outfit](https://fonts.google.com/specimen/Outfit) (Google Fonts) — peso 400 a 800
- **Layout:** Sistema de container centralizado com `clamp()` responsivo para tipografia fluida
- **Animações:** `fade-in-up` ativado por `IntersectionObserver` para performance otimizada

---

## 📄 Licença

Projeto proprietário — desenvolvido exclusivamente para a **Maximize Digital**.  
Todos os direitos reservados.
