    import os
    def cls():
        os.system('cls' if os.name == 'nt' else 'clear')
    
    def menu_principal():
        print("SEJA BEM VINDO!")
        print("1. Direitos Humanos 📖")
        print("2. Lógica Computacional 🖥️")
        print("3. Introdução ao Python 👨‍💻")
        print("4. Sair 🚪")
    
    def menu1_1():
        print("1. Módulo I")
        print("2. Módulo II")
        print("3. Voltar")
    
    def menu1_2():
        print("1. Video Aula")
        print("2. Material de apoio")
        print("3. Questões")
        print("4. Voltar")
        
    def menu2_1():
        print("1. Módulo I")
        print("2. Módulo II")
        print("3. Voltar")
    
    def menu2_2():
        print("1. Video Aula")
        print("2. Material de apoio")
        print("3. Questões")
        print("4. Voltar")   
        
    def menu3_1():
        print("1. Módulo I")
        print("2. Módulo II")
        print("3. Voltar")
    
    
    def menu3_2():
        print("1. Video Aula")
        print("2. Material de apoio")
        print("3. Questões")
        print("4. Voltar")
        
    while True:
        cls()
        menu_principal()
        opcao = input("Escolha uma opção (1 a 4): ")
        
        if opcao == "1":
            while True:
                cls()
                print(" Direitos Humanos")
                menu1_1()
                selecao = input("Escolha um módulo (1-2) ou 3 para voltar: ")
                if selecao in ("1", "2"):
                    while True:
                        cls()
                        print(f" Direitos Humanos - Módulo {selecao}")
                        menu1_2()
                        conteudo = input("Escolha uma opção ou 4 para voltar: ")
                        if conteudo == "4":
                            break
                        else:
                            print(f"Você escolheu a opção {conteudo}. Conteúdo em breve!")
                            input("Pressione Enter para continuar...")
                elif selecao == "3":
                    break
                else:
                    input("Opção inválida. Pressione Enter para tentar novamente.")
        
        elif opcao == "2":
            while True:
                cls()
                print(" Lógica Computacional")
                menu2_1()
                selecao = input("Escolha um módulo (1-2) ou 3 para voltar: ")
                if selecao in ("1", "2"):
                    while True:
                        cls()
                        print(f" Lógica Computacional - Módulo {selecao}")
                        menu2_2()
                        conteudo = input("Escolha uma opção ou 4 para voltar: ")
                        if conteudo == "4":
                            break
                        else:
                            print(f"Você escolheu a opção {conteudo}. Conteúdo em breve!")
                            input("Pressione Enter para continuar...")
                elif selecao == "3":
                    break
                else:
                    input("Opção inválida. Pressione Enter para tentar novamente.")
    
        elif opcao == "3":
            while True:
                cls()
                print(" Introdução ao Python")
                menu3_1()
                selecao = input("Escolha um módulo (1-2) ou 3 para voltar: ")
                if selecao in ("1", "2"):
                    while True:
                        cls()
                        print(f" Python - Módulo {selecao}")
                        menu3_2()
                        conteudo = input("Escolha uma opção ou 4 para voltar: ")
                        if conteudo == "4":
                            break
                        else:
                            print(f"Você escolheu a opção {conteudo}. Conteúdo em breve!")
                            input("Pressione Enter para continuar...")
                elif selecao == "3":
                    break
                else:
                    input("Opção inválida. Pressione Enter para tentar novamente.")
    
        elif opcao == "4":
            print("Saindo do programa.")
            break
        else:
            input("Opção inválida. Pressione Enter para tentar novamente.")
      
    
    
    
        
        
