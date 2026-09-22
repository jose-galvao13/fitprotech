# Site FITPRO TECH

Site institucional da FITPRO TECH, construído em [Astro](https://astro.build),
pronto para publicar no GitHub Pages.

## O que já está feito

- Site de uma página em português (pt-PT), com as secções: Início, Sobre,
  O que fazemos (Produtos e Serviços), Como trabalhamos, Projetos e Contacto.
- Cores e motivo visual (duplo chevron) baseados no logótipo.
- Formulário de contacto que envia diretamente para
  `fitprotech.geral@gmail.com` através do serviço gratuito Web3Forms
  (ver secção "Ativar o formulário de contacto" abaixo — **é o único
  passo obrigatório antes de publicar**).
- Todo o conteúdo (dados da empresa, CAE, serviços) foi retirado dos
  documentos `Dados_Empresa.docx` e `Estrutura_da_Empresa.docx` fornecidos.

## O que falta preencher (placeholders)

Procure por estes pontos antes ou depois de publicar:

| Onde | O que fazer |
|---|---|
| `src/components/Footer.astro` | Os links "Instagram" e "Facebook" apontam para `#`. Substitua pelos URLs reais das redes sociais, ou remova as linhas se a empresa não as tiver. |
| `src/components/Projetos.astro` | Secção com 3 blocos de placeholder ("Foto do projeto", "[Nome do projeto]"). Substituir por fotos e nomes reais de projetos concluídos quando existirem (ou apagar o componente de `src/pages/index.astro` se não quiser esta secção por agora). |
| `public/img/logo.jpg` | Está a usar o logótipo fornecido (fundo escuro). Se tiver uma versão em PNG com fundo transparente, substitua este ficheiro e ajuste a extensão nas referências em `src/layouts/Layout.astro`. |

Não incluí no site público o IBAN, NIB e número de Segurança Social da
empresa (estavam no documento de dados, mas não são informação a publicar
num site). O NIF/NIPC aparece apenas no rodapé, como é habitual em sites
comerciais portugueses.

## Como testar localmente

Precisa de ter o [Node.js](https://nodejs.org) instalado (versão 22 ou
superior).

```bash
npm install
npm run dev
```

Depois abra o endereço que aparecer no terminal (normalmente
`http://localhost:4321`).

## Publicar no GitHub Pages

1. Crie um repositório no GitHub (ex.: `fitprotech-site`) e envie este
   projeto para lá:
   ```bash
   git init
   git add .
   git commit -m "Site FITPRO TECH"
   git branch -M main
   git remote add origin https://github.com/SEU-UTILIZADOR/NOME-DO-REPOSITORIO.git
   git push -u origin main
   ```
2. No GitHub, vá a **Settings → Pages** do repositório e, em "Build and
   deployment" → "Source", escolha **GitHub Actions**. Não precisa de fazer
   mais nada aqui — o ficheiro `.github/workflows/deploy.yml` já está
   configurado para publicar automaticamente a cada `git push` para `main`.
3. Edite `astro.config.mjs` e substitua:
   ```js
   site: 'https://SEU-UTILIZADOR.github.io',
   base: '/NOME-DO-REPOSITORIO',
   ```
   pelos valores reais (o nome de utilizador do GitHub e o nome do
   repositório que criou no passo 1). Faça commit e push desta alteração.
4. Ao fim de 1–2 minutos, o site fica disponível em:
   `https://SEU-UTILIZADOR.github.io/NOME-DO-REPOSITORIO/`

### Se quiser um domínio próprio (ex. fitprotech.pt)

Em **Settings → Pages → Custom domain**, indique o domínio e siga as
instruções do GitHub para configurar o DNS. Depois, em `astro.config.mjs`,
mude para:
```js
site: 'https://fitprotech.pt',
base: '/',
```

## Estrutura do projeto

```
src/
  components/   Cada secção da página (Header, Hero, Sobre, Servicos, ...)
  layouts/      Layout.astro — estrutura HTML comum (head, fontes, etc.)
  pages/        index.astro — junta todos os componentes na página final
  styles/       global.css — cores, tipografia e estilos partilhados
public/img/     Logótipo e outras imagens estáticas
.github/workflows/deploy.yml   Publicação automática no GitHub Pages
```

## Alterar textos ou dados

A maior parte do texto está escrita diretamente dentro de cada ficheiro
`.astro` (ex.: `src/components/Hero.astro`, `src/components/Sobre.astro`).
Procure o texto que quer mudar e edite-o — não precisa de saber programar
para isto, é só texto normal dentro do ficheiro.
