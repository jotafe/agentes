# ⚙️ CORTANA v2.0 — Assistente de Produção

**Versão:** 2.0  
**Tipo:** Agente de Produção de Entregáveis  
**SLA:** 1-3 dias (documentação), 3-5 dias (TAP)  
**Status:** ✅ Operacional

---

## O Que É CORTANA?

CORTANA é um agente especializado em **produzir entregáveis de alta qualidade** para projetos de TI. Ela transforma requisitos em documentação, código, configurações e planos prontos para execução imediata.

**Responsabilidade:** PRODUZIR ✅  
**Responsabilidade NÃO:** Validar ❌ (isto é trabalho de ASK)

---

## Quando Chamar CORTANA

✅ **CORTANA é indicada quando você precisa:**

- Termo de Abertura do Projeto (TAP) completo
- Documentação Técnica estruturada
- Código (SQL, PL/SQL, APIs, scripts)
- Plano de Implantação
- Plano de Testes
- Plano de Rollback
- Especificações Funcionais
- Especificações Técnicas
- Diagramas e Fluxogramas (Mermaid)
- Documentos Word/PDF/PowerPoint
- Configurações de sistema
- Checklist de validação

❌ **NÃO chamar CORTANA para:**
- Diagnosticar erros (chamar ASK)
- Analisar código legado (chamar ASK)
- Ler e interpretar logs (chamar ASK)
- Dúvidas técnicas (chamar ASK)

---

## Processo de Trabalho: PDIVF

CORTANA segue um processo estruturado em 5 fases:

### 1️⃣ P — DESCOBRIR (Coleta de Requisitos)

**O que acontece:**
- Levantamento do objetivo do projeto
- Mapeamento de escopo (incluso vs. fora do escopo)
- Identificação de stakeholders
- Listagem de dependências técnicas
- Registro de restrições e premissas
- Definição de critérios de aceite

**Você fornece:**
- Descrição do projeto
- Contexto técnico
- Prazos
- Restrições conhecidas

**CORTANA entrega:**
- Resumo executivo (3-5 linhas)
- Premissas listadas
- Riscos iniciais

---

### 2️⃣ P — PLANEJAR (Estruturação)

**O que acontece:**
- Divisão em fases principais
- Definição de marcos
- Estimativa de cronograma
- Mapeamento de responsáveis (RACI)
- Lista de artefatos a produzir
- Ambiente e acesso necessários

**Você fornece:**
- Equipe disponível
- Ambiente de teste
- Consultor (se necessário)

**CORTANA entrega:**
- Cronograma com datas
- Matriz RACI
- Checklist de artefatos

---

### 3️⃣ I — IMPLEMENTAR (Produção)

**O que acontece:**
- Criação de documentação técnica
- Geração de scripts
- Escrita de APIs
- Criação de TAP (13 seções)
- Desenho de arquitetura
- Especificação de parâmetros

**Você fornece:**
- Feedback durante produção
- Acesso a ambientes
- Informações técnicas

**CORTANA entrega:**
- Documentação em Markdown
- Código funcional
- Diagramas
- TAP v01

⚠️ **IMPORTANTE:** Antes de finalizar, CORTANA chama ASK para validação

---

### 4️⃣ V — VERIFICAR (Garantia de Qualidade)

**O que acontece:**
- Criação de Plano de Testes
- Definição de casos de teste
- Critérios de aceite verificáveis
- Smoke tests
- Queries de validação

**Você fornece:**
- Ambiente para testes
- Dados de teste

**CORTANA entrega:**
- Plano de Testes completo
- Checklist de validação
- Queries de verificação

---

### 5️⃣ F — FINALIZAR (Preparação)

**O que acontece:**
- Criação de Plano de Rollback
- Documentação de lições aprendidas
- Identificação de pendências
- Próximos incrementos
- Documentação de Operação
- TAP final

**Você fornece:**
- Feedback final
- Aprovação

**CORTANA entrega:**
- Rollback step-by-step
- Checklist pré-go-live
- Documento de Encerramento
- TAP v02 (final)

---

## Integração com TAP (Importante!)

**CORTANA atualiza o TAP continuamente:**

Cada fase produz mapeamento:
```
Seção 2 (Escopo) → Fase I completa
Seção 6 (Cronograma) → Datas reais vs. planejadas
Seção 11 (Entregas) → Documentação entregue
Seção 12 (Aceite) → Critérios validados
```

**Se ASK encontrar um risco:**
```
Seção 10 (Riscos) → Novo risco adicionado
                  → Mitigação documentada
                  → Cronograma ajustado se necessário
```

---

## Padrão de Documentação

Toda documentação segue este padrão:

```markdown
# Título da Funcionalidade

## Objetivo
(O quê e por quê - 2-3 linhas)

## Escopo
- Incluso: ...
- Fora do escopo: ...

## Pré-requisitos
- Acesso necessário
- Versões de software
- Conhecimento esperado

## Implementação / Conteúdo
(Passo a passo, tabelas, exemplos)

## Testes / Validação
(Como verificar que funcionou)

## Rollback / Reversão
(Como desfazer se necessário)

## Observações
(Contexto adicional importante)

## Histórico de Versões
| Versão | Data | Mudanças |
```

---

## Checklist de Saída

Antes de CORTANA entregar qualquer artefato, ela valida:

### Documentação
- [ ] Título claro e descritivo
- [ ] Objetivo resumido (2-3 linhas)
- [ ] Escopo: incluso vs. fora do escopo explícito
- [ ] Pré-requisitos completos
- [ ] Passo a passo testado
- [ ] Exemplos práticos inclusos
- [ ] Testes/validação documentados
- [ ] Rollback definido
- [ ] Histórico de versões preenchido
- [ ] Mapeado ao TAP

### TAP
- [ ] 13 seções completas
- [ ] Tabelas estruturadas (não texto puro)
- [ ] RACI implícita (quem faz o quê)
- [ ] Datas reais vs. planejadas
- [ ] Status de cada entrega claro
- [ ] Assinaturas e aprovações

### Código/Scripts
- [ ] Comentários explicativos
- [ ] Boas práticas aplicadas
- [ ] Tratamento de erros
- [ ] Versionamento (v01, v02...)
- [ ] Script de rollback

---

## Critérios de Sucesso Objetivos

| Artefato | Sucesso É | Evidência |
|---|---|---|
| **TAP** | 13 seções completas | Documento 100% preenchido |
| **Documentação** | Pronta para implementação sem dúvidas | Dev consegue seguir sem questões |
| **Código** | Executável, testado, com rollback | Testes passam; log de execução |
| **Plano de Testes** | 100% cenários mapeados | Todos paths críticos cobertos |

---

## SLA — Quanto Tempo Esperar

| Tipo | SLA | Exemplo |
|---|---|---|
| Documentação simples | 1-3 dias | Guia de parametrização |
| Projeto pequeno | 1 semana | Implementação de feature |
| Projeto médio | 2 semanas | Projeto completo com TAP |
| Projeto complexo | 2-4 semanas | Integração de 2+ sistemas |
| TAP apenas | 3-5 dias | TAP sem código |

---

## Como Chamar CORTANA

**Forneça:**

1. **Objetivo** (1 frase clara)
   - Exemplo: "Implementar parametrização de NF-e no Tasy"

2. **Escopo inicial** (o que está incluso)
   - Exemplo: "Parâmetros de emissão, integração municipal, testes"

3. **Restrições** (prazos, equipe, ambiente)
   - Exemplo: "Prazo: 2 semanas. Tasy HTML5. Consultoria: 20h"

4. **Responsável de aprovação**
   - Exemplo: "Antonio Borges Neto"

---

## Perguntas Frequentes

**P: Quanto tempo leva?**  
R: Depende do escopo. Veja tabela SLA acima.

**P: Posso fazer ajustes depois?**  
R: Sim. Histórico de versões registra mudanças. TAP é atualizado.

**P: Preciso de validação?**  
R: Sim. CORTANA chama ASK antes de finalizar entrega crítica.

**P: E se ficar incompleto?**  
R: CORTANA avisa quais informações faltam. Fornece checklist de ações.

---

## Próximos Passos

1. **Defina seu projeto** (objetivo claro)
2. **Escolha o artefato** (TAP? Documentação? Código?)
3. **Reúna informações** (escopo, restrições, prazos)
4. **Chame CORTANA** com as informações acima
5. **Acompanhe via TAP** (vivo e atualizado)

---

## 🔗 Links Úteis

- ⬅️ [Voltar ao Portal Central](../README.md)
- 🔍 [ASK v2.0 — Análise](../ASK/)
- 🔄 [Fluxo de Integração](../FLUXO-INTEGRACAO/)

---

**Pronto para começar?** Defina seu projeto e chame CORTANA! 🚀
