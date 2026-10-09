# Quantiflux: Meta-Engineering & Multi-Wave Agent Orchestration

Framework metanalítico de engenharia de software para orquestração de enxames de subagentes autônomos por meio de **Planos Diretores** e **Execução por Ondas (Wave-based Execution)**.

![Arquitetura Quantiflux](assets/quantiflux_architecture.svg)

---

## Estrutura do Repositório

```
quantiflux/
├── README.md                           # Documentação principal
├── quantiflux_operation_diagram.bpmn.xml # Diagrama BPMN 2.0 formal
├── assets/
│   └── quantiflux_architecture.svg     # Diagrama vetorial SVG
├── docs/
│   ├── AGENT_HARNESS_GUIDE.md          # Guia de instalação e operação para Agentes
│   └── abntex2/                        # Documentação em TeX/LaTeX (padrão ABNT)
│       ├── main.tex                    # Arquivo principal ABNT
│       ├── capitulo1_introducao.tex
│       ├── capitulo2_arquitetura.tex
│       ├── capitulo3_orquestracao_ondas.tex
│       └── capitulo4_conclusao.tex
└── plugins/
    └── hermes/                         # Plugin JS para Hermes e OpenCode
        ├── package.json
        └── index.js
```

---

## As 4 Camadas do Quantiflux

1. **Nível Conceitual (Tese & Invariantes):** Modelagem formal do sistema e definição dos contratos imutáveis do domínio.
2. **Nível Estratégico (Plano Diretor & Waves):** Elaboração do Master Engineering Plan e decomposição em Ondas sequenciais.
3. **Nível Tático (Isolamento de Contexto & Fanout):** Disparo de subagentes táticos (`delegate_task`) com contexto filtrado por Onda.
4. **Nível Operacional (Execução & Wave Gates):** Execução local de código/testes e verificação rigorosa nos Portões de Onda.

---

## Documentação Técnica e Artigo ABNT

A documentação acadêmica e formal no padrão ABNT (utilizando `abntex2`) encontra-se no diretório `docs/abntex2/`.

Para compilar o documento PDF único:

```bash
cd docs/abntex2/
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

---

## Operação por Agentes (Hermes / OpenCode / Claude Code)

Consulte o guia dedicado em [`docs/AGENT_HARNESS_GUIDE.md`](docs/AGENT_HARNESS_GUIDE.md) para detalhes de instalação e inclusão da skill no catálogo do seu harness.
