# registro_diario
# com intuito de fazer analise do meu trabalho, desenvolvi essa pequena funcionalidade em Python
# opwrite, versao: 1.0 | objetivo do programa: criar repositorio na maquina local, receber dados, salvar e atualizar |
# fluxo: inicio --> exibir interface --> aguardar dados do usuario --> processar resposta --> salvar --> fim
# estensao: o arquivo gerado sera do tipo .csv e sera ultilizado para criar insights com analise de dados
# from datetime import date


from datetime import *
from colorama import *

data= date.today()
tempo= date.strftime('%d/%m/%Y %H:%M')
endereco= "'c:/Users/HOME/Documents/"
extensao= ".csv'"

usuario= input('Nome do usuario: ')
print('Ola', usuario, '\nData:', data,'\n> Caso nao tenha local para salvar os dados que serao gerados, recomendamos a criaçao de um repositorio. Mas fique tranquilo, ajudaremos voçe!')

saudacao= int(input('> Digite uma das opçoes a seguir e pressione tecla ENTER\n 1: Criar um repositorio \n 2: Ja possuo repositorio\n '))
if saudacao == 1:
    print('> Pronto! Criamos um repositorio para voçe!')
    with open('c:/Users/HOME/Documents/registro.csv', mode= 'a+', encoding= 'utf-8') as arquivo:
        cabecalho= 'COLABORADOR,  MOTOCICLETA,  SERVICO,  QUILOMETRAGEM,  ANO/MODELO,  HORARIO \n'
        # cabecalho1= '\033[0;33;42m cabecalho \033
        arquivo1= arquivo.write(cabecalho)

    print('> Caso precise navegar ate ele, esse sera o caminho --> c:/Users/HOME/Documents/registro.csv\n> Lembre de usa-lo em seu proximo acesso!')
    print('> Descreva o servico a ser realizado, ou digite "SAIR" para sair e pressione tecla ENTER\n--> Digite: Moto, Serviço, Km, Ano:\n  ')

    while True:
        with open('c:/Users/HOME/Documents/registro.csv', mode= 'a+', encoding= 'utf-8') as arquivo:
            nome= usuario
            moto= input(' MOTO: ')
            servico= input(' SERVIÇO: ')
            km= input(' KM: ')
            ano= input(' ANO: ')

            inicio= (f'{nome}, {moto}, {servico}, {km}, {ano}, {tempo}\n')
            arquivo1= arquivo.writelines(inicio)

            fim= int(input('Ok! Digite:\n 1: Proximo serviço\n 2: Salvar e sair\n : '))
            if fim == 1:
                pass
            elif fim == 2:
                print(f'* Fim do expediente:', tempo, '\nAte a proxima!')
                break
            arquivo.read()
            arquivo.close()
        breakpoint

elif saudacao == 2:
    usuario= input('Nome do usuario: ')
    programa= input('Digite corretamente o caminho ate o repositorio: ')
    print('> Descreva o servico a ser realizado, ou digite "SAIR" para sair e pressione tecla ENTER\n--> Digite: Moto, Serviço, Km, Ano:\n  ')
    while True:
        with open(programa, mode= 'a+', encoding= 'utf-8') as arquivo:
            nome= usuario
            moto= input(' MOTO: ')
            servico= input(' SERVIÇO: ')
            km= input(' KM: ')
            ano= input(' ANO/MODELO: ')

            inicio= (f'{nome}, {moto}, {servico}, {km}, {ano}, {tempo}\n')
            arquivo1= arquivo.writelines(inicio)

            fim= int(input('\nOk! Digite: \n 1: Proximo serviço\n 2: Salvar e sair\n : '))
            if fim == 1:
                pass
            elif fim == 2:
                print(f'* Fim do expediente:', tempo, '\nAte a proxima!')
                break
            arquivo= arquivo.close()
            

                
# python= os.system('clear')
# executavel: cxfreeze opwrite.py --target-dir Registro_Diario

