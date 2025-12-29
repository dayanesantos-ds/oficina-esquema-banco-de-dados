## 📊 Projeto de Modelagem Conceitual de Banco de Dados para Oficina Mecânica

Desenvolvido como parte de um desafio da DIO de modelagem de banco de dados, cujo objetivo é construir um esquema conceitual para um sistema de gestão de execução de ordens de serviço em uma oficina mecânica.
O modelo foi criado com base na narrativa fornecida no desafio, identificando entidades, atributos e relacionamentos essenciais para o funcionamento do sistema.

## 🖼️ Diagrama Conceitual
![Página 1](https://github.com/dayanesantos-ds/oficina-esquema-banco-de-dados/blob/main/imagens/diagrama-oficina.png)


### 🎯 Objetivo do Projeto
Criar o modelo conceitual de um sistema responsável por:

Registrar ordens de serviço (OS)

Associar veículos, clientes e equipes de mecânicos

Controlar serviços executados e peças utilizadas

Calcular o valor total da OS a partir de mão de obra e peças

Acompanhar status e datas de execução

### 🧩 Contexto e Regras de Negócio
A narrativa do problema descreve o seguinte cenário:

Clientes levam veículos para conserto ou revisão

Cada OS pertence a um veículo

Cada veículo pertence a um cliente

Cada OS é atribuída a uma equipe de mecânicos

A equipe identifica os serviços que serão executados e registra a OS

O valor total da OS é composto por:
Serviços (mão de obra) e Peças utilizadas

O cliente deve autorizar a execução

A mesma equipe avalia e executa os serviços

Mecânicos possuem:
código,
nome,
endereço,
especialidade,

Cada OS possui:
número,
data de emissão,
data de conclusão,
valor total,
status

🏗️ Entidades Principais do Modelo

👤 Cliente
Armazena dados do cliente proprietário do veículo.

🚗 Veículo
Relaciona-se com o cliente e pode possuir várias ordens de serviço.

🧰 Ordem de Serviço
Registra os serviços realizados e peças utilizadas.

👨‍🔧 Mecânico
Cada mecânico pertence a uma ou mais equipes.

🛠️ Equipe
Uma equipe executa os serviços de uma OS.

🧩 Equipe_has_Mecânico
Tabela associativa para relacionamento N:N entre mecânicos e equipes.

🪛 Serviço
Tabela de referência para os tipos de serviço (ex.: revisão, conserto, diagnóstico), incluindo valor de mão de obra.

🔩 Peça
Tabela de referência para peças utilizadas.

📌 OS_has_Serviço
Tabela associativa que registra os serviços executados em cada OS.

📌 OS_has_Peça
Tabela associativa que registra as peças utilizadas em cada OS.

🔗 Principais Relacionamentos
Cliente 1:N Veículo
Veículo 1:N Ordem de Serviço
Equipe 1:N Ordem de Serviço
Equipe N:M Mecânico (via tabela associativa)
Ordem de Serviço N:M Serviço (via OS_has_Serviço)
Ordem de Serviço N:M Peça (via OS_has_Peça)

🧮 Regras de Cálculo
O valor total da OS será composto pela Soma dos (Serviços executados) + a Soma de (Peças utilizadas)
Os valores unitários de peças e serviços são armazenados nas tabelas associativas, permitindo histórico e controle financeiro.

🛠️ Ferramenta Utilizada
O modelo conceitual foi desenvolvido utilizando:
📌 MySQL Workbench — ferramenta de modelagem visual


💡 Aprendizados
Durante o desenvolvimento deste projeto foi possível:
✔ Interpretar requisitos a partir de uma narrativa
✔ Identificar entidades e seus atributos
✔ Definir corretamente cardinalidades e relacionamentos
✔ Utilizar tabelas associativas para relacionamentos N:M
