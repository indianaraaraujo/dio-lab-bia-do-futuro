# Documentação do Agente

## Caso de Uso

### Problemaa
> Qual problema financeiro seu agente resolve?

Muitas pessoas têm dificuldade em enteder conceitos básicos de finanças pessoais, como reserva de emergêcia, tipos de investimentos e como organizar seus gastos. 

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente educativo que explica conceitos financeiros de forma simples, usando os dados do próprio cliente como exemplo prático, mas sem dar recomendação de investimento

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
