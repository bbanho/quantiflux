# Guia de Instalação e Orientação para Agentes e Harnesses

Este documento orienta como agentes harness e executores devem carregar e utilizar a skill e o plugin Quantiflux.

---

## 1. Estrutura do Plugin e da Skill

* **Skill:** `multi-wave-agent-orchestration` (registrada no catálogo de skills do agente).
* **Plugin:** `plugins/hermes/index.js` (hook leve de inicialização do orquestrador).

---

## 2. Instalação em Agentes Harness

### Para Agentes baseados em CLI / Runtime
A skill é carregada dinamicamente via comando:

```bash
skill_view(name="multi-wave-agent-orchestration")
```

Para registrar o plugin no perfil ativo do seu harness:

```bash
cp -r plugins/hermes ~/.config/harness/plugins/quantiflux
```

### Configuração em arquivo JSON de Harness
Adicione o plugin à lista de plugins no arquivo de configuração do seu agente:

```json
{
  "plugin": [
    "quantiflux-orchestration",
    "/var/home/bruno/Documentos/quantiflux/plugins/hermes"
  ]
}
```

---

## 3. Diretrizes de Execução do Orquestrador

1. **Jamais escreva código no primeiro turno de uma nova feature.**
2. **Crie ou atualize o Plano Diretor:** `.hermes/plans/master_plan.md`.
3. **Mapeie as Ondas (Waves):**
   * Wave 0: Contratos e Tipos.
   * Wave 1: Persistência / Adapters.
   * Wave 2: Regras de Negócio / Services.
4. **Dispare a execução por Onda:** Use `delegate_task` para enviar aos subagentes apenas o contexto da Wave ativa.
5. **Execute a validação no Portão de Onda:** Testes unitários e estado Git limpo antes de avançar para a Wave seguinte.
