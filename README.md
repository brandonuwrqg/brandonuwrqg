E.def num_primo(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
def circ(n):
    nn = str(n)
    for _ in range(len(nn)):
        if not num_primo(int(nn)):
            return False
        nn = nn[1:] + nn[0]
    return True
while True:
    n = int(input())
    if n == -1:
        break
    if circ(n):
        print("SI")
    else:
        print("NO")
 A.def es_primo(num):
    if num <= 1:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True
def gpp(limite):
    primos = []
    for num in range(2, limite + 1):
        if es_primo(num):
            primos.append(num)
    return primos
def dpp(casos, primos):
    resultados = []
    for x in casos:
        menor_distancia = float('inf')
        for primo in primos:
            distancia = abs(primo - x)
            if distancia < menor_distancia:
                menor_distancia = distancia
            if primo > x:
                break
        resultados.append(menor_distancia)
    return resultados
limite_primos = 100000
primos = gpp(limite_primos)
n = int(input())
casos = []
for _ in range(n):
    x = int(input())
    casos.append(x)
resultados = dpp(casos, primos)
for resultado in resultados:
    print(resultado)
 b:import sys
def desc(n):
	nn=[]
	d =2
	while n > 1:
		while n % d == 0:
			nn.append(d)
			n = n //d
		d += 1
	print(nn[len(nn)-1])
for linea in sys.stdin:
	if linea == '\n':
		break
	n = int(linea)
	desc(n)
 c.import sys
def fPrimo(n):
	factores = []
	while n % 2 == 0:
		factores.append(2)
		n //= 2
	d = 3
	while d * d <= n:
		while n % d == 0:
			factores.append(d)
			n //= d
		d += 2
	if n > 2:
		factores.append(n)
	return factores
for line in sys.stdin:
	n = int(line.strip())
	print(*fPrimo(n))
 
