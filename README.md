# Flying Studio — Revista Digital

Revista digital interativa do **Grupo Flying** (Flying Studio · NID Studio · Rinno Films · OGDI), implementada a partir do projeto Claude Design *"Flying Studio - Revista Digital.dc.html"*.

## Como usar

O site é 100% estático. Basta servir a pasta e abrir `index.html`:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

Navegação: setas ← → do teclado, botões na tela, ou toque nas laterais (mobile). Páginas de case (Livigno, Ousy, Mirage) são acessadas pelos botões "Explorar" na página **Os Cases**.

## Estrutura

| Arquivo | Descrição |
|---|---|
| `index.html` | Página publicada (revista completa, rail de miniaturas oculto) |
| `Flying Studio - Revista Digital.dc.html` | Fonte original do design (formato design-canvas) |
| `support.js` | Runtime do design-canvas (carrega React de `vendor/`) |
| `deck-stage.js` | Web component do deck de páginas (escala 1920×1080, navegação, print) |
| `image-slot.js` | Componente de slots de imagem da galeria |
| `vendor/` | React 18.3.1, ReactDOM, Babel standalone e pdf.js 3.11.174 vendorizados (sem dependência de CDN) |
| `assets/` | Imagens, logos e PDFs da revista |

## Notas sobre os assets

Os arquivos foram importados do projeto Claude Design. A API de leitura limita cada arquivo a 256 KiB, então:

- Imagens maiores que o limite foram **recuperadas parcialmente** (recorte da região decodificável do JPEG). A maioria preserva 50–95% do conteúdo.
- `assets/nid-portfolio-2026.pdf` foi **reconstruído** (13 páginas) a partir das grades de referência do projeto — resolução reduzida.
- `assets/nid-livigno-apresentacao.pdf` é um **placeholder** de 2 páginas (o original de 44 páginas excede o limite de download).
- `foto03-scaled-mrfncik2.jpg` (fundo da capa) e `assets/ogdi-predio.png` foram substituídos por imagens equivalentes do próprio acervo, pois os originais não puderam ser recuperados.
- Logos NID (versão escura) regenerada a partir da versão branca íntegra.

Para restaurar a qualidade máxima, basta substituir esses arquivos pelos originais em alta resolução — os nomes e caminhos foram mantidos.

Fontes (Google Fonts) e players do Vimeo (página *Rinno · Em cartaz*) são carregados da internet.
