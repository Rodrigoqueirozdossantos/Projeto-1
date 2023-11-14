# Projeto-1
Controle de Estoque.
# Inicializar um dicionário vazio para representar o estoque
estoque = {}

# Função para adicionar um item ao estoque
def adicionar_item():
    nome = input("Nome do item: ")
    quantidade = int(input("Quantidade: "))
    preco_unitario = float(input("Preço unitário: R$"))
    
    if nome in estoque:
        estoque[nome]['quantidade'] += quantidade
    else:
        estoque[nome] = {'quantidade': quantidade, 'preco_unitario': preco_unitario}

# Função para atualizar a quantidade de um item no estoque
def atualizar_item():
    nome = input("Nome do item que deseja atualizar: ")
    
    if nome in estoque:
        quantidade = int(input("Nova quantidade: "))
        estoque[nome]['quantidade'] = quantidade
    else:
        print("Item não encontrado no estoque.")

# Função para visualizar o estoque
def visualizar_estoque():
    print("\nEstoque:")
    for item, info in estoque.items():
        print(f"Item: {item}, Quantidade: {info['quantidade']}, Preço unitário: R${info['preco_unitario']:.2f}")

# Função para remover um item do estoque
def remover_item():
    nome = input("Nome do item que deseja remover: ")
    
    if nome in estoque:
        del estoque[nome]
    else:
        print("Item não encontrado no estoque.")

# Menu principal
while True:
    print("\nControle de Estoque")
    print("1. Adicionar Item")
    print("2. Atualizar Item")
    print("3. Visualizar Estoque")
    print("4. Remover Item")
    print("5. Sair")
    
    opcao = input("Escolha uma opção: ")
    
    if opcao == '1':
        adicionar_item()
    elif opcao == '2':
        atualizar_item()
    elif opcao == '3':
        visualizar_estoque()
    elif opcao == '4':
        remover_item()
    elif opcao == '5':
        break
    else:
        print("Opção inválida. Por favor, escolha uma opção válida.")

print("O programa foi encerrado.")
