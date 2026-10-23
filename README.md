print("=" * 50)
print(" SISTEMA DE VERIFICAÇÃO DE TRANSPORTE DE CARGA ")
print("=" * 50)

# Entrada de dados
motorista = input("Digite o nome do motorista: ")
veiculo = input("Digite o modelo do veículo: ")

try:
    capacidade = float(input("Capacidade máxima do veículo (kg): "))
    peso_carga = float(input("Peso da carga (kg): "))

    # Validação
    if capacidade <= 0 or peso_carga <= 0:
        print("\nErro: Os valores devem ser maiores que zero!")

    else:
        print("\n--- RELATÓRIO DE TRANSPORTE ---")
        print(f"Motorista: {motorista}")
        print(f"Veículo: {veiculo}")
        print(f"Capacidade do veículo: {capacidade:.2f} kg")
        print(f"Peso da carga: {peso_carga:.2f} kg")

        sobra = capacidade - peso_carga

        # Estruturas condicionais
        if peso_carga < capacidade:
            print("\n✅ Transporte autorizado!")
            print(f"Capacidade restante: {sobra:.2f} kg")

        elif peso_carga == capacidade:
            print("\n⚠️ Transporte autorizado!")
            print("A carga atingiu o limite máximo permitido.")

        else:
            excesso = peso_carga - capacidade
            print("\n❌ Transporte NÃO autorizado!")
            print(f"Excesso de carga: {excesso:.2f} kg")

except ValueError:
    print("\nErro: Digite apenas números válidos para peso e capacidade.")

print("\nObrigado por utilizar o sistema!")
