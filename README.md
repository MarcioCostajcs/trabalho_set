# trabalho_set

class ConjuntoAbstrato:
    def __init__(self):
        self.elementos = set()

    def inserir(self, elemento):
        self.elementos.add(elemento)

    def remover(self, elemento):
        if elemento in self.elementos:
            self.elementos.remove(elemento)

    def consultar(self, elemento):
        return elemento in self.elementos

    def uniao(self, outro_conjunto):
        novo_conjunto = ConjuntoAbstrato()
        novo_conjunto.elementos = self.elementos.union(outro_conjunto.elementos)
        return novo_conjunto

    def intersecao(self, outro_conjunto):
        novo_conjunto = ConjuntoAbstrato()
        novo_conjunto.elementos = self.elementos.intersection(outro_conjunto.elementos)
        return novo_conjunto

    def diferenca(self, outro_conjunto):
        novo_conjunto = ConjuntoAbstrato()
        novo_conjunto.elementos = self.elementos.difference(outro_conjunto.elementos)
        return novo_conjunto

    def elementos(self):
        return self.elementos

conjunto_A = ConjuntoAbstrato()
conjunto_A.inserir(1)
conjunto_A.inserir(2)
conjunto_A.inserir(3)
conjunto_A.inserir(4)

conjunto_B = ConjuntoAbstrato()
conjunto_B.inserir(3)
conjunto_B.inserir(4)
conjunto_B.inserir(5)
conjunto_B.inserir(6)

conjunto_A.remover(2)

uniao = conjunto_A.uniao(conjunto_B)
intersecao = conjunto_A.intersecao(conjunto_B)
diferenca = conjunto_A.diferenca(conjunto_B)

print("Conjunto A:", conjunto_A.elementos)
print("Conjunto B:", conjunto_B.elementos)
print("União:", uniao.elementos)
print("Interseção:", intersecao.elementos)
print("Diferença:", diferenca.elementos)
