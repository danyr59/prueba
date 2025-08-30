# Parser de Compiladores - ULA 2025

## Descripción

Este proyecto implementa un parser completo para un lenguaje funcional que incluye expresiones aritméticas, lógicas, de control de flujo y manejo de tipos. La implementación utiliza una arquitectura limpia y elegante basada en clases C++ con herencia y polimorfismo.

## Arquitectura

### Jerarquía de Clases

```
Expression (clase base abstracta)
├── Valores Primitivos
│   ├── IntegerValue (números enteros)
│   ├── RealValue (números reales)
│   ├── BooleanValue (valores booleanos)
│   ├── StringValue (cadenas de texto)
│   └── Identifier (identificadores de variables)
├── Operaciones Binarias
│   ├── Aritméticas: Addition, Subtraction, Multiplication, Division, Modulo
│   ├── Lógicas: LogicalAnd, LogicalOr, LogicalXor
│   ├── Comparación: LessThan, GreaterThan, LessEqual, GreaterEqual, Equal, NotEqual
│   └── StringConcat (concatenación de strings)
├── Operaciones Unarias
│   ├── LogicalNot (negación lógica)
│   └── Conversiones: ConvertIntToReal, ConvertRealToInt, ConvertIntToString, ConvertRealToString
├── Operaciones con Pares
│   ├── Pair (creación de pares)
│   ├── First (primer elemento del par)
│   └── Second (segundo elemento del par)
├── Control de Flujo
│   ├── IfExpression (expresiones condicionales)
│   └── LetExpression (binding de variables)
└── Utilidades
    └── PrintExpression (impresión por pantalla)
```

### Características Principales

1. **Sistema de Tipos Dinámico**: Utiliza `std::variant<int, double, bool, std::string>` para manejar diferentes tipos de valores
2. **Gestión de Memoria**: Cada expresión maneja su propia limpieza de memoria através del método `destroy()`
3. **Entorno de Variables**: Clase `Environment` para manejar scope y binding de variables
4. **Evaluación Polimórfica**: Método virtual `eval()` que evalúa cada expresión en su contexto

## Sintaxis Soportada

### Operaciones Aritméticas
```
5 + 3           # Suma
2 * 4           # Multiplicación  
10 - 3          # Resta
8 / 2           # División
7 % 3           # Módulo
(2 + 3) * 4     # Precedencia con paréntesis
```

### Operaciones Lógicas
```
true and false  # AND lógico
true or false   # OR lógico
true xor false  # XOR lógico
not true        # Negación lógica
```

### Operaciones de Comparación
```
5 > 3           # Mayor que
5 < 3           # Menor que
5 >= 3          # Mayor o igual que
5 <= 3          # Menor o igual que
5 == 3          # Igual que
5 != 3          # Diferente que
```

### Tipos de Datos
```
42              # Enteros
3.14            # Números reales
true            # Booleanos
false
"Hola mundo"    # Strings
```

### Concatenación de Strings
```
"Hola" # " mundo"           # Concatenación
itos(42) # " es la respuesta" # Con conversión
```

### Conversiones de Tipo
```
itos(42)        # int a string
rtos(3.14)      # real a string
itor(42)        # int a real
rtoi(3.14)      # real a int
```

### Binding de Variables (Let)
```
let(x)(10)(x + 5)                    # Binding simple
let(x)(10)(let(y)(20)(x + y))        # Binding anidado
```

### Expresiones Condicionales
```
if(5 > 3)(42)           # If simple
if(false)(10) else (20) # If-else
```

### Pares
```
pair(1)(2)      # Crear par
fst(pair(1)(2)) # Primer elemento
snd(pair(1)(2)) # Segundo elemento
```

### Impresión
```
print("Hola mundo")     # Imprimir string
print(itos(42))         # Imprimir valor convertido
```

## Uso del Intérprete

### Compilación
```bash
make clean
make
```

### Ejecución

#### Desde stdin:
```bash
./interpreter
# Luego ingrese expresiones y presione Ctrl+D
```

#### Desde archivo:
```bash
echo "5 + 3" | ./interpreter
# o
./interpreter archivo.txt
```

### Ejemplos de Uso

```bash
# Operaciones aritméticas
echo "5 + 3 * 2" | ./interpreter
# Salida: Expresión: (5 + (3 * 2)), Resultado: 11, Tipo: addition

# Variables
echo "let(x)(10)(x * 2)" | ./interpreter  
# Salida: Expresión: let(x, 10, (x * 2)), Resultado: 20, Tipo: let_expression

# Condicionales
echo "if(5 > 3)(42) else (0)" | ./interpreter
# Salida: Expresión: if((5 > 3), 42, 0), Resultado: 42, Tipo: if_expression

# Conversiones y concatenación
echo 'itos(42) # " es la respuesta"' | ./interpreter
# Salida: Expresión: (itos(42) # " es la respuesta"), Resultado: "42"" es la respuesta", Tipo: string_concat
```

## Características Técnicas

- **Lenguaje**: C++17
- **Parser Generator**: GNU Bison (compatible con versión 2.3+)
- **Lexer Generator**: Flex
- **Compilador**: g++ con soporte C++17
- **Gestión de Memoria**: Manual con métodos `destroy()`
- **Sistema de Tipos**: Dinámico usando std::variant

## Precedencia de Operadores

1. `()` (paréntesis)
2. `not` (negación lógica)
3. `* / %` (multiplicación, división, módulo)
4. `+ -` (suma, resta)
5. `#` (concatenación de strings)
6. `< > <= >=` (comparación)
7. `== !=` (igualdad)
8. `and` (AND lógico)
9. `xor` (XOR lógico)
10. `or` (OR lógico)

## Limitaciones Actuales

1. No se han implementado funciones (`fun`) todavía
2. No hay soporte para arrays (`empty`, `head`, `tail`)
3. Los pares no están completamente implementados para extracción de elementos
4. No hay verificación de tipos en tiempo de compilación

## Arquitectura de Código

### Archivos Principales

- `expression.hpp/cpp`: Definición e implementación de todas las clases de expresiones
- `parser.bison`: Gramática BNF del lenguaje
- `scanner.flex`: Definición de tokens léxicos
- `main.c`: Programa principal del intérprete
- `Makefile`: Configuración de compilación

Este parser proporciona una base sólida y extensible para el desarrollo de un compilador completo, con una arquitectura limpia que facilita agregar nuevas características y tipos de expresiones.
