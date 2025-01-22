# Modelo Conceitual do Sistema de Oficina Mecânica

## Descrição do Projeto Conceitual
Este projeto descreve o modelo conceitual para um sistema de controle e gerenciamento de ordens de serviço (OS) em uma oficina mecânica. O objetivo é organizar as entidades e relacionamentos necessários para gerenciar clientes, veículos, equipes de mecânicos, serviços, peças e ordens de serviço.

![Construindo um Esquema Conceitual para Banco De dados](https://github.com/user-attachments/assets/70248d60-7b0a-40fa-8395-935c522e2181)


## Modelo Conceitual

### Entidades e Atributos

1. **Cliente:** Representa os clientes que levam veículos para conserto ou revisão.
   - **Atributos:**
     - ID_Cliente (identificador único)
     - Nome
     - Endereço
     - Telefone

2. **Veículo:** Representa os veículos pertencentes aos clientes.
   - **Atributos:**
     - ID_Veiculo (identificador único)
     - Placa
     - Modelo
     - Ano
     - ID_Cliente (relacionamento com Cliente)

3. **Mecânico:** Representa os mecânicos que realizam os serviços.
   - **Atributos:**
     - ID_Mecanico (identificador único)
     - Nome
     - Endereço
     - Especialidade

4. **Equipe:** Representa as equipes de mecânicos que trabalham em uma OS.
   - **Atributos:**
     - ID_Equipe (identificador único)
     - Nome_Equipe

5. **Serviço:** Representa os serviços realizados.
   - **Atributos:**
     - ID_Servico (identificador único)
     - Descricao
     - Valor_Mao_de_Obra

6. **Peça:** Representa as peças utilizadas nos serviços.
   - **Atributos:**
     - ID_Peca (identificador único)
     - Descricao
     - Valor

7. **Ordem de Serviço (OS):** Representa as ordens de serviço criadas para cada veículo.
   - **Atributos:**
     - ID_OS (identificador único)
     - Numero
     - Data_Emissao
     - Data_Conclusao
     - Valor_Total
     - Status
     - ID_Veiculo (relacionamento com Veículo)
     - ID_Equipe (relacionamento com Equipe)

### Relacionamentos

1. **Cliente** 1:N **Veículo** (Um cliente pode ter vários veículos).
2. **Veículo** 1:N **Ordem de Serviço (OS)** (Um veículo pode ter várias ordens de serviço).
3. **Equipe** 1:N **Ordem de Serviço (OS)** (Uma equipe pode trabalhar em várias ordens de serviço).
4. **Mecânico** N:M **Equipe** (Um mecânico pode fazer parte de várias equipes e vice-versa).
5. **Serviço** N:M **Ordem de Serviço (OS)** (Uma OS pode conter vários serviços e um serviço pode estar presente em várias OS).
6. **Peça** N:M **Ordem de Serviço (OS)** (Uma OS pode conter várias peças e uma peça pode estar presente em várias OS).
