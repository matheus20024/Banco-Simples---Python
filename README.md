# Banco-Simples---Python
Esse é um programação de banco com senha, saques e saldos

Primeira Parte Banco 1.0

import random
Seu_Nome = str(input('Digite seu Nome'))
def saque(saldo, valor_saque):
        result =  saldo -  valor_saque 
        print(f'SALDO R${result}')
 
def deposito(saldo, valor_deposito): 
        result  =  saldo  +  valor_deposito
        print(f'SALDO R$ {result}')
def visualizar(saldo): 
    print(f' Seu saldo é R$ {saldo}')
def parar(escolha):
    if escolha != '1' or '2' or '3':
       print('Escolha incorreta') 
def banco():
    saldo_randomico =  random.randint(100,1000)
    print(f'SEJA BEM VINDO{Seu_Nome} ao banco Bradesco')
    print('Digite -> 1 para saldo| 2 para deposito | 3 para saque ') 
    escolha_operacao =   input('Digite sua escolha')
    if escolha_operacao ==  '1':
       visualizar(saldo_randomico)  
    elif escolha_operacao == '2': 
       print(f'Seu saldo  -  R${saldo_randomico},00') 
       dep =  float(input('Digite o valor do deposito')) 
       deposito(saldo_randomico, dep)    
    elif escolha_operacao == '3':
       print(f'Seu saldo  -  {saldo_randomico}') 
       saq =  float(input('Digite o valor do saque')) 
       saque(saldo_randomico,saq) 
    else: 
       parar(escolha_operacao)
       banco()
while True:
      banco()        

Segunda Parte Banco 2.0

import random
Seu_Nome = int(input('Digite seu Numero'))
def verificar_senha():
    senha_salva = "123"  
    tentativas = 3
    while tentativas > 0:
        senha_digitada = input("Digite a senha: ")
        if senha_digitada == senha_salva:
            print('Senha correta')
            print(f'Seja Bem vindo {Seu_Nome} ao Banco Bradesco')
            return True
        else:
            tentativas -= 1
            print("Senha incorreta! Tentativas restantes:", tentativas)
    print("Você excedeu o número máximo de tentativas.")
    return False
verificar_senha()     
class ContaBancaria:
    def __init__(self, saldo_inicial):
        self.saldo = saldo_inicial
    def depositar(self, valor):
        self.saldo += valor
        print(f"Depósito de {valor} realizado. Novo saldo: {self.saldo}")
    def sacar(self, valor):
        if valor > self.saldo:
            print("Saldo insuficiente.")
        else:
            self.saldo -= valor
            print(f"Saque de {valor} realizado. Novo saldo: {self.saldo}")
def main():
    saldo_inicial = 1000
    conta = ContaBancaria(saldo_inicial)
    while True:
        print("\n1. Ver saldo\n2. Depositar\n3. Sacar\n4. Sair")
        opcao = input("Escolha uma opção: ")
        if opcao == "1":
            print(f"Seu saldo atual é: {conta.saldo}")
        elif opcao == "2":
            valor_deposito = float(input("Digite o valor a depositar: "))
            conta.depositar(valor_deposito)
        elif opcao == "3":
            valor_saque = float(input("Digite o valor a sacar: "))
            conta.sacar(valor_saque)
        elif opcao == "4":
            print("Saindo...")
            print("Banco Bradesco Agradece")
            break
        else:
            print("Opção inválida. Tente novamente.")
if __name__ == "__main__":
    main()
