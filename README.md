import random

simbolos_tigrinho = ["💰", "🏮", "🧧", "🐯", "💎"] 


saldo_jogador = 1000
aposta = 1,00
jogando = True 

print("🎉 BEM-VINDO AO FORTUNE TIGER SIMPLIFICADO! 🎉")
print("Gire os rolos e torça para o Tigre da Sorte te abençoar!")
print("3 símbolos iguais = GRANDE VITÓRIA! 🤑")
print(f"Seu saldo inicial é de R$ {saldo_jogador:.2f}")


while jogando:
    print(f"\n--- SEU SALDO ATUAL: R$ {saldo_jogador:.2f} ---")

    
    if saldo_jogador <= 0:
        print("Você não tem mais saldo para jogar. Fim de jogo!")
        break 

    
    try:
        aposta = int(input("Quanto você quer apostar por giro (digite um número, por exemplo R$1,00)? R$ "))
    except ValueError:
        print("Entrada inválida. Por favor, digite um número inteiro.")
        continue 
    
    if aposta <= 0 or aposta > saldo_jogador:
        print("A aposta deve ser um valor positivo e não pode ser maior que seu saldo.")
        continue 

    saldo_jogador -= aposta
    print(f"Saldo após a aposta: R$ {saldo_jogador:.2f}")
    print("\n🐯 O TIGRE VAI GIRAR OS ROLOS... 🐯\n")

   
    rolo1 = random.choice(simbolos_tigrinho)
    rolo2 = random.choice(simbolos_tigrinho)
    rolo3 = random.choice(simbolos_tigrinho)

   
    print(f"")
    print(f"  {rolo1}    {rolo2}    {rolo3}  ")
    print(f"")

    
    if rolo1 == rolo2 == rolo3:
        ganho = aposta * 5  
        saldo_jogador += ganho
        print(f"\n✨💰 PARABÉNS!!! O TIGRE DA SORTE TE ABENÇOOU! 💰✨")
        print(f"🌟 3 SÍMBOLOS IGUAIS! Você ganhou R$ {ganho:.2f}! 🌟")
    else:
        print("\n😞 Que pena! O Tigre não sorriu para você desta vez...")
        print("Tente de novo para buscar sua fortuna! 🍀")

    print(f"Seu saldo atual: R$ {saldo_jogador:.2f}")

   
    if saldo_jogador > 0:
        continuar = input("\nPressione ENTER para girar novamente ou digite 'S' para SAIR: ")
        if continuar == 'S':
            jogando = False
    else:
        
        jogando = False

print("\nObrigado por jogar! Volte sempre para tentar a sorte com o Tigre! 👋")
print(f"Seu saldo final é de R$ {saldo_jogador:.2f}")
