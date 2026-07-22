# CLAUDE.md — Manual de História

Instruções permanentes para o Claude Code neste repositório. Leia este arquivo integralmente no início de cada sessão.

## O projeto

Manual educacional aberto e abrangente de **História**, em **português brasileiro**, parte da série *Manuais de Ciências*. Cobre **História Geral (Mundo) integrada à História do Brasil**, em ordem cronológica, com atenção explícita aos temas e ao estilo de questões de **vestibulares e do ENEM**. Formato livro Quarto com saída dupla **HTML + PDF**, publicado via GitHub Actions em GitHub Pages.

- **Escopo:** 15 volumes, 91 capítulos, em 3 fases (ver `ROADMAP.md`)
- **Público:** do leitor curioso ao estudante de ensino médio, pré-vestibular e graduação; sem pré-requisitos
- **Capítulo gabarito:** `capitulos/vol01/cap01-o-que-e-historia.qmd` — é a referência canônica de estilo, tom, profundidade e anatomia. Antes de escrever qualquer capítulo novo, releia-o.

## Modo de execução autônoma

Você está **pré-aprovado** para: criar e editar arquivos, gerar figuras TikZ/SVG, rodar comandos de validação (`quarto render`, `quarto preview`) e fazer `git commit` ao final de cada capítulo — **sem pausar para pedir aprovação**. Pare somente diante de erro verdadeiramente bloqueante.

- **Formato de commit:** `cap NN: <título do capítulo>` (ex.: `cap 04: A Revolução Francesa`). Para tarefas de infraestrutura: `infra: <descrição>`.
- **Windows:** use apenas flags simples `git commit -m "..."`. **Nunca** use here-strings do PowerShell (`@'...'@`) dentro do Bash — o caractere `@` vaza para a mensagem.
- **Fluxo de sessão:** um capítulo por sessão; `/clear` entre capítulos; `/compact` ao atingir ~80% do contexto; `/model opus` para escrever capítulos; `/model sonnet` para tarefas mecânicas (atualizar `_quarto.yml`, status no `ROADMAP.md`).
- **Estratégia de fatia vertical:** complete um volume inteiro antes de abrir o próximo; complete a Fase 1 antes da Fase 2. O `ROADMAP.md` é a fila autoritativa — atualize o status do capítulo (⬜ → ✅) no mesmo commit.

## Anatomia obrigatória de cada capítulo

Na ordem:

1. **Abertura** — parágrafo-gancho que conecta o tema a uma cena concreta, a uma pergunta instigante ou ao presente do leitor (uma notícia, um debate atual, um lugar de memória, um filme). Nunca comece por "Neste capítulo veremos…".
2. **Objetivos de aprendizagem** — lista curta "Ao final deste capítulo, você será capaz de…"
3. **Desenvolvimento** — seções `##` em ordem cronológica e/ou temática, com **contexto** (o quê, quando, onde), **processo** (como os eventos se encadeiam) e **causas e consequências** explicitadas; conceitos-chave definidos em callouts; linhas do tempo, mapas esquemáticos e diagramas em TikZ sempre que ajudarem a visualizar cronologia, espaço ou hierarquia social.
4. **`## 🔎 Historiografia em Foco`** — seção **obrigatória**: apresenta como os historiadores **debatem e interpretam** o tema do capítulo. Contraste ao menos duas leituras (escolas, autores ou revisões recentes), mostrando que a História é uma construção do conhecimento, não uma lista fechada de fatos. Sempre que possível, ancore a discussão numa **fonte primária** ou num historiador citado em `referencias.bib`. Explique por que as interpretações divergem (novas fontes, novas perguntas, contexto do próprio historiador).
5. **`## Resumo do capítulo`** — bullets densos recapitulando cada processo, conceito e data-chave
6. **`## Exercícios`** — 6 a 10 exercícios em dificuldade crescente, **misturando** questões conceituais, análise de documento/imagem e **questões no estilo ENEM/vestibular** (enunciado-texto + alternativas, quando couber); cada um com solução completa e comentada em bloco colapsável:
   ```markdown
   ::: {.callout-tip collapse="true" title="Solução"}
   ...
   :::
   ```
7. **`## Para saber mais`** — leituras, filmes e documentários recomendados, com citações `@chave` para as obras acadêmicas

### Convenções de escrita

- Português brasileiro, tom didático, narrativo e direto, segunda pessoa ("você"); rigor conceitual e cronológico sem jargão gratuito — todo termo técnico é definido na primeira ocorrência (em **negrito**)
- **Datas e nomes:** sempre situe o leitor no tempo e no espaço; ao introduzir um personagem, dê a baliza temporal (ex.: "Péricles (c. 495–429 a.C.)"). Use "a.C./d.C." de forma consistente
- Callouts Quarto: `.callout-note` (definições e conceitos), `.callout-important` (armadilhas, anacronismos e erros comuns), `.callout-tip` (intuição, mnemônicos e dicas de prova), `.callout-warning` (controvérsias historiográficas e limites das fontes)
- **Pluralismo e cuidado interpretativo:** em temas de debate real (causas da queda de Roma, natureza do feudalismo, caráter da Independência do Brasil, avaliação da Era Vargas ou do regime militar…), apresente as principais posições com seus melhores argumentos antes de qualquer síntese. **Evite anacronismo** (julgar o passado pelos valores do presente) e teleologia (tratar o que aconteceu como inevitável)
- **História plural:** contemple protagonismos habitualmente silenciados — mulheres, povos indígenas, população negra, camadas populares — como sujeitos históricos, não como apêndices. Atenção às Leis 10.639/2003 e 11.645/2008 (história e cultura afro-brasileira e indígena)
- Referências cruzadas: `@sec-`, `@fig-`, `@tbl-` sempre que citar outro ponto do manual
- Capítulos com ~2.500–4.500 palavras de corpo (fora exercícios)

### Bibliografia

- BibTeX em `referencias.bib` + CSL ABNT; citações no texto via `@chave` / `[@chave, p. 42]`
- Autores e obras esperados (exemplos): Marc Bloch, Fernand Braudel, Eric Hobsbawm, Jacques Le Goff, Peter Burke, Carlo Ginzburg, Jared Diamond, Yuval Harari; para o Brasil: Sérgio Buarque de Holanda, Caio Prado Jr., Gilberto Freyre, Boris Fausto, Lilia Schwarcz, Laurentino Gomes, Emília Viotti da Costa, José Murilo de Carvalho, Mary Del Priore; fontes primárias sempre que possível (Carta de Caminha, cronistas, tratados, discursos, constituições)
- Ao citar um autor pela primeira vez no manual, adicione a entrada ao `referencias.bib` no mesmo commit

## Figuras

**Divisão de responsabilidade:** TikZ para todo diagrama esquemático/didático — **linhas do tempo** (o recurso mais frequente), **mapas esquemáticos** (rotas, territórios, frentes de guerra — esquemáticos, não cartográficos de precisão), **organogramas de hierarquias sociais** (pirâmide feudal, sociedade colonial, sociedade de castas), **genealogias e dinastias**, **fluxogramas de causa e consequência**. Para conteúdo fotográfico (obras de arte, fotografias, documentos), use imagem embutida ou um placeholder descritivo.

Sintaxe TikZ obrigatória:

```markdown
::: {#fig-linha-do-tempo-imperio}

```{.tikz}
%%| filename: fig-linha-do-tempo-imperio
%%| alt: Linha do tempo do Segundo Reinado, de 1840 a 1889.
\begin{tikzpicture}
  ...
\end{tikzpicture}
```

Linha do tempo do Segundo Reinado.
:::
```

- Estilos predefinidos disponíveis: `curva`, `destaque`, `auxiliar`, `eixo`, `ponto`, `vetor`; cores: `manualblue`, `manualred`, `manualgreen`, `manualyellow`, `manualgray`
- **Convenção de linha do tempo:** eixo horizontal com `eixo`; marcos como `ponto` sobre a linha, rótulo de data abaixo e evento acima; períodos/eras como faixas destacadas; use `manualblue` para processos políticos, `manualred` para guerras/conflitos, `manualgreen` para economia/sociedade
- **Mapas e diagramas** são **esquemáticos** (setas de deslocamento, blocos rotulados), nunca cartografia de precisão
- Referencie sempre via `@fig-nome`

## ⚠️ Toolchain — regras invioláveis

Estas regras existem porque cada uma custou horas de depuração em manuais anteriores. **Nunca as redescubra.**

1. **Extensão TikZ (`danmackinlay/tikz`) tem patches locais.** Os arquivos vivem em `_extensions/danmackinlay/tikz/`. **NUNCA execute `quarto add` ou `quarto update`** — isso baixa o upstream sem os patches e quebra a renderização. No `_quarto.yml`, o filtro `danmackinlay/tikz` deve vir **antes** de `quarto`, e `tikz: svg-engine: dvisvgm`.

2. **PATH do TinyTeX é o bloqueador recorrente.** `quarto install tinytex` NÃO adiciona o bin ao PATH da sessão. Sintoma: figura falha, `tikz.lua` com `imgdata nil` por volta da linha 587 — é PATH, não pacote faltando. Antes de qualquer render/preview, prependa ao PATH:
   - Windows: `$HOME/AppData/Roaming/TinyTeX/bin/windows`
   - Linux/macOS: `~/.TinyTeX/bin/<plataforma>`
   Instalação local: `quarto install tinytex` e depois `tlmgr install standalone pgf pgfplots dvisvgm xcolor amsmath amsfonts`.

3. **CI precisa de `chrome-headless-shell`.** O grafo mermaid de pré-requisitos no `index.qmd` trava o render de PDF em runners Ubuntu. Em `.github/workflows/publish.yml`, inclua o passo `run: quarto install chrome-headless-shell` **antes** do render/publish. Use `chrome-headless-shell`, não `chromium`.

4. **`styles.css` precisa do marcador SCSS.** Como está listado em `theme: [cosmo, styles.css]`, o Quarto ≥1.9 o trata como camada SCSS e **exige** `/*-- scss:rules --*/` na primeira linha; sem isso, o render inteiro quebra ("doesn't contain at least one layer boundary").

5. **`lang: pt` na raiz** do `_quarto.yml`, nunca dentro de `book:`.

6. **Branch `gh-pages` deve pré-existir** antes do primeiro workflow (`quarto-actions/publish@v2` aborta sem ela):
   ```
   git push origin $(git commit-tree $(git hash-object -t tree /dev/null) -m 'init gh-pages'):refs/heads/gh-pages
   ```

7. **No CI, o bin do TinyTeX NÃO está no PATH e `tlmgr` precisa se autoatualizar antes de instalar.** O passo `Preparar TeX` do `publish.yml` deve, **antes** do render:
   - localizar `pdflatex` com `command -v` (ou `find ~ -name pdflatex` **sem** `-type f`, pois `pdflatex`/`tlmgr` são **symlinks** e `-type f` os ignora), derivar o bin e adicioná-lo a `$GITHUB_PATH`;
   - rodar **`tlmgr update --self`** antes de `tlmgr install ...` — em TeX Live novo, o `tlmgr` empacotado recusa instalar com "tlmgr itself needs to be updated" e **todo** `tlmgr install` falha em silêncio, deixando faltar `pgfplots.sty` e o binário `dvisvgm`;
   - linkar os binários em `/usr/local/bin` (sempre no PATH) como rede de segurança e **verificar** com `kpsewhich pgfplots.sty`/`standalone.cls` e `dvisvgm --version` (sem `|| true`, para falhar alto). O template do TikZ sempre faz `\usepackage{pgfplots}`, então **toda** figura precisa de `pgfplots`.

## Validação por capítulo (antes do commit)

1. `quarto render capitulos/volNN/capNN-*.qmd --to html` sem erros nem warnings novos
2. Todas as figuras TikZ renderizaram (nenhum placeholder de erro)
3. Toda `@chave` citada existe em `referencias.bib`
4. Capítulo listado no `_quarto.yml` e status atualizado no `ROADMAP.md`
5. Seção 🔎 Historiografia em Foco presente, com pelo menos duas interpretações contrastadas e fonte/autor citado
6. Exercícios com soluções colapsáveis completas, incluindo ao menos uma questão no estilo ENEM/vestibular
7. Datas, nomes e balizas temporais conferidos; sem anacronismos flagrantes
