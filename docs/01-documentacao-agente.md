# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas têm dificuldade em controlar seus gastos, planejar seu orçamento e identificar hábitos financeiros que prejudicam sua saúde financeira.

### Solução
> Como o agente resolve esse problema de forma proativa?

Desenvolver um assistente virtual para ajudar usuários no controle de gastos e planejamento de orçamento, permitindo registrar despesas, organizar gastos por categoria, gerar análises simples sobre consumo, emitir alertas quando o orçamento estiver próximo do limite e oferecer recomendações básicas com base nos hábitos financeiros do usuário.

### Público-Alvo
> Quem vai usar esse agente?

O público-alvo deste projeto são pessoas que desejam melhorar o controle de suas finanças pessoais, mas que não possuem conhecimento avançado em educação financeira ou dificuldade em organizar seus gastos.

---

## Persona e Tom de Voz

### Nome do Agente
Scorea

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Educativo e paciente 
- Usar exemplos praticos 
- Nunca julgar os gastos dos clientes 

### Tom de Comunicação
> Formal, informal, técnico, acessível?
Acessivel e didatico

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] --> B["Streamlit (Interface Visual)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV mockados|

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos  no contexto 
- [ ] Admite quando não sabe algo 
- [ ] Não faz recomendações de investimento 
- [ ] Foca apenas em ajudar e não aconselhar

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de investimento
- Não acessa dados bancarios reais e/ ou sensiveis
- Não substitui um profissional certificado 
