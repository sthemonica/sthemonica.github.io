# Site da Sthefanie

Site pessoal e acadêmico baseado no tema [Gradfolio](https://github.com/jitinnair1/gradfolio)
(licença MIT, de Jitin Nair), adaptado com **publicações**, **artigos, vídeos, podcasts e galeria de fotos**, **CV que vira PDF**,
**ligação com o LinkedIn**, **botão de modo escuro** e **versões em português e inglês**. Hospedado de graça no GitHub Pages e editável
direto pelo site do GitHub, sem instalar nada.

Abas do cabeçalho: **Início · Pesquisa · Publicações · Conteúdos · CV**
(em inglês: **Home · Research · Publications · Content · CV**, em `/en/`).
Conteúdos tem as subabas **Artigos · Vídeos · Podcasts · Galeria de fotos**.

---

## 1. Colocar o site no ar (uma vez só)

1. Crie um repositório chamado **exatamente** `SEU-USUARIO.github.io`, público.
2. **Add file → Upload files**: arraste **todo o conteúdo desta pasta** (não a
   pasta em si) e clique em **Commit changes**.
3. Edite o `_config.yml` e troque `SEU-USUARIO` na linha `url`.
4. Em **Settings → Pages**, confira: *Deploy from a branch*, branch **main**, pasta **/ (root)**.
5. Acompanhe na aba **Actions** (verde = pronto) e abra `https://SEU-USUARIO.github.io`.

## 2. Personalizar

| O que | Onde |
|---|---|
| Nome e linha abaixo dele no cabeçalho | `_config.yml` → `title`, `description` (PT) e `description_en` (EN) |
| Nomes das abas e demais textos da interface | `_data/i18n.yml` |
| Ícones do rodapé (LinkedIn, YouTube, e-mail, Lattes, ORCID…) | `_config.yml` — use só o **usuário** (YouTube: `@canal`), exceto Lattes, Scholar e Spotify (link completo) |
| Sua foto | substitua `assets/images/perfil.jpg` (quadrada, mesmo nome) |
| Texto da página inicial | `index.md` (PT) e `en/index.md` (EN) |
| Cor principal (verde) | `assets/css/_sass/variables.scss` → `$brand-color` e `$projectbox` |

Campos vazios (`""`) no `_config.yml` simplesmente não aparecem.

## 3. Publicar um novo artigo ✍️

1. Na pasta `_posts/pt` (texto em português) ou `_posts/en` (texto em inglês):
   **Add file → Create new file**.
2. Nome no formato **`ANO-MES-DIA-titulo.md`**, ex.: `2026-11-05-minha-tese-em-5-minutos.md`
   (sem acentos nem espaços no nome do arquivo; o título de verdade vai dentro).
3. Cole o conteúdo de `modelos/MODELO-post.md`, escreva e clique em **Commit changes**.

Em ~1 minuto ele aparece em **Conteúdos › Artigos** e em "Últimos artigos" na página inicial
(veja a seção 4 sobre os dois idiomas).
Também dá para subir um `.md` pronto com **Upload files**, seguindo o padrão do nome.

Campos do cabeçalho do post (entre os `---`):

```yaml
title: "Título do texto"        # obrigatório
resumo: "Frase para a lista"    # opcional (senão usa o 1º parágrafo)
tags: [congressos, pesquisa]    # opcional
imagem: "/assets/images/posts/capa.jpg"          # opcional, capa
linkedin: "https://www.linkedin.com/posts/..."   # opcional
ref: "apelido-do-texto"         # opcional, liga as versões PT e EN
```

A data do post é a do nome do arquivo (datas futuras só aparecem depois que o
dia chegar e houver um novo commit). Para despublicar, apague o arquivo.

## 4. Vídeos e podcasts 🎬🎙️

**Vídeo do YouTube:** crie um `.md` na pasta `_videos` com o conteúdo de
`modelos/MODELO-video.md` e cole o link do vídeo no campo `youtube` (qualquer
formato: `watch?v=`, `youtu.be/`, `shorts/`…). A miniatura aparece sozinha e o
vídeo toca ali mesmo ao clicar. Preencha `youtube: "@seucanal"` no `_config.yml`
para mostrar o ícone no rodapé e o botão "Ver o canal" na aba Vídeos.

**Podcast:** crie um `.md` na pasta `_podcasts` com o conteúdo de
`modelos/MODELO-podcast.md`. Com o link do episódio no **Spotify**, aparece um
player embutido; também há campos para Apple Podcasts, YouTube ou outro link.
O campo `programa` serve para quando você é convidada de outro podcast.

Nos dois casos, o campo `idioma` (pt/en) marca o conteúdo com uma etiqueta na
versão do site do outro idioma, e `title_en`/`texto_en` traduzem título e descrição.

## 5. Publicações 📚

Cada publicação é um arquivo `.md` na pasta `_publicacoes` (modelo em
`modelos/MODELO-publicacao.md`), com título, autores, revista/congresso, ano e
tipo (`artigo`, `conferencia`, `capitulo`, `preprint`, `tese` ou `outro`).

A aba agrupa por tipo, da mais recente para a mais antiga, com botões de filtro
no topo. Seu nome aparece em negrito na lista de autores: escreva-o em
`destaque_nome` no `_config.yml` exatamente como aparece nas publicações
(ex.: `"Souza S"`). Campos opcionais viram botões: DOI, PDF, código, dados,
slides e pôster; se escrever um resumo no corpo do arquivo, aparece um botão "Resumo".

A mesma lista entra **automaticamente no CV**, então você só cadastra cada
publicação uma vez.

## 6. CV 📄

O currículo fica em `cv.md` (português) e `en/cv.md` (inglês), escrito em
Markdown: `##` para seções, `###` para cada item e uma linha em *itálico* com
instituição · local · período. Seu nome, a linha de descrição e os contatos
entram automaticamente no topo (vêm do `_config.yml`).

O botão **Baixar PDF** abre a impressão do navegador já com um layout limpo
(sem menu, rodapé nem modo escuro); basta escolher "Salvar como PDF".
Se preferir oferecer um PDF pronto, envie-o para `assets/files/` e preencha
`cv_pdf: "/assets/files/CV.pdf"` no `_config.yml`: o botão passa a baixar esse arquivo.

## 7. Português e inglês 🌐

O botão **PT | EN** no canto superior direito troca o idioma do site inteiro.

- **Com tradução:** escreva as duas versões (uma em `_posts/pt`, outra em
  `_posts/en`) e coloque o **mesmo `ref`** nas duas, ex. `ref: tese-em-5-minutos`.
  O botão PT | EN pula direto de uma versão para a outra, e cada versão mostra
  no topo um aviso com link para a outra.
- **Sem tradução:** o texto aparece também na lista de artigos do outro idioma,
  marcado como "Disponível só em português/inglês", com um link de **tradução
  automática** (Google Tradutor). Assim todo mundo consegue ler tudo, e você
  traduz só o que quiser.
- **Projetos (Pesquisa):** `_projects/pt` e `_projects/en`, ligados também pelo `ref`.
- **Publicações:** uma lista só, que aparece nos dois idiomas.
- **Galeria:** uma foto serve aos dois idiomas; preencha `title_en`, `local_en`
  e `texto_en` para a versão em inglês (se vazios, aparece o texto em português).

## 8. Modo escuro 🌙

Por padrão o site segue o modo claro/escuro do aparelho do visitante. O botão
de lua/sol no canto superior direito troca manualmente, e o navegador lembra a
escolha. As cores do modo escuro ficam em `assets/css/_sass/variables.scss`.

## 9. Galeria de fotos 📸 (em Conteúdos)

1. Envie a foto para `assets/images/galeria/` (de preferência horizontal e com menos de ~1 MB).
2. Na pasta `_galeria`, crie um `.md` (qualquer nome) com o conteúdo de `modelos/MODELO-galeria.md`.
3. Ajuste `title`, `date`, `local` e `imagem` (o nome da foto enviada).

As fotos ficam da mais recente para a mais antiga; clicar amplia.

## 10. Projetos na aba Pesquisa 🔬

A aba Pesquisa mostra um bloco para cada área ou projeto: ao passar o mouse,
aparece o resumo (`description`); ao clicar, abre uma página com o texto
completo. Cada bloco é um arquivo em `_projects/pt` ou `_projects/en` (modelo em
`modelos/MODELO-projeto.md`). O campo `ordem` define a posição. Com o campo
`redirect`, o bloco leva direto para um link externo.

## 11. LinkedIn 🔗

- **Rodapé:** ícone do seu perfil (campo `linkedin` no `_config.yml`).
- **Cada artigo:** botão "Compartilhar no LinkedIn". Se você publicar algo lá sobre o
  texto, cole o link no campo `linkedin:` e aparece também "Ver a discussão no LinkedIn".
- **Galeria:** cada foto pode ter `linkedin:` apontando para a publicação daquela conquista.

No LinkedIn, vale colocar o endereço do site em *Informações de contato* e em *Destaques*.

## Ver no computador antes de publicar (opcional)

```bash
bundle install
bundle exec jekyll serve   # abra http://localhost:4000
```
