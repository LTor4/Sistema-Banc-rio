# Sistema Bancário

💻 Criação de um sistema bancário simples em Python para o bootcamp DIO-Santander de Back-End em Python

----------------------------
## Objetivo

Implementar três operações essenciais: depósito, saque e extrato. O sistema foi desenvolvido para um banco que busca monetizar suas operações.

------------
# CÓDIGO
### Menu inicial de escolha de opções
menu = """

|======MENU INICIAL =======|

|=======[1] Deposito========|

|======= [2] Saque =========|

|======= [3] Extrato =========|

|======= [0] Sair ===========|

=> """

saldo = 0 <br>
limite = 500 <br>
extrato = "" <br>
numero_saques = 0 <br>
LIMITE_SAQUES = 3 <br>

while True:

#### Função de depósito

    opcao = input(menu)
    if opcao == "1":
        valor = float(input("Informe o valor que deseja depositar: "))
        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor: .2f}\n"
            
        else:
            print("Valor inválido")
#### Função Saque
    elif opcao == "2":
        valor = float(input("Informe o valor que deseja sacar: "))
        if valor > saldo:
            print("Saldo insuficiente!")
        elif valor > limite:
            print("Saque excedeu o limite de valor!")
        elif numero_saques >= LIMITE_SAQUES:
            print("Excedido o limite de saques diário! Tente novamente amanhã!")
        elif valor < saldo:            
            saldo -= valor
            extrato += f"Saque: R$ {valor: .2f}\n"
            numero_saques += 1
#### Função extrato            
    elif opcao == "3":
        print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")
### Para sair do sistema    
    elif opcao == "0":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")
