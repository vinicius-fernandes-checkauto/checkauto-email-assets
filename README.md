# checkauto-email-assets

Imagens públicas usadas nos templates de e-mail da Checkauto.

Um e-mail HTML não leva as imagens dentro dele. Cada `<img>` é um link que o Gmail ou o Outlook do cliente baixa quando a pessoa abre a mensagem. Por isso as imagens precisam estar num endereço público com https. Este repositório guarda esses arquivos, e o [jsDelivr](https://www.jsdelivr.com/) os entrega por CDN, direto do GitHub.

> **Solução temporária.** O repositório foi criado às pressas para a Expo FENAUTO (novembro de 2026), porque não dava para esperar a hospedagem oficial. O ideal é mover as imagens para um servidor da Checkauto (site, Firebase Hosting ou bucket) e atualizar os links nos templates.

## Campanhas

### `fenauto/`: e-mail pós-consulta da Expo FENAUTO

Quem visita o stand da Checkauto na Expo FENAUTO ganha um voucher de consulta veicular grátis. Depois da consulta, a pessoa recebe este e-mail com o relatório em PDF anexado. O e-mail agradece a visita e convida a pessoa a conhecer as outras modalidades de consulta no site.

- **Assunto:** Sua consulta veicular está aqui
- **Plataforma de disparo:** SQAD Mail
- **Template:** `02_email-fenauto.html`, enviado à parte. O template não fica neste repositório, só as imagens.

| Arquivo | Onde aparece no e-mail |
|---|---|
| `logo-checkauto.png` | Logo azul no topo |
| `hero-bg.png` | Fundo do bloco azul de abertura, com os padrões da marca |
| `hero-relatorio.png` | Ilustração do relatório de consulta, com a placa e os itens "Nada consta" |
| `icon-file.png` | Ícone do cartão "Sua consulta está pronta" |
| `icon-shield.png`, `icon-eye.png`, `icon-badge.png` | Pilares Segurança, Transparência e Confiança |
| `logo-checkauto-branco.png` | Logo no rodapé |
| `social-*.png` | Ícones das redes sociais no rodapé |

As imagens estão em resolução dobrada (2x), para ficarem nítidas em telas de alta densidade. As cores e a tipografia seguem o Manual de Marca Checkauto 2026.

## Como usar as imagens

Formato do link:

```
https://cdn.jsdelivr.net/gh/vinicius-fernandes-checkauto/checkauto-email-assets@<tag>/<pasta>/<arquivo>
```

Exemplo:

```
https://cdn.jsdelivr.net/gh/vinicius-fernandes-checkauto/checkauto-email-assets@v1/fenauto/logo-checkauto.png
```

## Como atualizar uma imagem

O jsDelivr guarda em cache, de forma permanente, cada arquivo de uma tag. **Trocar um arquivo e continuar usando a mesma tag não muda o que o cliente vê.** Para atualizar:

1. Substitua o arquivo, faça o commit e o push.
2. Crie uma tag nova: `git tag v2 && git push origin v2`.
3. Troque `@v1` por `@v2` nos links do template e suba o template de novo no SQAD Mail.

Não apague nem renomeie arquivos de tags já usadas. E-mails já enviados continuam apontando para eles.

## Versões

| Tag | Conteúdo |
|---|---|
| `v1` | Imagens iniciais da campanha Expo FENAUTO |
