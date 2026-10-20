# Apresentação executiva · Sr. Jorge

Versão cliente da apresentação executiva do Diagnóstico Estratégico de IA, publicada no GitHub Pages com acesso por senha.

## Como funciona

- O repositório guarda só o pacote **cifrado** (`site/presentation.enc`), cifrado com AES-256-GCM e PBKDF2 (600 mil iterações) no próprio navegador. Não há conteúdo em texto plano aqui.
- A senha não está no repositório. Ela é usada apenas na geração do pacote, a partir de uma máquina com acesso à pasta do cliente.
- O push para `main` dispara o deploy (GitHub Actions → GitHub Pages). Não há etapa de build.

## Atualizar a apresentação

Na pasta `executions/scripts/apresentacao-html` do repositório SrJorge:

```bash
PRESENTATION_PASSWORD="<senha>" node build.mjs --pages
```

O pacote sai em `tmp/publicar-apresentacao/`. Copie `site/` para este repositório, substituindo o conteúdo anterior, depois:

```bash
git add site
git commit -m "chore: atualiza apresentação executiva"
git push
```

Nunca copie a pasta `html/` desta apresentação para cá: ela contém a versão do apresentador, com notas internas.
