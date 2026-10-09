# Quantiflux: Meta-Engineering & Multi-Wave Agent Orchestration

**Quantiflux** é um framework metanalítico de engenharia de software desenhado para gerenciar enxames de subagentes autônomos por meio de **Planos Diretores** e **Execução em Ondas (Wave-based Execution)**.

O objetivo do Quantiflux é prevenir a crise conceitual em projetos de grande escala, garantindo que qualquer mudança drástica seja tratada de forma determinística, auditável e segura antes mesmo de escrever a primeira linha de código.

---

## 🏛️ Arquitetura em 4 Camadas de Abstração

```
[ Conceitual ]  ──►  [ Estratégico ]  ──►  [ Tático ]  ──►  [ Operacional ]
  (Visão/Regras)       (Plano/Ondas)       (Subagentes)       (Execução/Gate)
```

1. **Nível Conceitual (Engenheiro Sênior / Visão Master):**
   * Formuilação da tese arquitetural e modelagem de entidades imutáveis e invariantes do domínio.
   * Estabelece a linha de defesa contra acoplamento prematuro e *context drift*.

2. **Nível Estratégico (Orquestrador de Plano Diretor):**
   * Converte a tese no **Master Engineering Plan** (`.hermes/plans/master_plan.md`).
   * Estrutura a decomposição em **Ondas Sequenciais (Waves)**: *Wave 0 (Core Contracts)* -> *Wave 1 (Adapters)* -> *Wave N (Features/Services)*.

3. **Nível Tático (Gerenciador de Contexto & Subagentes):**
   * Isola estritamente o contexto por Onda para evitar a contaminação de contexto (*context bleed*).
   * Dispara e monitora subagentes táticos especialistas via `delegate_task`.

4. **Nível Operacional (Operadores Especialistas / Executores):**
   * Executa a escrita de código e testes focados exclusivamente no manifesto da Onda.
   * Validação rígida nos **Portões de Transição da Onda (Wave Quality Gates)**: compilação, suíte de testes e integridade do repositório (`git status`).

---

## 📂 Arquivos no Repositório

* **`quantiflux_operation_diagram.bpmn.xml`**: Diagrama BPMN 2.0 formal cobrindo o fluxo temporal e inter-camadas da operação. Pode ser aberto diretamente no [bpmn.io](https://bpmn.io) ou caminhos compatíveis.
* **`SKILL.md`**: Definição da skill `multi-wave-agent-orchestration` registrada no agente Hermes.

---

## 🚀 Como Visualizar o BPMN
1. Abra o navegador em [bpmn.io/demo](https://demo.bpmn.io/).
2. Carregue o arquivo `quantiflux_operation_diagram.bpmn.xml`.
3. Navegue entre as 4 raias (Lanes) que delimitam a interação temporal e hierárquica entre as camadas de agentes.
