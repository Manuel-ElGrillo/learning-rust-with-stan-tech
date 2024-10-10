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


## Tipos de datos 🦀

| **Tipo de Dato**   | **Descripción**                                                                                       | **Rango o Límite**                                          | **Ejemplo**               |
|--------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------|---------------------------|
| **Enteros con signo** (signed integers) |                                                                                       |                                                             |                           |
| `i8`               | Entero de 8 bits con signo                                                                            | -128 a 127                                                   | `let x: i8 = -42;`        |
| `i16`              | Entero de 16 bits con signo                                                                           | -32,768 a 32,767                                             | `let x: i16 = -32000;`    |
| `i32`              | Entero de 32 bits con signo                                                                           | -2,147,483,648 a 2,147,483,647                               | `let x: i32 = -100000;`   |
| `i64`              | Entero de 64 bits con signo                                                                           | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807       | `let x: i64 = -5000000;`  |
| `i128`             | Entero de 128 bits con signo                                                                          | -170,141,183,460,469,231,731,687,303,715,884,105,728 a 170,141,183,460,469,231,731,687,303,715,884,105,727 | `let x: i128 = -123456789123456789;` |
| **Enteros sin signo** (unsigned integers) |                                                                                       |                                                             |                           |
| `u8`               | Entero de 8 bits sin signo                                                                            | 0 a 255                                                      | `let x: u8 = 200;`        |
| `u16`              | Entero de 16 bits sin signo                                                                           | 0 a 65,535                                                   | `let x: u16 = 50000;`     |
| `u32`              | Entero de 32 bits sin signo                                                                           | 0 a 4,294,967,295                                            | `let x: u32 = 3000000000;`|
| `u64`              | Entero de 64 bits sin signo                                                                           | 0 a 18,446,744,073,709,551,615                               | `let x: u64 = 9000000000;`|
| `u128`             | Entero de 128 bits sin signo                                                                          | 0 a 340,282,366,920,938,463,463,374,607,431,768,211,455      | `let x: u128 = 123456789123456789;` |
| **Flotantes** (floating point) |                                                                                       |                                                             |                           |
| `f32`              | Número de coma flotante de 32 bits                                                                     | 1.2E-38 a 3.4E+38                                            | `let x: f32 = 3.14;`      |
| `f64`              | Número de coma flotante de 64 bits                                                                     | 2.3E-308 a 1.7E+308                                          | `let x: f64 = 2.71828;`   |
| **Booleano**       | Valor booleano                                                                                        | `true` o `false`                                             | `let x: bool = true;`     |
| **Caracter**       | Un carácter Unicode (32 bits)                                                                         | Un único carácter Unicode, por ejemplo, `'a'`, `'é'`, `'∞'`  | `let x: char = 'A';`      |
| **Tupla**          | Grupo de valores heterogéneos (de diferentes tipos)                                                   | No tiene un rango definido                                   | `let x: (i32, f64, bool) = (42, 6.9, true);` |
| **Array**          | Secuencia de elementos del mismo tipo, de longitud fija                                               | La longitud se debe definir en el momento de la declaración  | `let x: [i32; 3] = [1, 2, 3];` |
| **String**         | Cadena de texto (dinámica)                                                                            | Depende del sistema y memoria disponible                     | `let x: String = String::from("Hola");` |


//Nota para mi 🦗🎵: Ver como son los iteradores en Rust

## Bucles / Ciclos / Iteradores