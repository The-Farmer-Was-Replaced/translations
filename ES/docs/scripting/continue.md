# Continue
`continue` permite detener la iteración actual de un bucle y saltar a la siguiente iteración del bucle más interno.

```python
for i in range(10):
	continue
	print("esto nunca se imprime")
```

Esto ejecuta todas las `10` iteraciones del bucle, pero la declaración `print` después de `continue` siempre se omite.

También funciona en bucles `while`.

```python
while True:
	if not can_harvest():
		continue

	harvest()
```

East código solo llama a `harvest()` cuando `can_harvest()` es `True`. Tiene el mismo efecto que

```python
while True:
	if can_harvest():
		harvest()
```

En bucles anidados, `continue` siempre afecta al bucle más interno.

```python
for i in range(10):
	for j in range(10):
		print("esto se imprime 100 veces")
		continue
		print("esto nunca se imprime")
	print("esto se imprime 10 veces")
```
