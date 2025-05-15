import os
import json
import hashlib

arquivo_usuarios = "usuarios.json"

if not os.path.exists(arquivo_usuarios):
    with open(arquivo_usuarios, "w") as f:
        json.dump([], f)

def carregar_usuarios():
    if not os.path.exists(arquivo_usuarios):
        return []
    try:
        with open(arquivo_usuarios, "r") as f:
            return json.load(f)
    except json.JSONDecodeError:
        return []

def salvar_usuarios(lista):
    with open(arquivo_usuarios, "w") as f:
        json.dump(lista, f, indent=4)

def proteger_senha(senha):
    return hashlib.sha256(senha.encode()).hexdigest()

def cadastrar():
    os.system("cls" if os.name == "nt" else "clear")
    print("Cadastro de Usuário")
    nome = input("Digite um nome de usuário: ")
    email = input("Digite seu email: ")
    senha = input("Crie uma senha: ")

    usuarios = carregar_usuarios()

    for usuario in usuarios:
        if isinstance(usuario, dict) and usuario.get("usuario") == nome:
            print("Esse nome de usuário já existe!")
            input("Pressione Enter para voltar.")
            return

    novo_usuario = {
        "usuario": nome,
        "email": email,
        "senha": proteger_senha(senha)
    }

    usuarios.append(novo_usuario)
    salvar_usuarios(usuarios)

    print("Cadastro feito com sucesso!")
    input("Pressione Enter para continuar.")

def login():
    os.system("cls" if os.name == "nt" else "clear")
    nome = input("Digite seu nome de usuário: ")
    senha = input("Digite sua senha: ")

    usuarios = carregar_usuarios()
    senha_protegida = proteger_senha(senha)

    for usuario in usuarios:
        if isinstance(usuario, dict) and usuario.get("usuario") == nome and usuario.get("senha") == senha_protegida:
            print(f"Bem-vindo, {nome}!")
            input("Pressione Enter para continuar.")
            return True

    print("Usuário ou senha incorretos.")
    input("Pressione Enter para tentar novamente.")
    return False

def menu_principal():
    print("Seja bem-vindo!")
    print("Escolha a matéria que deseja estudar hoje.")
    print("1. Direitos Humanos 📖")
    print("2. Lógica Computacional 🖥️")
    print("3. Introdução ao Python 👨‍💻")
    print("4. Sair 🚪")

def menu_modulos():
    print("1. Módulo I")
    print("2. Módulo II")
    print("3. Voltar")

def menu_conteudo():
    print("1. Vídeo Aula")
    print("2. Material de apoio")
    print("3. Questões")
    print("4. Voltar")

while True:
    os.system("cls" if os.name == "nt" else "clear")
    print("Bem-vindo ao sistema de aprendizagem")
    print("1. Fazer login")
    print("2. Cadastrar novo usuário")
    print("3. Sair")

    escolha = input("Escolha uma opção: ")

    if escolha == "1":
        if login():
            break
    elif escolha == "2":
        cadastrar()
    elif escolha == "3":
        print("Até logo!")
        exit()
    else:
        input("Opção inválida. Pressione Enter para tentar novamente.")

while True:
    os.system("cls" if os.name == "nt" else "clear")
    menu_principal()
    opcao = input("Escolha uma opção (1 a 4): ")

    if opcao in ["1", "2", "3"]:
        while True:
            os.system("cls" if os.name == "nt" else "clear")
            if opcao == "1":
                print("Direitos Humanos")
            elif opcao == "2":
                print("Lógica Computacional")
            elif opcao == "3":
                print("Introdução ao Python")

            menu_modulos()
            modulo = input("Escolha um módulo (1-2) ou 3 para voltar: ")

            if modulo in ["1", "2"]:
                while True:
                    os.system("cls" if os.name == "nt" else "clear")
                    print(f"Módulo {modulo}")
                    menu_conteudo()
                    conteudo = input("Escolha uma opção ou 4 para voltar: ")
                    if conteudo == "4":
                        break
                    else:
                        print(f"Você escolheu a opção {conteudo}. Conteúdo em breve!")
                        input("Pressione Enter para voltar.")
            elif modulo == "3":
                break
            else:
                input("Opção inválida. Pressione Enter para tentar novamente.")
    elif opcao == "4":
        print("Saindo do programa.")
        break
    else:
        input("Opção inválida. Pressione Enter para tentar novamente.")
