# Claude Video Studio

Um ambiente de edição de vídeo assistido por IA, onde o [Claude Code](https://claude.ai/code) executa operações com `ffmpeg` diretamente via linguagem natural.

## Ideia

A edição de vídeo por linha de comando é poderosa, mas exige memorizar uma sintaxe complexa. Este projeto resolve isso: você descreve o que quer fazer em português (ou inglês), e o Claude traduz isso em comandos `ffmpeg` precisos, executa, e entrega o resultado.

Nenhuma interface gráfica. Nenhum clique. Só conversa.

## Como usar

1. Coloque seus vídeos/áudios na pasta `input/`
2. Abra o terminal nesta pasta
3. Rode `claude`
4. Descreva o que quer fazer, por exemplo:
   - *"Corta do minuto 1:30 até 3:45 e exporta em mp4"*
   - *"Junta todos os vídeos da pasta input em ordem alfabética"*
   - *"Extrai o áudio desse vídeo em mp3"*
   - *"Redimensiona para 1080p mantendo a proporção"*
   - *"Adiciona a legenda legenda.srt ao vídeo"*

Os resultados aparecem em `output/`.

## Estrutura

```
claude-video-studio/
├── input/       # vídeos e áudios originais
├── output/      # arquivos processados
├── scripts/     # scripts ffmpeg reutilizáveis
└── CLAUDE.md    # contexto e instruções para o Claude
```

## Pré-requisitos

- [Claude Code](https://claude.ai/code) instalado
- `ffmpeg` instalado (`sudo apt install ffmpeg` ou `brew install ffmpeg`)

## Por que isso funciona bem

O projeto inclui um `.claude/settings.json` com permissões pré-aprovadas para `ffmpeg`, `ffprobe` e ferramentas de arquivo. Isso significa que o Claude executa os comandos sem interromper o fluxo pedindo confirmação a cada passo.

O `CLAUDE.md` fornece contexto sobre a estrutura do projeto e convenções, então o Claude sabe onde buscar os arquivos e onde salvar os resultados sem precisar ser instruído toda vez.

## Licença

MIT
