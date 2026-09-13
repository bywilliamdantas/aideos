# AIDE OS

App único (PWA) que reúne dois módulos de trabalho de campo:

- **Gerenciamento de Encerramento** — preenchimento de atendimentos e geração de relatórios de encerramento prontos para copiar no WhatsApp.
- **Solicitação Infraestrutura** — solicitação e acompanhamento de demandas de infraestrutura.

## Como funciona

Na primeira vez que o app é aberto, a tela inicial pede o **nome do técnico**. Esse nome fica salvo no aparelho e é reaproveitado automaticamente em todos os módulos — não é pedido novamente, a menos que o técnico toque em "Trocar" na tela inicial.

A partir da tela inicial, basta escolher um dos dois módulos e tocar em "Continuar".

## Estrutura do projeto

```
aide-os/
├── index.html                     # tela inicial (seleção de módulo + nome do técnico)
├── manifest.json                  # manifesto do PWA
├── sw.js                          # service worker (cache offline)
├── icons/                         # ícones do app
└── modulos/
    ├── encerramento/index.html    # módulo Gerenciamento de Encerramento
    └── infraestrutura/index.html  # módulo Solicitação Infraestrutura
```

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub e suba todo o conteúdo desta pasta na branch `main`.
2. Em **Settings → Pages**, em "Build and deployment", selecione **GitHub Actions** como origem.
3. O workflow em `.github/workflows/deploy.yml` já está pronto: a cada push na `main`, o app é publicado automaticamente.
4. A URL final fica no formato `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Status do desenvolvimento

- [x] Etapa 1 — Base do app (tela inicial, roteamento, nome persistente, estrutura de arquivos)
- [ ] Etapa 2 — Módulo de Encerramento + correção do texto de franquia do repetidor (2.0/3.0 x 4.0)
- [ ] Etapa 3 — Correção da Classificação (Andamento x Encerramento)
- [ ] Etapa 4 — Módulo de Solicitação Infraestrutura
- [ ] Etapa 5 — Fechamento do PWA (ícones, service worker, testes finais)
