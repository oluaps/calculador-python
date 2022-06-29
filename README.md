from decimal import Decimal
def calculate():
    operation = input('''
Digite o operador desejado:
+ Para Adição
- Para Subtração
* Para Multiplicação
/ Para Divisão
''')

    number_1 = int(input('Digite o primeiro número: '))
    number_2 = int(input('Digite o segundo número: '))

    if operation == '+':
        print('{} + {} = '.format(number_1, number_2))
        print(str(Decimal(number_1 + number_2).quantize(Decimal('.01'))).replace('.', ','))

    elif operation == '-':
        print('{} - {} = '.format(number_1, number_2))
        print(str(Decimal(number_1 - number_2).quantize(Decimal('.01'))).replace('.', ','))

    elif operation == '*':
        print('{} * {} = '.format(number_1, number_2))
        print(str(Decimal(number_1 * number_2).quantize(Decimal('.01'))).replace('.', ','))

    elif operation == '/':
        print('{} / {} = '.format(number_1, number_2))
        print(str(Decimal(number_1 / number_2).quantize(Decimal('.01'))).replace('.', ','))

    else:
        print('Um operador válido não foi digitado, reinicie o programa!')

    again()

def again():
    calc_again = input('''
Deseja calcular novamente?
Digite S para SIM e N para Não.
''')

    if calc_again.upper() == 'S':
        calculate()
    elif calc_again.upper() == 'N':
        print('Até Mais!')
    else:
        again()

calculate()
