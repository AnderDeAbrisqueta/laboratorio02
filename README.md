# Mongo DB consultas

## General

En esta base de datos puedes encontrar un montón de apartamentos y sus reviews, esto está sacado de hacer webscrapping.

**Pregunta**: Si montaras un sitio real, ¿qué posibles problemas pontenciales le ves a cómo está almacenada la información?

```

```

## Consultas

### Básico

- Saca en una consulta cuántos apartamentos hay en España.

```
use('mylistings')

db.listingsAndReviews
.aggregate([
    { 
        $match: 
        { 
            "address.country": "Spain" 
        } 
    }, 
    {
        $project: {
          _id:0,
          "address.country": "Número de apartamentos en España:"
        }
    },
    { 
        $count: 
        "Número de apartamentos en España:"
    }
])
.pretty();

```

- Lista los 10 primeros:
  - Sólo muestra: nombre, camas, precio, government_area.
  - Ordenados por precio.
  
```

```

### Filtrando

- Queremos viajar cómodos, somos 4 personas y queremos:
  - 4 camas.
  - Dos cuartos de baño.
  
```

```

- Al requisito anterior, hay que añadir que nos gusta la tecnología queremos que el apartamento tenga wifi.

```

```

- Y bueno, un amigo se ha unido que trae un perro, así que a la query anterior tenemos que buscar que permitan mascota Pets Allowed.

```

```

### Operadores lógicos

- Estamos entre ir a Barcelona o a Portugal, los dos destinos nos valen, peeero... queremos que el precio nos salga baratito (50 $), y que tenga buen rating de reviews.

```

```

## Agregaciones

- Queremos mostrar los pisos que hay en España, y los siguiente campos:
  - Nombre.
  - De que ciudad (no queremos mostrar un objeto, solo el string con la ciudad).
  - El precio.
  
```
  
```
  
  - Queremos saber cuántos alojamientos hay disponibles por país.
  
```
  
```
  
 # Opcional
  
- Queremos saber el precio medio de alquiler de airbnb en España.
  
```
  
```
  
- ¿Y si quisiéramos hacer como el anterior, pero sacarlo por paises?
  
```
  
```
  
- Repite los mismos pasos pero agrupando también por número de habitaciones.
  
```
  
```
  
# Desafio
  
- Queremos mostrar el top 5 de apartamentos más caros en España, y sacar los siguentes campos:
  - Nombre.
  - Ciudad.
  - Amenities, pero en vez de un array, un string con todos los amenities.
    
```

```



