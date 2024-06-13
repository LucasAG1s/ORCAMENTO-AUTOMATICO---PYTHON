# Projeto 01- criação de pdf automatico com python
# Mostrando informações ao usuário
# Comando `print()`

#### Armazenando dados em viriáveis

#As variáveis no python podem ser atribuidas como o seu nome e possuem uma função de armazenamento de informações, utilizando o sinal de [=] para definir qual registro será armazenado na mesma, então para encaminhar dados a variável basta utilizar a sintaxe correta
projeto = "Sistema Python "
numero = 10
horas_trabalhadas = 100
print(projeto),
print (numero),
print(horas_trabalhadas)

# Mesclando todos os conceitos
projeto = input ("Digite a descrição do projeto: ")
horas_previstas = input("Digite a quantidade de horas previstas: ")
valor_hora = input("Digite o valor da hora trabalhada: ")
prazo = input("Digite o prazo estimado: ")
print(projeto)
print(horas_previstas)
print(valor_hora)
print(prazo)
#### Tipos de dados

- Textos: `str` (String)
- Número: `int` (Numero)
- Comando: `type()`  `str` `int`
nome = "Vinicius"
valor = 100
type(nome)
## CÓDIGO COMPLETO


from fpdf import FPDF

projeto = input ("Digite a descrição do projeto: ")
horas_previstas = input("Digite a quantidade de horas previstas: ")
valor_hora = input("Digite o valor da hora trabalhada: ")
prazo = input("Digite o prazo estimado: ")
nome_orçamento = input("Digite o nome da empresa que solicitou o orçamento: ") + ".pdf"
valor_total = int(valor_hora) * int(horas_previstas)

pdf = FPDF()

pdf.add_page()
pdf.set_font("Arial")

pdf.image("Realize a criação de um templete personalizado para alterar o layout, insira o caminho aqui", x=0, y=0)

pdf.text(115, 145, projeto)
pdf.text(115,160,horas_previstas)
pdf.text(115,175,valor_hora)
pdf.text(115,190,prazo)
pdf.text(115,205,str(valor_total))


pdf.output(nome_orçamento)

print("Orçamento gerado com sucesso")
