[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/7EVNAYx2)
# ClientServerBasics (2.0)
Starter code for the basic client-server assignment


Este template corresponde ao exemplo da Fig. 2.3 do livro. O exercício consiste em acrescentar funcionalidade ao servidor para torná-lo mais útil. Essa funcionalidade deve ser acessível aos clientes. Por exemplo, o servidor pode ser uma espécie de calculadora remota. O cliente passa dois valores numéricos, juntamente com o nome de uma operação (ex.: add, subtract, multiply, divide) e o servidor executa a operação respectiva e retorna seu resultado para o cliente. Você pode implementar um servidor com outras funcionalidades (diferente da calculadora). O imporante é que ele ofereça pelo menos três operações diferentes que os clientes podem utilizar remotamente, passando dados para serem processados e recebendo o resultado desse processamento como resposta.

Tarefa individual.

Incluir um Readme descritivo do sistema implementado.



--------------------------------------------------------------------------------------------------------------


Calculadora Remota TCP (Client-Server)
Este projeto implementa um sistema simples de Calculadora Remota utilizando o modelo cliente-servidor sobre o protocolo de transporte TCP. O objetivo é permitir que um cliente envie operações matemáticas para um servidor, que processa os dados e retorna o resultado.

📋 Descrição do Sistema
O sistema utiliza a biblioteca socket do Python para estabelecer uma conexão confiável. A lógica de negócio está centralizada no servidor, permitindo que o cliente seja "leve" (thin client), apenas coletando entradas do usuário e exibindo resultados.

Funcionalidades Implementadas:
O servidor suporta quatro operações principais:

Soma (add): Retorna a soma de dois números inteiros.

Subtração (sub): Retorna a diferença entre dois números inteiros.

Multiplicação (mult): Retorna o produto de dois números inteiros.

Divisão (div): Retorna o quociente, incluindo tratamento de erro para divisão por zero.

🛠️ Tecnologias Utilizadas
Linguagem: Python 3.x
Protocolo de Transporte: TCP (SOCK_STREAM)
Biblioteca: socket (nativa do Python)

🚀 Como Executar
1. Pré-requisitos
Certifique-se de que o arquivo constCS.py esteja no mesmo diretório que os scripts do servidor e do cliente. Ele deve conter as definições de PORT e HOST, por exemplo:

Python
# constCS.py
HOST = '127.0.0.1'
PORT = 5000

2. Passo a Passo
Inicie o Servidor:
Abra um terminal e execute:

Bash
python servidor.py
O servidor ficará em estado listening, aguardando conexões.

Inicie o Cliente:
Abra um segundo terminal e execute:

Bash
python cliente.py
Interação:
No terminal do cliente, siga as instruções:

Digite o primeiro número.

Digite o segundo número.

Escolha a operação (add, sub, mult, div).

📂 Estrutura do Protocolo de Comunicação
A comunicação entre cliente e servidor segue um formato de string simples separado por vírgulas:

Requisição (Cliente -> Servidor): "num1,num2,operação"

Exemplo: "10,5,add"

Resposta (Servidor -> Cliente): Uma string contendo o resultado numérico ou uma mensagem de erro.

Exemplo: "15" ou "Erro: Operação inválida."

🛡️ Tratamento de Erros
O sistema foi projetado para lidar com situações adversas:

Divisão por Zero: O servidor identifica e retorna uma mensagem amigável em vez de travar.

Dados Inválidos: Caso o usuário envie letras em vez de números, o servidor e o cliente tratam exceções de valor (ValueError).

Conexão Recusada: O cliente informa se o servidor não estiver online no momento da tentativa de conexão.

Nota: Este projeto foi desenvolvido como parte de uma atividade individual de Sistemas Distribuídos.
