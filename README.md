Código:

def raiz(x0, tolerance=1e-6, max_iterations=100):
    x = x0
    for i in range(max_iterations):
        fx = x**2 - 2
        f_prime_x = 2 * x
        if f_prime_x == 0:
            print("Derivada zero, método falhou.")
            return None
        x_next = x - fx / f_prime_x
        if abs(x_next - x) < tolerance:
            print(f"Convergência alcançada após {i+1} iterações.")
            return x_next
        x = x_next
    print("Número máximo de iterações atingido.")
    return x

x0 = 1.5
result = raiz(x0)
print(result)



Explicação: Em

def newton_raphson_sqrt2(x0, tolerance=1e-6, max_iterations=100):

determinamos os paramentos, como precisão, ponto inicial e maximo de calculos que serão feitos para evitar loops infinitos;

Em 

for i in range(max_iterations):

iniciamos um loop ate encontramos o valor desejado;

A linha 

  if f_prime_x == 0:
            print("Derivada zero, método falhou.")
            return None

Verifica se a derivada resultará em 0, o que causa uma indeterminação no calculo;

A linha 

 x_next = x - fx / f_prime_x

é a formula dada de Newton;

A expressão

if abs(x_next - x) < tolerance:
            print(f"Convergência alcançada após {i+1} iterações.")
            return x_next

Verifica se a diferença absoluta entre a nova aproximação x_next e a anterior x é menor que a tolerância;


Se o loop atingir max_iterations sem convergir,  retorna a última aproximação x


