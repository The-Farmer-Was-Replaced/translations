# Dictionaries
Dictionaries sind eine Datenstruktur, die es ermöglicht, Schlüssel mit Werten zu verknüpfen, ähnlich wie ein echtes Wörterbuch Wörter mit ihren Definitionen verknüpft, und man kann sie sehr schnell nachschlagen.

Ein Dictionary kann so erstellt werden:
`rotation = {North:East, East:South, South:West, West:North}`

Der Ausdruck vor dem Doppelpunkt ist der Schlüssel und der Ausdruck nach dem Doppelpunkt ist der Wert, dem der Schlüssel zugeordnet ist.
Das obige Dictionary ordnet Richtungen der Richtung zu, die rechts von ihnen liegt.

Hier ist ein weiteres Beispiel, das die Position der Drohne dem Objekt zuordnet, über dem sie sich befindet.
`x, y = get_pos_x(), get_pos_y()
entity_dict = {(x,y):get_entity_type()}`

Auf den Wert, der einem Schlüssel zugeordnet ist, kann ähnlich wie auf ein Element in einer Liste zugegriffen werden:
`value = dict[key]`

Beispiel:
`orientation = rotation[South]`
Dies setzt `orientation` auf `West`.

Ein neues Schlüssel-Wert-Paar kann so zu einem Dictionary hinzugefügt werden:
`dict[key] = value`

Beispiel:
`entity_dict[(get_pos_x(), get_pos_y())] = get_entity_type()`
Dies aktualisiert das gespeicherte Objekt für die aktuelle Position.

Schlüssel sind eindeutig, daher wird das Hinzufügen eines bereits vorhandenen Schlüssels im Dictionary den vorherigen Wert überschreiben.

Verwenden Sie `dict.pop(key)`, um ein Schlüssel-Wert-Paar aus `dict` zu entfernen.

`key in dict` ergibt `True`, wenn `key` ein Schlüssel im `dict` ist, und `False` andernfalls.
Sie können also `if key in dict:` verwenden, um zu überprüfen, ob `dict` den Schlüssel enthält.

Ein Dictionary in einer for-Schleife zu verwenden, ermöglicht es Ihnen, alle Schlüssel zu durchlaufen:
`for key in dict:
	value = dict[key]`

Es gibt keine Garantie für die Reihenfolge, in der die Schlüssel durchlaufen werden.

Siehe auch [Sets](docs/scripting/sets)
