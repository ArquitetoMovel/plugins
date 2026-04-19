# markV AI Plugins

Catálogo de plugins de IA multiplataforma com suporte a **Claude Code**, **GitHub Copilot CLI** e **Cursor**.

Cada plugin é publicado simultaneamente para os três hosts a partir do mesmo repositório, reaproveitando *skills* compartilhadas e disponibilizando agentes adaptados ao formato de cada plataforma.

## Catálogo

| Plugin | Categoria | Descrição | Plataformas |
| --- | --- | --- | --- |
| [`dotnet-unity-tests-plugin`](./dotnet-unity-tests) | testing | Planejador, revisor e criador de testes unitários para .NET (xUnit / MSTest v3). | Claude Code · Copilot CLI · Cursor |

## Plugins

### dotnet-unity-tests-plugin

Automação completa do ciclo de testes unitários em soluções .NET.

- **Agentes:** `dotnet-tester-reviewer` (analisa a solução e gera `test-plan.md`) e `dotnet-tester-creator` (implementa os testes conforme o plano, com meta de 80% de cobertura).
- **Skills:** `dotnet-mstest` (para `net472`) e `dotnet-xunit` (para `net8.0+`).
- **Palavras-chave:** `dotnet`, `unit-tests`, `xunit`, `mstest`, `testing`, `csharp`.
- **Instalação e detalhes:** [`dotnet-unity-tests/README.md`](./dotnet-unity-tests/README.md).

## Instalação genérica

Substitua `<plugin-name>` pelo nome do plugin desejado.

```bash
# Claude Code
/plugin marketplace add ArquitetoMovel/markv-ai-plugins
/plugin install <plugin-name>@arquiteto-movel-plugins

# GitHub Copilot CLI
copilot plugin marketplace add ArquitetoMovel/markv-ai-plugins
copilot plugin install <plugin-name>
```

Para **Cursor**, importe este repositório em *Dashboard → Settings → Plugins → Team Marketplaces → Import*.

## Como contribuir com um novo plugin

1. Siga a estrutura documentada em [`CLAUDE.md`](./CLAUDE.md) (manifests por host, pastas `agents/`, `copilot-agents/`, `skills/`).
2. Acrescente o plugin nos quatro `marketplace.json` do repositório (`./marketplace.json`, `.claude-plugin/`, `.cursor-plugin/`, `.github/plugin/`).
3. Adicione uma linha na tabela **Catálogo** e uma subseção em **Plugins** neste arquivo.

## Referências

- Especificação do repositório: [`spec-modular-plugins.md`](./spec-modular-plugins.md)
- Claude Code: [`claude-plugins-ref.md`](./claude-plugins-ref.md) · [`claude-plugins-market-place.md`](./claude-plugins-market-place.md)
- Copilot CLI: [`copilot-plugins-ref.md`](./copilot-plugins-ref.md) · [`copilot-plugins-market-place.md`](./copilot-plugins-market-place.md)
- Cursor: [`cursor-plugins-ref.md`](./cursor-plugins-ref.md)

## Autor

Alexandre Danelon (Arquiteto Móvel) — MIT License
