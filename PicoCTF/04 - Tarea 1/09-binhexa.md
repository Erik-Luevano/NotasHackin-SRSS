How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 63870`

### Solución
WebSehll, Python

```
erik616-picoctf@webshell:~$ nc titan.picoctf.net 63870

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01101101
Binary Number 2: 01111100


Question 1/6:
Operation 1: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 0b111110
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b11101001
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b1111101
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 0b11011010
Correct!

Question 5/6:
Operation 5: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b1101100
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0b11010011001100
Correct!

Enter the results of the last operation in hexadecimal: 0x34cc

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_1367e2c6}


Para hacer las operaciones se realizo un codiguito:

def operaciones_binarias(a, b, operacion):

    if operacion == '+':

        resultado = bin(a + b)

    elif operacion == '-':

        resultado = bin(a - b)

    elif operacion == '*':

        resultado = bin(a * b)

    elif operacion == '>>':

        num = input("Elige el número a o b: ")

        if num == 'a':

            resultado = bin(a >> 1)

        elif num == 'b':

            resultado = bin(b >> 1)

        else:

            print("Número inválido para elegir")

            return None

    elif operacion == '<<':

        num = input("Elige el número a o b: ")

        if num == 'a':

            resultado = bin(a << 1)

        elif num == 'b':

            resultado = bin(b << 1)

        else:

            print("Número inválido para elegir")

            return None

    elif operacion == '&':

        resultado = bin(a & b)

    elif operacion == '|':

        resultado = bin(a | b)

    else:

        print("Operación inválida")

        return None

  

    return resultado

  

if __name__ == "__main__":

    a = input("Ingresa el número a en binario: ")

    b = input("Ingresa el número b en binario: ")

    a = int(a, 2)

    b = int(b, 2)

  

    for i in range(6):

        operacion = input("Elige la operación binaria: ")

  

        resultado = operaciones_binarias(a, b, operacion)

        if resultado:

            print("Resultado binario:", resultado)

            if i == 5:

                print(f"Resultado hexadecimal: {hex(int(resultado, 2))}")
```