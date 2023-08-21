# Trabalho de Complexidade de Algoritmos - Autômatos Finitos
Questão 3, 4 e 5:
Class AutomatoFinito:
def init(self): self.estado_inicial = 'q0' self.estado_final = {'q0', 'q3'}

def process_entrada(self, entrada):
    for simbolo in entrada:
        if simbolo not in {'a', 'b'}:
            return False

        if self.estado_inicial == 'q0':
            if simbolo == 'a':
                self.estado_inicial = 'q0'
            else:
                self.estado_inicial = 'q1'
        elif self.estado_inicial == 'q1':
            if simbolo == 'a':
                self.estado_inicial = 'q3'
            else:
                self.estado_inicial = 'q0'
        elif self.estado_inicial == 'q3':
            if simbolo == 'a':
                self.estado_inicial = 'q1'
            else:
                self.estado_inicial = 'q3'

    return self.estado_inicial in self.estado_final

Create automato
automato = AutomatoFinito()

entradas = ['bab', 'bba', 'ababab', 'bbbb', 'baaa'] 
   for entrada in entradas: if automato.process_entrada(entrada): 
print(f'A entrada "{entrada}" foi aceita pelo autômato.') 
  else: print(f'A entrada "{entrada}" não foi aceita pelo autômato.')
