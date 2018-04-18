# projeto
def erro_login(senha,chave):
    while senha!= chave:
        print('A chave de acesso não está correta, digite novamente!')
        senha = input()
    #Quando senha estiver correta, permitir acesso
    menu_principal()
 estoque = {'111000':['arroz', '14 11 2018',5]}
def adicionar_item():
    nome = input('digite o nome do produto:')
    quant = int(input('Quantide:'))
    print('Responda as seguintes perguntar com '"S"' para sim e '"N"' para não')
    cod1 = input('É perecível?').upper()
    if cod1 =='S':
        data = input('data de validade:(dd/mm/aaaa)').split('/')
    cod2 = input('É frágil?').upper()
    print('Digite 1 para NATURAL e 2 para GELADO.')
    cod3 = input('Climatação:')
    #FUNÇÃO GERA CÓDIDO E ADICONA NO DICIONÁRIO
    gerar_codigo(cod1,cod2,cod3,nome,data,quant)

def gerar_codigo(cod1,cod2,cod3,nome,data,quant):
    cod = ''
    if cod1 =='S':
        cod += '1'
    else:
        cod += '0'
    if cod2=='S':
        cod+='1'
    else:
        cod += '0'
    if cod3 =='1':
        cod+='1'
    else:
        cod += '0'
    cod += '000'
    #Verificar se o código já existe e acrescentar 1 para adicionar no estoque
    if cod in estoque:
      ultimo = int(cod[-1])
      sem_ultimo = cod[:-1]
      novo_ultimo = str(ultimo+1)
      cod = sem_ultimo + novo_ultimo
      estoque[cod]=[nome,data,quant]
     else:
       estoque[cod]=[nome,data,quant]
