import os
import sys

def menu():
    os.system('cls')
    print("Selecciona una opción")
    print("\t1 - Escribir contenido")
    print("\t2 - Guardar y Nombrar archivo ")
    print("\t3 - Abrir Ultimo Archivo")
    print("\t9 - Salir")


def main(n=''):
    t = ''
    while True:
        menu()
        iter = input("inserta un numero valor (1-9)")
        if iter == "1":
            print("")
            input("Has pulsado la opción 1...\nEscribe el contenido del texto(escribe '<>' para finalizar)")
            for line in sys.stdin:
                if line == '<>\n':
                    break
                for var in line.split():
                    t += var
        elif iter == "2":
            print("")
            n =input("Has pulsado la opción 2...\nEscribe el nombre del archivo\n")
            file = open(f'{n}.txt', "w")
            file.write(t + os.linesep)
            file.close()
        elif iter == "3":
            print("")
            input(f"Se abrira el archivo {n}.txt\npulsa una tecla para continuar")
            os.system(f"start {n}.txt")
        elif iter == "9":
            break
        else:
            print("")
            input("No has pulsado ninguna opción correcta...\npulsa una tecla para continuar")


if __name__ == "__main__":
    main()