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

Procure o texto que quer mudar e edite-o — não precisa de saber programar
para isto, é só texto normal dentro do ficheiro.
