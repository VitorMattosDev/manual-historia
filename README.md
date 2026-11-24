# Manual de História

Manual educacional aberto e abrangente de **História**, em português brasileiro, parte da série *Manuais de Ciências*. Cobre **História Geral (Mundo) integrada à História do Brasil**, em ordem cronológica, com atenção aos temas e ao estilo de vestibulares e do ENEM. Livro [Quarto](https://quarto.org) com saída dupla **HTML + PDF**, publicado via GitHub Actions em GitHub Pages.

- **Escopo:** 15 volumes, 91 capítulos, em 3 fases (ver [`ROADMAP.md`](ROADMAP.md)).
- **Público:** do leitor curioso ao estudante de ensino médio, pré-vestibular e graduação; sem pré-requisitos.

## Como construir localmente

Pré-requisitos: [Quarto](https://quarto.org) ≥ 1.9 e uma distribuição TeX (TinyTeX). As figuras usam a extensão TikZ com patches locais em `_extensions/danmackinlay/tikz/` — **nunca** rode `quarto add`/`quarto update` sobre ela.

```bash
# adicione o bin do TinyTeX ao PATH da sessão (Windows)
export PATH="$HOME/AppData/Roaming/TinyTeX/bin/windows:$PATH"

quarto preview          # servidor local com recarga
quarto render           # gera _book/ (HTML + PDF)
```

## Geração assistida por IA

O manual é escrito capítulo a capítulo com o **Claude Code**, seguindo a fila de
[`ROADMAP.md`](ROADMAP.md) (capítulos com status ⬜/✅).

## Estrutura

- `capitulos/volNN/` — capítulos em `.qmd`.
- `_quarto.yml` — configuração do livro (filtro `danmackinlay/tikz` antes de `quarto`).
- `referencias.bib` + `referencias-abnt.csl` — bibliografia (ABNT).
- `.github/workflows/publish.yml` — build e deploy automáticos.

## Licença

Conteúdo sob **CC BY-SA**.
