# 🤖 AGENTES v2.0 — Portal Central

**Versão:** 2.0  
**Data:** 29/06/2026  
**Responsável:** João Fábio Bruno (IT Coordination)  
**Status:** ✅ Operacional

---

## 📋 O Que É Este Repositório?

Este repositório documenta dois agentes de IA integrados que auxiliam no desenvolvimento de projetos de TI:

- **CORTANA** — Produção de Entregáveis (documentação, código, TAPs, planos)
- **ASK** — Análise e Validação Técnica (diagnóstico, code review, validação)

Ambos trabalham de forma integrada para garantir **qualidade**, **segurança** e **rastreabilidade** em projetos críticos.

---

## 🎯 Decisão Rápida: Qual Agente Chamar?

### Você precisa PRODUZIR algo?
→ **Chamar CORTANA**

✅ Exemplos:
- TAP (Termo de Abertura do Projeto)
- Documentação Técnica
- Código (SQL, PL/SQL, APIs)
- Plano de Implantação
- Plano de Testes
- Plano de Rollback
- Especificações Funcionais/Técnicas

---

### Você precisa ANALISAR ou VALIDAR algo?
→ **Chamar ASK**

✅ Exemplos:
- Diagnóstico de erro (ORA-01536, performance, timeout)
- Code review (SQL, Java, PL/SQL)
- Análise de logs e traces
- Validação de arquitetura
- Comparação de soluções
- Aprovação antes de go-live

---

### Você quer INTEGRAR os dois?
→ **Usar Fluxo de Integração**

✅ Exemplos:
- CORTANA produz → ASK valida → Entrega pronta
- Projeto novo do zero (diagnóstico → planejamento → validação)
- Problema crítico em produção (diagnóstico → solução → validação)

---

## 📚 Documentação

### 1️⃣ [CORTANA v2.0 — Assistente de Produção](./CORTANA/)
**Quando usar:** Para produzir entregáveis formais

**Contém:**
- Processo PDIVF estruturado (Descobrir → Planejar → Implementar → Verificar → Finalizar)
- Integração obrigatória com TAP
- Checklist de saída estruturado
- SLA definido (1-3 dias para documentação, 3-5 dias para TAP)
- Critérios de sucesso SMART

**[Abrir CORTANA →](./CORTANA/README.md)**

---

### 2️⃣ [ASK v2.0 — Copiloto Técnico](./ASK/)
**Quando usar:** Para análise e validação técnica

**Contém:**
- 5 modos de análise (Diagnóstico, Code Review, Validação, Logs, Arquitetura)
- Integração com CORTANA definida
- SLA claro (< 2h para urgente, < 24h para validação)
- Critérios de sucesso por tipo de análise
- Regras obrigatórias de conduta

**[Abrir ASK →](./ASK/README.md)**

---

### 3️⃣ [Fluxo de Integração — CORTANA + ASK](./FLUXO-INTEGRACAO/)
**Quando usar:** Para entender como os agentes trabalham juntos

**Contém:**
- Arquitetura integrada (diagrama)
- Matriz de decisão: qual agente chamar?
- 3 casos de uso completos (projeto novo, produção, refatoração)
- Comunicação formalizada entre agentes
- TAP vivo (atualização dinâmica)
- Checklist de aprovação final

**[Abrir Fluxo →](./FLUXO-INTEGRACAO/README.md)**

---

## 📊 Comparação Rápida

| Aspecto | CORTANA | ASK |
|---|---|---|
| **Modo** | Produção | Análise |
| **Implementa** | ✅ Sim | ❌ Não (orienta) |
| **Valida** | ❌ Não (produz) | ✅ Sim |
| **TAP** | ✅ Cria | 🟡 Contribui via CORTANA |
| **Documentação** | ✅ Produz | ❌ Não |
| **Code Review** | ❌ Não | ✅ Sim |
| **Diagnóstico** | ❌ Não | ✅ Sim |
| **Diagramas** | ✅ Cria (Mermaid) | 🟡 Sugere ajustes |

---

## 🚀 Como Começar

### Opção 1: Projeto Novo
1. Leia este README (2 min)
2. Abra [Fluxo de Integração](./FLUXO-INTEGRACAO/)
3. Siga "Caso 1: Projeto Novo"
4. Comece com ASK → diagnóstico

### Opção 2: Análise de Erro
1. Leia este README (2 min)
2. Abra [ASK v2.0](./ASK/)
3. Descreva o erro
4. ASK faz diagnóstico

### Opção 3: Documentação Urgente
1. Leia este README (2 min)
2. Abra [CORTANA v2.0](./CORTANA/)
3. Defina escopo e prazo
4. CORTANA começa produção

---

## 📋 Estrutura do Repositório

```
AGENTES-v2.0/
├── README.md                          # Este arquivo (Portal Central)
├── CORTANA/
│   ├── README.md                      # Documentação completa de CORTANA
│   └── exemplos/                      # (Opcional) Exemplos de uso
├── ASK/
│   ├── README.md                      # Documentação completa de ASK
│   └── exemplos/                      # (Opcional) Exemplos de análise
├── FLUXO-INTEGRACAO/
│   ├── README.md                      # Documentação de fluxo integrado
│   └── casos-uso/                     # (Opcional) Casos de uso detalhados
├── docs/
│   ├── RESUMO_ENTREGA.md              # Síntese completa de correções
│   ├── GUIA_IMPORTACAO_NOTION.md      # Instruções para Notion
│   └── RESUMO_1PAGINA.md              # Resumo executivo (1 página)
└── LICENSE                            # (Opcional) Licença do projeto
```

---

## ✅ Problemas Corrigidos (v2.0)

| Problema | Severidade | Solução |
|---|---|---|
| 🔴 Sobreposição CORTANA ↔ ASK | CRÍTICA | Responsabilidades separadas |
| 🔴 Sem integração entre agentes | CRÍTICA | Fluxo de integração criado |
| 🔴 TAP rastreabilidade ausente | CRÍTICA | Integração obrigatória com TAP |
| 🟡 Padrão único ausente | MÉDIO | Notion-flavored Markdown |
| 🟡 Checklists vagos | MÉDIO | Estruturados e específicos |

---

## 💡 Destaques v2.0

✨ **TAP Vivo:** Atualiza automaticamente conforme progresso  
✨ **Integração 100%:** Sem separação artificial entre agentes  
✨ **Rastreabilidade Total:** Tudo mapeado ao TAP  
✨ **SLA Transparente:** Sabe quanto tempo esperar  
✨ **Critérios Objetivos:** Métricas SMART, não opinião  
✨ **Padrão Único:** Markdown em tudo  

---

## 📞 Como Usar

### Passo 1: Escolha o Agente
Use a [Matriz de Decisão](#-decisão-rápida-qual-agente-chamar) acima

### Passo 2: Abra a Documentação
Clique no link correspondente ao agente

### Passo 3: Siga as Instruções
Cada agente tem processo e checklist claros

### Passo 4: Execute
CORTANA produz ou ASK valida conforme combinado

---

## 🎯 Próximos Passos Sugeridos

**Curto Prazo (Próxima Semana)**
- [ ] Ler este README e os 3 documentos principais
- [ ] Testar CORTANA com um projeto pequeno
- [ ] Testar ASK com um log/erro real
- [ ] Validar integração com caso real

**Médio Prazo (Próximo Mês)**
- [ ] Importar estrutura para Notion (se ainda não fez)
- [ ] Treinar time sobre novos agentes
- [ ] Documentar feedback de uso
- [ ] Criar template de pedido formal

**Longo Prazo (Próximo Trimestre)**
- [ ] Avaliar se SLAs estão sendo atendidos
- [ ] Identificar novas casos de uso
- [ ] Revisar e atualizar (v2.1, v2.2)
- [ ] Integrar com OpenProject (quando implementado)

---

## 📊 KPIs Sugeridos

Acompanhe após 30 dias de uso:

| KPI | Meta | Método |
|---|---|---|
| Taxa de aprovação (ASK) | ≥ 90% | Contar Pass/Fail |
| Tempo médio de entrega (CORTANA) | No SLA | Comparar datas |
| Integração bem sucedida | ≥ 95% | Contar casos sem ajustes |
| Satisfação do usuário | ≥ 4/5 | Feedback informal |

---

## 🔗 Links Rápidos

- 📖 [CORTANA v2.0 — Produção](./CORTANA/README.md)
- 🔍 [ASK v2.0 — Análise](./ASK/README.md)
- 🔄 [Fluxo de Integração](./FLUXO-INTEGRACAO/README.md)
- 📋 [Resumo Completo da Entrega](./docs/RESUMO_ENTREGA.md)
- 📄 [Resumo 1 Página](./docs/RESUMO_1PAGINA.md)

---

## 🆘 Suporte

**Dúvida sobre qual agente chamar?**  
→ Veja [Decisão Rápida](#-decisão-rápida-qual-agente-chamar)

**Quer integrar CORTANA + ASK?**  
→ Abra [Fluxo de Integração](./FLUXO-INTEGRACAO/)

**Precisa de exemplos práticos?**  
→ Veja [3 Casos de Uso](./FLUXO-INTEGRACAO/README.md#casos-de-uso)

**Encontrou um problema?**  
→ Abra uma [Issue](../../issues) neste repositório

---

## 📜 Histórico de Versões

| Versão | Data | Mudanças |
|---|---|---|
| 2.0 | 29/06/2026 | Integração CORTANA + ASK. TAP obrigatório. Fluxo estruturado. |
| 1.0 | 2026 | Versão anterior (descontinuada) |

---

## 👥 Autores

- **Concepção:** João Fábio Bruno (IT Coordination, HAC)
- **Análise Crítica:** Claude (Assistente)
- **Reformulação v2.0:** Claude (Assistente)

---

## 📍 Localização Institucional

- **Organização:** Sociedade Hospitalar Angelina Caron Ltda. (HAC)
- **Localização:** Campina Grande do Sul, Paraná, Brasil
- **Sistemas Principais:** Tasy HTML5, Oracle Database, Apache NiFi
- **Gerente de Projetos:** Antonio Borges Neto
- **Analista TI:** João Fábio Bruno

---

## 📝 Licença

Este projeto está sob domínio interno do HAC. Para uso fora da organização, solicitar autorização.

---

**Última atualização:** 29/06/2026  
**Status:** ✅ Operacional  
**Versão:** 2.0

🚀 **Pronto para começar?** Escolha um agente acima e comece!
