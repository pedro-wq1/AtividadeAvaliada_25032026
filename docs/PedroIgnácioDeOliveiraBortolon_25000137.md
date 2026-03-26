# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: *Pedro Ignácio De Oliveira Bortolon*  
RA: *25000137*  
Data: *25/03/2026*  

---

# 1. Definição do MVP
Meu MVP está focado na parte de vendas a prazo e no controle de contas a receber na farmácia. 
A ideia é garantir que toda venda com pagamento futuro seja registrada de maneira correta e acompanhada pelo sistema.

Dentro desse escopo, o sistema permite identificar ou cadastras os clientes, registrar as vendas, definir quando a venda será a prazo e gerar automaticamente uma conta a receber com data de vencimento e status. 
Além disso o sistema possibilita consultar essas contas e registrar seus pagamentos.

Fora disso ficam algumas funcionalidade do sistema que não fazem parte desse MVP, como o controle completo de estoque, o gerenciamento de compras com fornecedores, contas a pagar e relatórios gerenciais mais complexos. 
Essas partes não foram incluidas para manter o focoem um fluxo especifico.

Minha escolha foi essa pois o controle de vendas a prazo é uma parte crítica da operação, já que impacta diretamente o fluxo de caixa e exige organização para evitar atrasos e problemas.

---

# 2. Regras de Negócio (mínimo: 5)
Liste e descreva **cada RN** de forma clara.

**RN01 — Toda venda a prazo deve gerar uma conta a receber**
         O sistema deve criar um lançamento financeiro automaticamente ao registrar uma venda a prazo.
**RN02 — Contas devem possuir data de vencimento obrigatória**
         Nenhuma conta a receber pode ser registrada sem data de vencimento.
**RN03 — Contas vencidas devem ser marcadas como atrasadas**
         O sistema deve automaticamente mudar o status para "Atrasada" quando ultrapassar a data de vencimento.
**RN04 — Cliente é obrigatório para venda a prazo**
         Não pode realizar vendas a prazo sem cliente identificado.
**RN05 — Pagamento altera o status da conta**
         Quando o pagamento for registrado, a conta deve ser marcada como "Recebida".

---

# 3. Requisitos Funcionais (mínimo: 8)
Liste os requisitos funcionais do seu MVP.

**RF01 — Cadastrar cliente**  
**RF02 — Consultar cliente**  
**RF03 — Registrar venda**  
**RF04 — Registrar venda a prazo**  
**RF05 — Gerar conta a receber automaticamente**  
**RF06 — Consultar contas a receber**  
**RF07 — Registrar pagamentos de conta**  
**RF08 — Atualizar status da conta automaticamente**  

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)
Liste os RNFs do sistema conforme seu MVP.

**RNF01 — Desempenho**
          O sistema deve atualizar o status das contas de forma automatica, sem atrapalhar a performance.
**RNF02 — Segurança**
          Somente usuários autorizados podem acessar informações financeiras.
**RNF03 — Confiabilidade**
          O sistema deve garantir que os dados financeiros não sejam perdidos.
**RNF04 — Usabilidade**
          As operações financeiras devem ser simples e rápidas para o usuário.

---

# 5. Casos de Uso (mínimo: 10)
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
- os 10 casos
- relação entre eles e atores
- pelo menos 3 includes
- pelo menos 3 extends

<img width="409" height="869" alt="image" src="https://github.com/user-attachments/assets/127e2739-81a9-4471-8947-b13e04e48f56" />

---

# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---

## **UCXX — Nome do Caso de Uso**
**Ator(es):**  
**Descrição:**  
**Pré-condições:**  
**Pós-condições:**  

### Fluxo Principal
1.  
2.  
3.  
4.  

### Fluxos Alternativos / Exceções
- FA01 —  
- FA02 —  

### Relacionamentos
- **Include:** (listar quando aplicável)  
- **Extend:** (listar quando aplicável)  

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.

---

> Repita essa estrutura para **todos os seus casos de uso** (mínimo 10).


