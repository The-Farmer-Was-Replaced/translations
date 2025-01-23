# Break
`break` permite detener un ciclo antes de tiempo. Cuando se alcanza la instrucción `break`, se sale inmediatamente del ciclo más interno y se comienza a ejecutar el código después del ciclo.

`for i in range(10):
    break
print(i)`
Esto imprime `0` porque `i` es `0` en la primera iteración del ciclo y luego la instrucción break termina el ciclo.

También funciona en ciclos `while`.

`while True:
    if can_harvest():
        break`

Este código ejecuta el ciclo `while` hasta que `can_harvest()` es `True`.
Tiene el mismo efecto que

`while not can_harvest():
    pass`

En ciclos anidados, `break` siempre sale del ciclo más interno.

`for i in range(10):
    for j in range(10):
        break
        print("esto nunca se imprime")
    print("esto se imprime 10 veces")`
