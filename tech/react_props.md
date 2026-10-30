---
up:
  - "[[react]]"
---
# REACT
## SUMMARY
> [!summary]

## THEORY

## QUESTIONS
- - - 

# ## QUESTIONS

#flashcards/react

¿CÓMO SE PASAN LAS PROPS A UN COMPONENTE?
?
Se pasan como atributos en la etiqueta del componente, utilizando la sintaxis de JSX.```<Componente ejemplo="Valor" />```

¿CÓMO SE ACCEDEN A LAS PROPS DENTRO DE UN COMPONENTE?
?
En componentes funcionales, las props se reciben como argumento de la función. En componentes de clase, se acceden con this.props.```function Saludo(props){return <h1>hola, {props.nombre}</h1>```

¿SON LAS PROPS MODIFICABLES?
?
No, las props son inmutables. Esto significa que no se pueden cambiar dentro del componente que las recibe.

¿CUÁL ES LA DIFERENCIA ENTRE PROPS Y STATE?
?
**Props**: Se pasan desde un componente padre y son inmutables.
**State**: Es local al componente y puede cambiar con el tiempo.

¿QUÉ PASA SI NO SE PASA UNA PROP REQUERIDA?
?
Si no se pasa una prop, su valor será undefined a menos que el componente tenga un valor predeterminado configurado.

- - - 

