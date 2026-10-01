# Web para Todos

Site estático para um trabalho de extensão universitária sobre acessibilidade e inclusão digital. Foi feito com HTML5, CSS3 e JavaScript puro, sem instalação de dependências.

## Como abrir

1. Extraia o ZIP, preservando a estrutura das pastas.
2. Abra `index.html` no navegador. A página, o painel de acessibilidade, o laboratório e o quiz funcionam localmente.
3. Se o navegador restringir vídeos ou legendas ao abrir arquivos diretamente, inicie um servidor local na pasta do projeto. Por exemplo, com Python instalado: `python -m http.server 8000`. Depois acesse `http://localhost:8000`.

Não é preciso publicar o site para apresentá-lo em um computador. Todos os estilos e scripts são locais.

## Onde colocar os vídeos e as legendas

| Conteúdo | Caminho esperado |
| --- | --- |
| Vídeo principal em MP4 | `videos/video-principal.mp4` |
| Legenda em português, formato WebVTT | `legendas/video-principal.vtt` |
| Vídeo com interpretação em Libras | `videos/video-libras.mp4` |

Os dois arquivos MP4 **não estão incluídos**. Enquanto não forem adicionados, a página mostra espaços informativos em vez de um player quebrado. O vídeo principal usa o elemento HTML `<video>` e a legenda é ligada com `<track kind="captions">` em `index.html`.

O arquivo `.vtt` incluído é **um modelo** para o roteiro sugerido. Depois da gravação, sincronize os tempos, confira todas as falas e sons relevantes e atualize também o texto em “Leia o roteiro / transcrição sugerida”. Se o vídeo trouxer informação visual que não aparece no áudio, descreva-a na narração ou na transcrição. O vídeo em Libras deve acompanhar fielmente o conteúdo do vídeo principal.

Se preferir outros nomes de arquivos, altere os caminhos nos elementos `<source>` e `<track>` de `index.html`.

## Estrutura

```text
Web-para-Todos/
├── index.html                 Página completa
├── css/styles.css             Layout, responsividade e alto contraste
├── js/main.js                 Painel, laboratório, quiz e vídeos
├── images/                    Capa do vídeo e ícone do site
├── legendas/video-principal.vtt  Legenda modelo
└── videos/LEIA-ME.txt         Instruções para os MP4
```

## Recursos incluídos

- Navegação por teclado, link “Pular para o conteúdo principal” e foco visível.
- Estrutura semântica com `header`, `nav`, `main`, `section`, `article`, `footer` e `button`.
- Uso pontual de WAI-ARIA para rótulos, estados (`aria-pressed`, `aria-expanded`) e resultado do quiz (`role="status"`).
- Painel com texto maior ou menor, alto contraste, destaque de links e restauração. As escolhas são guardadas neste navegador, quando o armazenamento estiver disponível.
- Demonstrações de imagem, teclado e vídeo no laboratório; quiz de três perguntas.
- Preferência de movimento reduzido respeitada pelo CSS.

## Antes de apresentar

Teste a página com Tab, Shift+Tab, Enter e Espaço. Confira o contraste e a leitura com um leitor de telas. Depois de incluir os vídeos, verifique a sincronia das legendas, a transcrição e a interpretação em Libras com pessoas que usam esses recursos. A presença de controles de acessibilidade, por si só, não substitui essa validação.

## Referências

- [W3C WAI — WCAG em resumo](https://www.w3.org/WAI/standards-guidelines/wcag/glance/)
- [W3C WAI — mídia acessível](https://www.w3.org/WAI/media/av/)
