# Video Studio

Ambiente de edição de vídeo com ffmpeg.

## Estrutura
- `input/` — vídeos e áudios originais
- `output/` — arquivos processados
- `scripts/` — scripts reutilizáveis de ffmpeg

## Ferramentas disponíveis
- `ffmpeg` / `ffprobe` — edição, conversão, análise de vídeo
- `python3` — automação e scripts
- `mediainfo`, `exiftool` — metadados (se instalados)
- `convert` / `identify` (ImageMagick) — imagens/thumbnails

## Convenções
- Sempre inspecionar o arquivo com `ffprobe` antes de editar
- Preservar os originais em `input/`, nunca sobrescrever
- Saídas vão em `output/` com nomes descritivos
- Para operações destrutivas, confirmar antes de executar

## Tarefas comuns
- Cortar trecho: `ffmpeg -i input.mp4 -ss HH:MM:SS -to HH:MM:SS -c copy output.mp4`
- Converter formato: `ffmpeg -i input.mkv output.mp4`
- Extrair áudio: `ffmpeg -i input.mp4 -q:a 0 -map a output.mp3`
- Redimensionar: `ffmpeg -i input.mp4 -vf scale=1920:1080 output.mp4`
- Juntar vídeos: usar arquivo de lista com `ffmpeg -f concat`
- Adicionar legenda: `ffmpeg -i input.mp4 -vf subtitles=legenda.srt output.mp4`
