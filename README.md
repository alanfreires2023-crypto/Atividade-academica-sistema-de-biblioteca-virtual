class Livro:
    def __init__(self, titulo, preco):
        self.titulo = titulo
        self.preco = preco

    def alugar(self):
        print(f"✅ Você selecionou e alugou: {self.titulo}")


livros = {
    "1": Livro("O Príncipe", 15.00),
    "2": Livro("A Arte da Guerra", 20.00),
    "3": Livro("A Revolução dos Bichos", 30.00)
}

carrinho = [] # Lista para guardar os livros alugados
total_pagar = 0

# --- LOOP PRINCIPAL ---
while True:
    print("\n" + "="*30)
    print("  BEM-VINDO À BIBLIOTECA  ")
    print("="*30)
    print("[1] - O Príncipe : R$ 15.00")
    print("[2] - A Arte da Guerra : R$ 20.00")
    print("[3] - A Revolução dos Bichos : R$ 30.00")
    print("[0] - Finalizar e Sair")
    
    opcao = input("\nEscolha uma opção: ")

    if opcao == "0":
        break
    
    if opcao in livros:
        livro_escolhido = livros[opcao]
        livro_escolhido.alugar()
        
        # Somando ao total
        total_pagar += livro_escolhido.preco
        carrinho.append(livro_escolhido.titulo)
        
        print(f"💰 Total atual: R$ {total_pagar:.2f}")
        
        # Pergunta se quer continuar
        continuar = input("\nDeseja alugar outro livro? (sim/nao): ").lower()
        if continuar != "sim":
            break
    else:
        print("❌ Opção inválida! Tente novamente.")

# --- FINALIZAÇÃO ---
print("\n" + "-"*30)
print("RESUMO DO PEDIDO:")
for item in carrinho:
    print(f"- {item}")
print(f"\nVALOR TOTAL A PAGAR: R$ {total_pagar:.2f}")
print("-"*30)
print("Obrigado por usar nossa biblioteca!")
