# Mejora de Velocidad
La velocidad de ejecución se ha duplicado. El problema es que ahora el dron cosecha más rápido de lo que puede crecer la hierba, lo que resulta en no cosechar nada. Para manejar esto, ahora están desbloqueadas las ramificaciones [if](docs/scripting/if.md) y la función [can_harvest](functions/can_harvest).

## Verificar Antes de Cosechar
Hasta ahora solo teníamos `True` y `False` como condiciones, lo cual por supuesto no es muy útil con `if`.

La nueva función can_harvest() proporciona una mejor condición. `can_harvest()` devuelve `True` si la planta bajo el dron puede ser cosechada y `False` en caso contrario.

`if can_harvest():
    #hacer algo`

La razón por la que puedes usar esta función como una condición es porque devuelve un valor booleano.

Un valor de retorno significa esencialmente que después de que se ejecuta la funcionalidad, la expresión de llamada a la función se evalúa al valor devuelto.

Lo que sucede cuando se ejecuta el código anterior:
    -se ejecuta el if
    -se llama a `can_harvest()`
    -`can_harvest()` hace su trabajo
    -`can_harvest()` devuelve `True` o `False`
    -la declaración ahora es `if True:` o `if False:`
    -el bloque de código solo se ejecuta si puede cosechar

Ahora podemos usar `if` para evitar que el dron coseche demasiado pronto.
