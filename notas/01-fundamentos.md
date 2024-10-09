# Fundamentos en Rust

## Variables

Las variables en Rust son inmutables, esto quiere decir que no se puede modificar; no como otros lenguajes de programación de generación de cristal.

Para crear una variable se hace así:

```rust
// 1) Se usa la palabra reservada let
// 2) Se coloca el nombre de la variable
// 3) Se coloca el tipo de dato que va a tener esa variable

let variable_no_binaria: &str = "Me identifico como un string";
```

Si quiero que una variable sea mutable y débil se hace así:

```rust
let mut variable_debil: u8 = 9;
```

📢NOTA: En el caso de las constantes, estas se definen en la parte superior del programa (o del archivo) y son escritas en mayúsculas. El tipo de dato no se infiere y debe ser explícito (escrito por nosotros)

### Shadowing

Es un jutsu prohibido de Rust donde se puede reasisgnar el valor de una variable si necesidad de usar `mut`.

Rust destruye sus variables una vez son utilizadas pero parece que quedan en una especie de buffer y si esta variable es vuelta a llamar conserva su antiguo valor

```rust
fn main () {
    let x: u32 = 1;
    let x: u32 = x + 15; //16
    let x: u32 = x / 2; //8
    println!("Valor actual de x = {}", x);
}
```

//Nota para mí 🦗🎵: Hacer una tabla de tipos de datos 