# 🔄 Fluxo de Integração — CORTANA + ASK

**Versão:** 2.0  
**Tipo:** Documentação de Fluxo Integrado  
**Status:** ✅ Operacional

---

## O Que É Este Documento?

Este documento explica como CORTANA e ASK trabalham **juntos** para garantir projetos de sucesso. Nenhum agente trabalha isolado em projetos críticos.

---

## Arquitetura de Integração

```
Usuário pede projeto
        ↓
    [ASK] Diagnóstico Inicial
    (4h) Análise de riscos
        ↓
    [CORTANA] Produz TAP + Docs
    (5-10 dias) + Código + Planos
        ↓
    [ASK] Valida: Segurança
    (24-48h) + Performance + Arquitetura
        ↓
  Pass? → Entrega Pronta
  Fail? → CORTANA Ajusta
        ↓
    Usuário Aprova + Executa
```

---

## Matriz de Decisão: Qual Agente Chamar?

| Você Precisa De | Chamar | Motivo |
|---|---|---|
| TAP para projeto novo | CORTANA | Produção formal |
| Entender erro em produção | ASK | Diagnóstico |
| Validar SQL antes de produção | ASK | Code review |
| Documentação técnica completa | CORTANA | Entregável |
| Saber como resolver N+1 query | ASK | Análise + recomendação |
| Implementar integração Oracle-Tasy | CORTANA + ASK | Produção + validação |
| Revisar plano de testes | ASK | Verificação |
| Criar plano de rollback | CORTANA | Entregável |
| Análise de logs | ASK | Diagnóstico |
| Comparar 2 arquiteturas | ASK | Avaliação |

---

## 3 Casos de Uso Completos

### CASO 1: Projeto Novo (Reforma Tributária)

**Cenário:** Implementar Reforma Tributária no Tasy com prazo legal até jan/2026

---

#### Passo 1: ASK Diagnóstico Inicial (4 horas)

**O que ASK faz:**
```
Analisa:
- Versão do Tasy (HTML5 vs. Delphi)
- Prazo legal (< 6 meses)
- Integrações existentes
- Equipe disponível
- Ambiente de testes
```

**ASK retorna:**
```markdown
## Diagnóstico — Reforma Tributária

### Riscos Identificados
- 🔴 CRÍTICO: Prazo apertado (< 6 meses)
- 🔴 CRÍTICO: Incompatibilidade Delphi vs. HTML5
- 🟡 MÉDIO: Carga horária consultoria limitada

### Recomendação
Iniciar projeto estruturado com CORTANA imediatamente.
Planejar para 10-12 semanas.
```

---

#### Passo 2: CORTANA Produz TAP + Documentação (5-10 dias)

**O que CORTANA faz:**
```
Produz:
✅ TAP versão 01 (13 seções)
✅ Documentação de Parametrização
✅ Plano de Implantação
✅ Plano de Testes
✅ Cronograma detalhado
✅ Matriz RACI
```

**Inclui no TAP:**
- Objetivo: Implementar Reforma Tributária
- Escopo: Parametrização + Integração + Testes
- Riscos: Integrados do diagnóstico ASK
- Cronograma: 10-12 semanas

---

#### Passo 3: ASK Valida TAP + Documentação (3 dias)

**O que ASK valida:**
```
Checklist:
✅ Riscos estão bem documentados?
✅ Cronograma é realista?
✅ Dependências estão mapeadas?
✅ Critérios de aceite são SMART?
✅ Plano de rollback é executável?
```

**ASK retorna:**
```markdown
Status: ✅ APROVADO com Observações

Sugestões de Ajuste:
1. Adicionar risco R7 (indisponibilidade Portal Governo)
2. Aumentar prazo Testes de 3 para 4 semanas
3. Detalhar critério C6 com evidências

Validações Críticas:
✅ Segurança: Plano inclui validação de NF-e
✅ Performance: Testes de carga mapeados
✅ Rollback: Plano reversível em < 2h
✅ Compliance: Atende prazos legais

Recomendação: Aprovar TAP com ajustes listados.
```

---

#### Passo 4: Execução com Acompanhamento

**Durante Implementação:**
- CORTANA produz configurações, documentação, testes
- ASK valida cada entregável crítico (24-48h)
- TAP é atualizado continuamente (v01 → v01.1 → v01.2)

**Timeline:**
```
Semana 1-2: Kick-off + Parametrização (CORTANA)
            ↓ ASK valida segurança
Semana 3-6: Configuração + Integração (CORTANA)
            ↓ ASK valida performance
Semana 7-8: Testes (CORTANA)
            ↓ ASK valida plano teste
Semana 9-10: Ajustes (CORTANA + ASK)
Semana 11: Go-live
           ↓ ASK valida em produção
```

---

### CASO 2: Problema Crítico em Produção

**Cenário:** NF-e não está sendo emitida. Erro: ORA-01536

**Timeline Total:** 1 dia (vs. semanas sem integração)

---

#### Passo 1: ASK Diagnóstico Urgente (30 minutos)

**O que ASK faz:**
```
Analisa imediatamente:
- Erro ORA-01536
- Logs do último erro
- Mudanças recentes
- Queries afetadas
```

**ASK retorna:**
```markdown
## Diagnóstico Urgente — NF-e ORA-01536

### Causa Raiz (Confirmada)
Schema TASY_HAC atingiu limite de quota na tablespace USERS.

### Opções de Solução

🟢 OPÇÃO A — Aumentar Quota (15 minutos)
- Vantagem: Resolve imediato, zero downtime
- Desvantagem: Problema volta em 3-6 meses
- Impacto: Nenhum em produção

🟡 OPÇÃO B — Migrar Schema (2 horas + 30 min downtime)
- Vantagem: Solução permanente
- Desvantagem: Requer downtime
- Impacto: 30 min sem NF-e

🔴 OPÇÃO C — Limpeza + Aumentar (1 hora, sem downtime)
- Vantagem: Balanceado (curto + médio prazo)
- Desvantagem: Requer limpeza de dados
- Impacto: Zero downtime, ganho permanente

### Recomendação
✅ Executar OPÇÃO A AGORA (produção urgente)
📅 Agendar OPÇÃO B para próxima manutenção
```

---

#### Passo 2: CORTANA Documenta Solução (Paralelo)

Enquanto Usuário executa Opção A:

**O que CORTANA faz:**
```
Produz em paralelo:
✅ Plano detalhado para Opção B
✅ Script SQL de limpeza
✅ Documentação de Contingência
✅ Atualização de Procedimento Operacional
```

**Documentação criada:**
- Migration Script (testado em homologação)
- Rollback Script
- Checklist de validação

---

#### Passo 3: ASK Valida Script de Migração (1 hora)

Antes de executar em produção:

**O que ASK valida:**
```
✅ Script é idempotente? (seguro re-executar)
✅ Índices serão recriados? (sem perda de performance)
✅ Permissões estão corretas?
✅ Rollback é possível em < 15 min?
✅ Testes cobrem cenários críticos?
```

**ASK retorna:**
```markdown
Status: ✅ APROVADO

Validações:
✅ Script é idempotente
✅ Índices preservados
✅ Permissões OK
✅ Rollback testável em 10 min

Recomendação: Pronto para deploy em próxima manutenção.
```

---

#### Timeline Completa

```
10:00 - Erro identificado (NF-e não emite)
10:05 - ASK chamado para diagnóstico
10:35 - ASK retorna: Causa = quota USERS esgotada
10:40 - Opção A executada (aumentar quota)
10:55 - NF-e volta a funcionar
11:00 - CORTANA começa a documentar Opção B
14:00 - Script de migração pronto
15:00 - ASK valida script
16:00 - Documentação concluída
17:00 - TAP de incidente fechado

Resultado: Problema resolvido em 7 horas (vs. semanas de retrabalho)
```

---

### CASO 3: Refatoração de Código Legado

**Cenário:** Integração Tasy-Oracle está lenta. Need otimizar.

**Timeline Total:** 2 semanas

---

#### Passo 1: ASK Análise (2 dias)

**O que ASK faz:**
```
Examina:
- Código PL/SQL
- Planos de execução
- Índices
- Queries N+1
```

**ASK retorna:**
```markdown
## Análise Performance — Integração Tasy-Oracle

### Problemas Encontrados

1. 🔴 CRÍTICO: Loop sem índice (N+1 query)
   - Localização: Linha 45-60
   - Impacto: 10x mais lento (1000ms → 100ms potencial)
   
2. 🟡 MÉDIO: Função em WHERE clause
   - Localização: Linha 120
   - Impacto: Índice não usado

3. 🟢 BAIXO: Falta tratamento de erro

### Opções de Refatoração

**A — Refatoração Mínima** (< 1 dia)
- Usar JOIN ao invés de loop
- Benefício: 90% redução de tempo
- Impacto: Baixo (alteração localizada)
- Risco: Baixo (validação simples)

**B — Refatoração Completa** (1 semana)
- Reescrever com stored procedure
- Benefício: 95% redução + manutenção melhor
- Impacto: Médio (refatoração extensiva)
- Risco: Médio (testes extensivos)

### Recomendação
✅ Executar OPÇÃO A AGORA (ganho 90%)
📅 Agendar OPÇÃO B para próximo sprint
```

---

#### Passo 2: CORTANA Refatora (5 dias)

**O que CORTANA faz:**
```
Produz:
✅ Código refatorado (Opção A)
✅ Plano de Testes
✅ Script de rollback
✅ Documentação de mudanças
```

**Código final:**
- Versão otimizada com JOINs
- Testes unitários
- Comparação before/after (performance)

---

#### Passo 3: ASK Code Review (1 dia)

**O que ASK valida:**
```
Performance:
✅ Novo código é 92% mais rápido (validado em homologação)

Segurança:
✅ Sem SQL Injection
✅ Parametrização correta

Compatibilidade:
✅ Tasy HTML5 + Oracle 19c
✅ Sem regressão em outras queries

Rollback:
✅ Script pronto e testado
```

**ASK retorna:**
```markdown
Status: ✅ APROVADO

Validações:
✅ Performance: +92% (testado)
✅ Segurança: Pass (OWASP)
✅ Compatibilidade: OK
✅ Rollback: < 5 min

Recomendação: Pronto para produção.
```

---

#### Timeline Completa

```
Dia 1-2: ASK analisa código legado
Dia 3-7: CORTANA refatora (inclui testes)
Dia 8: ASK faz code review
Dia 9: Deploy em produção
Dia 10: ASK valida em produção (performance)

Resultado: +92% performance gain. Código mais limpo.
```

---

## Comunicação Formalizada

### CORTANA → ASK (Pedido de Validação)

```
Para: ASK
Assunto: Validação — Parametrização NF-e

Segue artefatos para validação:
- Documento de Parametrização (5 páginas)
- Plano de Testes (20 casos)
- Script de Rollback

Questões Específicas:
1. Segurança: Está parametrizado corretamente?
2. Performance: Vai impactar emissão?
3. Rollback: Plano é executável?

Prazo: Amanhã (go-live amanhã à noite)
Contato: João (joao.bruno@hac.com.br)
```

### ASK → CORTANA (Resultado Validação)

```
Para: CORTANA
Assunto: Validação CONCLUÍDA — Parametrização NF-e

Status: ✅ APROVADO com Observações

Validações Realizadas:
✅ Segurança: Parametrizado corretamente (auditoria realizada)
✅ Performance: Zero impacto em emissão
✅ Rollback: Plano é executável em < 5 min

Sugestões de Melhoria (não-bloqueadoras):
1. Adicionar validação de NF-e duplicada na parametrização
2. Documentar timeout máximo para fallback
3. Incluir teste de cancelamento

Conclusão: Aprovado para go-live. Sugestões são melhorias.
Contato: ASK
```

---

## TAP Vivo — Atualização Dinâmica

### Evolução do TAP

```
TAP v01 (Criado por CORTANA)
  └─ Contém: Objetivo, Escopo, Riscos iniciais, Cronograma

TAP v01.1 (Ajustado por ASK)
  └─ Adições: Novos riscos encontrados, Cronograma revisado

TAP v01.2 (Atualizado em Execução)
  └─ Atualizações: Datas reais, Entregas completadas

TAP v02 (Final)
  └─ Conclusão: Lições aprendidas, Go-live validado
```

### Exemplo: ASK Identifica Novo Risco

**Antes (TAP v01):**
```
Seção 10 — Riscos

R4: Carga horária de consultoria insuficiente
    Probabilidade: Média
    Mitigação: Monitorar consumo semanal
```

**ASK identifica:**
```
"Esquema Delphi + HTML5 tem incompatibilidade em NF-e"
```

**Depois (TAP v01.1):**
```
Seção 10 — Riscos

R4: Carga horária de consultoria insuficiente
    Probabilidade: Média
    Mitigação: Monitorar consumo semanal

R7: Incompatibilidade Delphi vs. HTML5 em funcionalidade NF-e [NOVO]
    Probabilidade: Média
    Impacto: Alto
    Mitigação: Validar em kick-off; acionar Philips se necessário
    Responsável: Eduardo Bianchet (Tasy Consultant)
```

---

## Checklist de Aprovação Final

**Antes de qualquer go-live, validar:**

### CORTANA Preparou
- [ ] TAP versão final (assinado)
- [ ] Documentação técnica completa
- [ ] Código pronto para produção
- [ ] Plano de rollback com script testado
- [ ] Treinamento documentado
- [ ] Histórico de versões preenchido

### ASK Aprovou
- [ ] ✅ Segurança: Passou validação (OWASP)
- [ ] ✅ Performance: Sem gargalos identificados
- [ ] ✅ Arquitetura: Riscos mitigados
- [ ] ✅ Testes: 100% cenários críticos cobertos
- [ ] ✅ Rollback: Testado e validado
- [ ] ✅ Documentação: Completa e clara

### Resultado
🟢 **PRONTO PARA PRODUÇÃO**

---

## SLA de Resposta — Quando Esperar

| Situação | CORTANA | ASK | Total |
|---|---|---|---|
| Projeto novo (médio) | 5-10 dias | 24-48h | 2-3 semanas |
| Produção urgente | - | < 2h | < 2h |
| Code review rotineiro | - | < 1 semana | < 1 semana |
| TAP apenas | 3-5 dias | 1-3 dias | 1 semana |

---

## Próximos Passos

1. **Qual projeto você quer iniciar?**
   - ASK faz diagnóstico inicial? Ou
   - CORTANA faz TAP logo?

2. **Existe código legado a analisar?**
   - ASK faz análise de performance

3. **Quer documentar processo existente?**
   - CORTANA cria documentação

---

## 🔗 Links Úteis

- ⬅️ [Voltar ao Portal Central](../README.md)
- ⚙️ [CORTANA v2.0 — Produção](../CORTANA/)
- 🔍 [ASK v2.0 — Análise](../ASK/)

---

**Integração ativa!** Use CORTANA para produzir + ASK para validar = Sucesso! 🚀
