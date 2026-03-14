# Manager Plane v2 Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `Book.toml`, `docs/glossary.md`, `docs/non_negotiables.md`, `spec/epistemic_state_spec.md`, `spec/ghost_record_spec.md`, `spec/continuous_verifier_spec.md`, `spec/closure_fraud_spec.md`, `spec/unified_stack_spec.md`

---

## 1. Objetivo

Este documento define o **Manager Plane v2** como plano de controle **não-chat**, **tipado** e **dirigido a eventos** do andar de governança epistêmica.

Seu papel é coordenar transições entre estados epistêmicos sem violar o cânone: preservar ausência estruturada (Ghost Records), submeter continuidade ao Continuous Verifier, rotear regimes epistêmicos (ok/doubt/not) e impedir fechamento ilegítimo via Closure Guard.

---

## 2. Fronteira do componente

O Manager Plane v2:

- **coordena** decisões de continuidade;
- **despacha** ações tipadas para componentes especializados;
- **registra** eventos, recibos e evidências de governança;
- **não substitui** Verifier, Router, Ghost Engine ou Closure Guard.

O Manager Plane v2 **não é**:

- interface conversacional;
- LLM soberano;
- engine de inferência textual livre.

---

## 3. CÂNON (normativo neste repositório)

Esta seção consolida o que já está fixado no cânone e deve ser tratado como obrigatório para implementações conformantes.

### 3.1 Forma canônica e continuidade

1. Raciocínio é governado como **transição entre estados epistêmicos**, não como geração de texto.  
2. O estado epistêmico inclui, no mínimo: claims, evidence, obligations, ghosts, provenance, branches, status e budgets.  
3. Ghost Record é objeto de primeira classe (não null, não TODO), com identidade, origem, obrigações e ciclo de vida.

### 3.2 Governança contínua

4. O **Continuous Verifier** julga admissibilidade de transições de forma contínua e pode retornar `admit`, `admit_with_doubt`, `repair_required`, `escalate`, `reject`, `closure_blocked`.  
5. Continuidade e fechamento são direitos distintos: transição pode ser admissível sem ser elegível para closure.

### 3.3 Regimes epistêmicos e roteamento

6. O regime epistêmico canônico é `{ok, doubt, not}`; `doubt` é primeira classe e não pode ser colapsado em `not`.  
7. O **Epistemic Router** existe para decidir o regime de continuidade e deve ser respeitado pelo Manager Plane.

### 3.4 Fechamento e fraude de fechamento

8. Closure é ato governado (não mero “output emitido”).  
9. Closure deve ser bloqueado quando houver ausência crítica não resolvida/dispensada/escalada.  
10. Concluir apesar de dependência crítica não resolvida caracteriza **Closure Fraud**.

### 3.5 Pilha unificada e alocação de poder

11. O Manager Plane vive no 4º andar (epistemic governance) e coordena, sem colapsar papéis dos outros componentes.  
12. LLM pode propor; não pode autorizar sozinho continuidade, supressão de dúvida, apagamento de ghost ou fechamento.

---

## 4. Contrato operacional do Manager Plane v2 (PROPOSTA desta spec)

> Esta seção é proposta de contrato explícito para implementação. Ela **não cria ontologia paralela**: apenas operacionaliza termos já canônicos.

### 4.1 Entradas tipadas

O Manager Plane v2 recebe:

- `event` (fato/solicitação estruturada);
- `state_ref` (referência ao Epistemic State corrente);
- `intent` (objetivo operacional da transição);
- `policy_context` (regras e limites aplicáveis).

### 4.2 Saídas tipadas

O Manager Plane v2 emite:

- `action` (comando estruturado para componente-alvo);
- `receipt` (resultado governável e auditável);
- `witness_request` (quando testemunho externo é exigido);
- `routing_decision` (`ok`/`doubt`/`not`) quando a decisão estiver sob sua responsabilidade de orquestração.

### 4.3 Álgebra mínima de ações (proposta inicial)

Ações canônicas suportadas:

- `Delegate`
- `RequestEvidence`
- `SpawnGhost`
- `ResolveGhost`
- `EscalateGhost`
- `AdvancePointer`
- `BlockClosure`
- `Terminate`

Regra de alinhamento canônico:

- `SpawnGhost`/`ResolveGhost`/`EscalateGhost` operam sobre **Ghost Record** (não sobre entidade alternativa);
- `AdvancePointer` é condicionado por verificação de admissibilidade;
- `BlockClosure` é obrigatório quando houver `closure_blocked` ou dependência crítica em aberto.

### 4.4 Protocolo de decisão (proposta)

Para cada evento:

1. Carregar `x_t` (estado epistêmico atual).  
2. Identificar transição proposta `T`.  
3. Consultar Epistemic Router para regime (`ok`/`doubt`/`not`) quando aplicável.  
4. Submeter `T` ao Continuous Verifier.  
5. Se decisão for `closure_blocked`, emitir `BlockClosure` e registrar obrigações.  
6. Se decisão for `admit_with_doubt`, preservar ghosts/obrigações e seguir em regime `doubt`.  
7. Se decisão for `escalate`, emitir ação de escalonamento e registrar pendência explícita.  
8. Só permitir fechamento quando precondições de closure estiverem satisfeitas.

### 4.5 Invariantes do Manager Plane v2 (propostos)

- **I1 — Sem bypass de verificação:** nenhuma transição governada avança sem caminho de decisão verificável.
- **I2 — Sem apagamento silencioso:** ghost ativo não desaparece sem operação explícita de ciclo de vida.
- **I3 — Dúvida preservada:** `doubt` não é reclassificado para `ok` sem evidência/justificativa registrada.
- **I4 — Fechamento governado:** toda tentativa de closure passa por guardas de legitimidade.
- **I5 — Rastreabilidade:** todo efeito de governança produz receipt vinculável a evento e estado.

---

## 5. Alinhamento explícito entre componentes (sem ontologia paralela)

### 5.1 Manager Plane ↔ Epistemic State

- Manager Plane não “inventa estado alternativo”; opera sobre o Epistemic State canônico e seus campos normativos.

### 5.2 Manager Plane ↔ Ghost Records

- Ghost Records permanecem no estado e no ciclo de vida definido em `ghost_record_spec`; Manager Plane apenas orquestra ações sobre eles.

### 5.3 Manager Plane ↔ Continuous Verifier

- Verifier decide admissibilidade; Manager Plane decide despacho de ação com base nessa decisão.

### 5.4 Manager Plane ↔ Epistemic Router

- Router define regime epistêmico da continuidade; Manager Plane aplica esse regime ao fluxo operacional.

### 5.5 Manager Plane ↔ Closure Guard

- Closure Guard mantém autoridade para bloquear fechamento; Manager Plane deve honrar bloqueio e registrar consequência operacional.

---

## 6. Questões em aberto (não normativas)

1. **Fronteira Router/Manager:** Router embutido no Manager ou componente separado obrigatório?  
2. **Granularidade de `AdvancePointer`:** toda progressão exige verificação completa ou há classes de avanço leve?  
3. **Álgebra mínima final:** os oito verbos propostos são realmente primitivos ou parte é açúcar sintático?  
4. **Witnesses:** quando testemunho externo é obrigatório por política versus apenas recomendável?  
5. **Cadência de verificação:** custo/latência aceitos para verificação contínua em cenários de alto volume?  
6. **Crítica de ghost para closure:** qual critério computável mínimo para classificar criticalidade em produção?

---

## 7. Critérios de conformidade

Uma implementação está conforme esta spec se, no mínimo:

1. mantém o Manager Plane como camada não-chat e tipada;
2. opera sobre Epistemic State, Ghost Records, Router, Verifier e Closure Guard sem redefinir seus conceitos;
3. impede bypass de verificação e de bloqueio de closure;
4. preserva `doubt` como regime explícito;
5. garante trilha auditável (`event` → `decision` → `action` → `receipt`).

---

## 8. Resumo

O Manager Plane v2 é a orquestração de governança epistêmica: ele coordena transições, mas não usurpa autoridade dos componentes canônicos. Esta spec separa claramente **cânone** (o que já vale), **proposta** (contrato operacional implementável) e **questões em aberto** (o que ainda precisa pesquisa), mantendo uma única ontologia em todo o repositório.
