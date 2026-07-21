# sdlc-test-agent

Agente `test` do [agentic-sdlc-reference-architecture](https://github.com/leandrosflora/agentic-sdlc-reference-architecture) — implementação operacional do papel `agent_role == "test"` definido em `policies/agent_authorization.rego`.

## Responsabilidade

Escreve testes e emite parecer independente de verificação; dono do **Verification gate** (testes determinísticos, cobertura de critérios, mutation/quality thresholds e evidências reproduzíveis).

## Autorização (OPA)

- `project.read`: permitido, restrito ao próprio `project_id`.
- Escrita de testes e emissão de parecer: previstas na matriz de capacidades do governance; ainda não codificadas como regra própria em `agent_authorization.rego` (hoje só `project.read` é avaliado para este papel).
- Sem permissão para escrever código de aplicação, alterar arquitetura/contratos ou acionar deploy.

## Status

Scaffold inicial (Python/.pyproj). Lógica do agente ainda não implementada.

## Referências

- Governança e gates: [docs/governance.md](https://github.com/leandrosflora/agentic-sdlc-reference-architecture/blob/main/docs/governance.md)
- Política: [policies/agent_authorization.rego](https://github.com/leandrosflora/agentic-sdlc-reference-architecture/blob/main/policies/agent_authorization.rego)
