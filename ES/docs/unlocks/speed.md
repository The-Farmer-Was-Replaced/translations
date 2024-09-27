# Speed Upgrade
La velocidad de ejecución se ha duplicado. El problema es que ahora el dron cosecha más rápido de lo que crece la hierba, lo que resulta en ninguna cosecha. Para lidiar con esto, las ramas [if](docs/scripting/if) y la función [can_harvest](functions/can_harvest) ahora están desbloqueadas.

## Comprobando Antes de Cosechar
Hasta ahora solo teníamos `True` y `False` como condiciones, lo cual, por supuesto, no es muy útil con `if`.

La nueva función `can_harvest()` proporciona una mejor condición. `can_harvest()` devuelve `True` si la planta bajo el dron puede ser cosechada y `False` en caso contrario.

`if can_harvest():
	#hacer algo`

La razón por la que puedes usar esta función como una condición de esta manera es porque devuelve un valor booleano.

Un valor de retorno esencialmente significa que después de que se ejecuta la funcionalidad, la expresión de llamada a la función se evalúa al valor devuelto.

Lo que sucede cuando se ejecuta el código anterior:
	-el if se ejecuta
	-se llama a `can_harvest()`
	-`can_harvest()` hace lo suyo
	-`can_harvest()` devuelve `True` o `False`
	-la declaración ahora es `if True:` o `if False:`
	-el dron hace un giro si puede cosechar

Ahora podemos usar `if` para evitar que el dron coseche demasiado pronto.
