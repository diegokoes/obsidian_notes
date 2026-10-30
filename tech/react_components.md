---
up:
  - "[[react]]"
---
# REACT -> COMPONENTS
1. [[componentes_funcionales|Functional components]]
2. [[componentes_clase|Class components]]
3. [[react_props|Props]]
4. [[react_state|State]]
5. [[ciclo_vida_componentes|Component lifecycle]]
6. [[eventosReact|Events]]
7. [[renderizado_condicional|Conditional rendering]]
8. [[renderizado_listas|List rendering]]
- - - 
## DEFINITION
**Official:**
> Un componente en React es una pieza reutilizable de código que representa una parte de la interfaz de usuario. Los componentes son independientes y gestionan su propio estado o reciben datos a través de propiedades (props).

**Personal:**
>Un componente es como una "pieza de Lego" en React. Sirve para construir la interfaz dividiendo la aplicación en partes más pequeñas y manejables, cada una con su funcionalidad específica. Puede ser tan simple como un botón o tan complejo como un formulario entero.

- - - 
### ¿QUÉ SON?
> [!info]- Click to reveal the answer
Una función javascript, generalmente el nombre de la función es el nombre del componente.

### ESA FUNCIÓN... ¿FUNCTION NAME() O LAMBDA?
> [!info]- Click to reveal the answer
```function() nombreFuncion(){ return ( < > . . . < / > ) }```. 
### DE QUÉ ESTÁN FORMADOS
> [!info]- Click to reveal the answer
  [[react_props|PROPS]], [[react_state|STATE]]código funcional y return de código [[react_jsx|JSX]]
### **¿CÓMO SE COMUNICAN LOS COMPONENTES ENTRE SÍ?**
> [!info]- Click to reveal the answer
La comunicación se hace a través de props, que permiten pasar datos de un componente padre a uno hijo. Para enviar datos de un hijo a un padre, se pueden usar funciones callback pasadas como props.
- - - 




