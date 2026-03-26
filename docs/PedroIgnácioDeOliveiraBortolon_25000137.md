# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: *Pedro Ignácio De Oliveira Bortolon*  
RA: *25000137*  
Data: *25/03/2026*  

---

# 1. Definição do MVP
Meu MVP está focado na parte de vendas a prazo e no controle de contas a receber na farmácia. A ideia é garantir que toda venda com pagamento futuro seja registrada de maneira correta e acompanhada pelo sistema. O sistema permite identificar ou cadastras os clientes, registrar as vendas, definir quando a venda será a prazo e gerar automaticamente uma conta a receber com data de vencimento e status. Além disso o sistema possibilita consultar essas contas e registrar seus pagamentos. Fora disso ficam algumas funcionalidade do sistema que não fazem parte desse MVP, como o controle completo de estoque, o gerenciamento de compras com fornecedores, contas a pagar e relatórios mais complexos. Essas partes não foram incluidas para manter o focoem um fluxo especifico. Minha escolha foi essa pois o controle de vendas a prazo é uma parte crítica da operação, já que impacta diretamente o fluxo de caixa e exige organização para evitar atrasos e problemas.

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

---

## **UC01 — Registrar vendas**
**Ator(es): Atendente**  
**Descrição: Registra uma venda no sistema**  
**Pré-condições: Usuário logado**  
**Pós-condições: Venda registrada**  

### Fluxo Principal
1. Atendente inicia a venda 
2. Informa os itens
3. Sistema calcula o valor
4. Venda é registrada

### Fluxos Alternativos / Exceções
- FA01 —  Dados inválidos -> sistema solicita correção

### Relacionamentos
- **Include: - ** 
- **Extend: Registrar venda a prazo**  

<img width="133" height="306" alt="image" src="https://github.com/user-attachments/assets/54dd84cc-9b91-4612-99fd-d3d7824d713a" />

---

## **UC02 — Identificar cliente**
**Ator(es): Atendente**  
**Descrição: Localiza cliente no sistema**  
**Pré-condições: Nenhuma**  
**Pós-condições: Cliente identificado**  

### Fluxo Principal
1. Informar CPF e nome
2. Sistema busca cliente
3. Exibe o resultado

### Fluxos Alternativos / Exceções
- FA01 —  Cliente não encontrado

### Relacionamentos
- **Include: - ** 
- **Extend: Cadastrar cliente**  

<img width="280" height="314" alt="image" src="https://github.com/user-attachments/assets/9a0c6431-7ac4-4027-b85d-070c5da3747c" />

---

## **UC03 — Cadastrar cliente**
**Ator(es): Atendente**  
**Descrição: Cadastrar novo cliente**  
**Pré-condições: Cliente não encontrado**  
**Pós-condições: Cliente salvo**  

### Fluxo Principal
1. Inserir dados
2. Validar dados
3. Salvar

### Fluxos Alternativos / Exceções
- FA01 —  Dados inválidos

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="250" height="314" alt="image" src="https://github.com/user-attachments/assets/1c671570-0553-4ad9-90d8-a7a227b91e1f" />

---

## **UC04 — Registrar vendas a prazo**
**Ator(es): Atendente**  
**Descrição: Registra venda com pagamento futuro**  
**Pré-condições: Cliente identificado**  
**Pós-condições: Conta gerada**  

### Fluxo Principal
1. Atendente inicia a venda 
2. Identifica o cliente
3. Insere os itens
4. Escolhe pagamento a prazo
5. Define o vencimento
6. Confirma

### Fluxos Alternativos / Exceções
- FA01 — Cliente não cadastrado
- FA02 — Data inválida 

### Relacionamentos
- **Include: Identificar cliente, Gerar conta a receber** 
- **Extend: Registrar venda**  

<img width="301" height="546" alt="image" src="https://github.com/user-attachments/assets/6e907bab-2ba8-4e20-ad49-0b3ebf466a52" />

---

## **UC05 — Gerar conta a receber**
**Ator(es): Sistema**  
**Descrição: Cria registro financeiro da venda a prazo**  
**Pré-condições: Venda a prazo realizada**  
**Pós-condições: Conta registrada**  

### Fluxo Principal
1. Receber dados da venda 
2. Criar conta
3. Definir status como "Aberta"

### Fluxos Alternativos / Exceções
- FA01 — Falha no registro

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="180" height="306" alt="image" src="https://github.com/user-attachments/assets/a5938d2c-3a5a-4a06-9ec2-c1e8bb6e9b04" />

---

## **UC06 — Consultar contas a receber**
**Ator(es): Financeiro**  
**Descrição: Visualiza contas**  
**Pré-condições: Usuário logado**  
**Pós-condições: Lista exibida**  

### Fluxo Principal
1. Acessa módulo
2. Sistema lista as contas
3. Aplica filtros

### Fluxos Alternativos / Exceções
- FA01 — Nenhuma conta encontrada

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="189" height="400" alt="image" src="https://github.com/user-attachments/assets/ec756874-0888-4300-aed2-27f27cdbebc7" />

---

## **UC07 — Registrar pagamento**
**Ator(es): Financeiro**  
**Descrição: Registra pagamento**  
**Pré-condições: Conta existente**  
**Pós-condições: Conta atualizada**  

### Fluxo Principal
1. Seleciona conta
2. Confirma pagamento
3. Sistema registra data
4. Atualiza status

### Fluxos Alternativos / Exceções
- FA01 — Conta já paga 

### Relacionamentos
- **Include: Atualizar status** 
- **Extend: Emitir comprovante**  

<img width="254" height="284" alt="image" src="https://github.com/user-attachments/assets/55c17959-77bf-4e5e-90e6-60a7d901e6dc" />

---

## **UC08 — Atualizar status da conta**
**Ator(es): Sistema**  
**Descrição: Atualiza status**  
**Pré-condições: Conta existente**  
**Pós-condições: Status atualizado**  

### Fluxo Principal
1. Verifica pagamento
2. Atualiza status

### Fluxos Alternativos / Exceções
- FA01 — Conta vencida -> status atrasado

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="413" height="322" alt="image" src="https://github.com/user-attachments/assets/ff28391c-7725-4554-85d0-9a2d7adea77f" />

---

## **UC09 — Listar contas vencidas**
**Ator(es): Financeiro**  
**Descrição: Mostra contas atrasadas**  
**Pré-condições: Sistema ativo**  
**Pós-condições: Lista exibida**  

### Fluxo Principal
1. Acessa sistema
2. Sistema filtra vencidas
3. Exibe lista

### Fluxos Alternativos / Exceções
- FA01 — Nenhuma conta vencida

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="241" height="314" alt="image" src="https://github.com/user-attachments/assets/148a6c1b-2ea0-4de8-a19d-8b1ebd51282c" />

---

## **UC10 — Emitir comprovante de pagamento**
**Ator(es): Financeiro**  
**Descrição: Gerar comprovante**  
**Pré-condições: Pagamento realizado**  
**Pós-condições: Comprovante gerado**  

### Fluxo Principal
1. Solicita comprovante
2. Sistema gera documento
3. Exibe

### Fluxos Alternativos / Exceções
- FA01 — Erro na geração 

### Relacionamentos
- **Include: - ** 
- **Extend: - **  

<img width="216" height="314" alt="image" src="https://github.com/user-attachments/assets/e2343ef1-8bba-4d35-8bda-3bf42f3b6013" />

---


