# dotnet-unity-tests-plugin

Plugin de planejamento, revisão e criação de testes unitários para .NET, compatível com **Claude Code**, **GitHub Copilot CLI** e **Cursor**.

## Fluxo de uso

1. O agente de IA invoca `dotnet-tester-reviewer` → gera `test-plan.md`
2. O agente de IA invoca `dotnet-tester-creator` → lê o plano e implementa os testes
3. Para projetos independentes (marcados como paralelizáveis na seção 4 do plano), o agente pode invocar múltiplas instâncias do creator em paralelo

## Estrutura de diretórios multiplataforma

```text
dotnet-unity-tests/
├── .claude-plugin/plugin.json     # Manifest Claude Code
├── .cursor-plugin/plugin.json     # Manifest Cursor
├── plugin.json                    # Manifest Copilot CLI (raiz)
├── agents/                        # Agentes para Claude Code e Cursor (*.md)
│   ├── dotnet-tester-creator.md
│   └── dotnet-tester-reviewer.md
├── copilot-agents/                # Agentes para Copilot CLI (*.agent.md)
│   ├── dotnet-tester-creator.agent.md
│   └── dotnet-tester-reviewer.agent.md
└── skills/                        # Skills compartilhadas entre as 3 plataformas
    ├── dotnet-mstest/SKILL.md
    └── dotnet-xunit/SKILL.md
```

## Instalação

### Claude Code

```bash
/plugin marketplace add ArquitetoMovel/markv-ai-plugins
/plugin install dotnet-unity-tests-plugin@arquiteto-movel-plugins
```

### GitHub Copilot CLI

```bash
copilot plugin marketplace add ArquitetoMovel/markv-ai-plugins
copilot plugin install dotnet-unity-tests-plugin
```

### Cursor

Disponibilize via repositório de marketplace de time em **Dashboard → Settings → Plugins → Team Marketplaces → Import**, apontando para o repositório `markv-ai-plugins`.
