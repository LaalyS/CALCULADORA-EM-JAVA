# CALCULADORA-EM-JAVA
Uma execução simplificada da criação de uma calculadora criada em JAVA .... Em teste e Execução


class Cliente:
    def init (self, nome, conta, saldo):
      self.nome = nome
      self.conta = conta
      self. saldo = saldo

    def depositar(self, valor):
        self.saldo += valor

    def sacar(self, valor):
        if self.saldo >= valor:
            self.saldo -= valor
        else:
            print("Saldo insuficiente")

clientes = [
    Cliente("João", "001", 1000.0),
    Cliente("Maria", "002", 2000.0),
    Cliente("José", "003", 500.0)
]

while True:
    print("Bem-vindo(a) ao banco")
    print("1 - Consultar saldo")
    print("2 - Depositar")
    print("3 - Sacar")
    print("0 - Sair")

    opcao = input("escolha um opçao")

    if opcao =="0":
          break

    elif opcao == "1":
        conta = input("Digite o numero da conta:")
        for cliente in clientes:
            if cliente.conta == conta:
               print(f"Saldo: R${cliente.saldo:2f}")
               break

        else:
            print("Conta não encontrada")
    elif opcao == "2":
        conta = input("Digite o número da conta: ")
        for cliente in clientes:
            if cliente.conta == conta:
                valor = float(input("Digite o valor do depósito: "))
                cliente.depositar(valor)
                print(f"Depósito realizado. Novo saldo: R${cliente.saldo:.2f}")
                break
        else:
            print("Conta não encontrada")
    elif opcao == "3":
        conta = input("Digite o número da conta: ")
        for cliente in clientes:
            if cliente.conta == conta:
                valor = float(input("Digite o valor do saque: "))
                cliente.sacar(valor)
                print(f"Saque realizado. Novo saldo: R${cliente.saldo:.2f}")
                break
        else:
            print("Conta não encontrada")
    else:
        print("Opção inválida")
