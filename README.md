# Creacion-de-funciones-en-cpp-

#include <iostream>
#include <conio.h>
#include <math.h>
#include <cstdlib>
#include <vector>
#include <iomanip>

/* construya las siguientes funciones:

1) bool tranquilo (int elemento)  ;
el objetivo de esta funcion es determinar los elementos del arreglo que son numeros
tranquilos si el elemento es tranquilo la funcion retorna true de lo contrario retorna false
lps mimeros tranquilos son los nnumeros de 3 cifras (entre 100 y 999) cuya multiplicacion de sus
digitos es menorque el fractorial del ultimo digito

por ejemplo si se lee el numero 955 no es tranquilo ya que 9*5*5=225 que es mayor que 5!=120

2) void llenar_arreglo (int A[], int n);
el objetivo de esta funcion es llenar el arreglo de manera que el usuario ingrese los elementos

3) void imprimir arreglo (int A[], int n);
esta funcion se encarga de imprimir los elemetos del arreglo que cumplan con la condicion de ser
numeros tranquilos (auxiliarse de la funcion tranquilo ) deben ser generados en forma horizontal
separado por un espacio

 el programa principal se leera el valor del numero de elementos del arreglo de tamaño n que sea
 mayor o igual que 1 y menor o igual 10 y se creara el arreglo de tamaño n (ingresado por el usuario))
 ademas se llamara alas funciones de acuerdo al momento en que se necesite y se debe imprimir los elementos
 del arreglo que cumplen la condicion de ser numeros tranquilos


*/

using namespace std;
// prototipos de funciones
void LlenarArreglo(int A[], int n);
bool Tranquilo(int elemento);
void ImprimirArreglo(int A[], int n);

int main()
{
    // valor del arreglo n
    int n;
    int A[n];

    if (n >= 1 && n <= 10)
    {
        cout << " digite elnumero de elementos del 1 al 10   " << endl;
        cin >> n;
    }

    // llamado a las funciones
    LlenarArreglo(A, n);
    ImprimirArreglo(A, n);
    bool Tranquilo(int elemento);

    getch();
    return 0;
}

// proceso de las funciones de acuerdo a lo solicitado
// funecion #1
void LlenarArreglo(int A[], int n)
{
    for (int i = 0; i < n; i++)
    {
        cout << "digite el elemento " << i + 1 << " del arreglo " << endl;
        cin >> A[i];
    }

    return;
}

// funcion #2
bool Tranquilo(int elemento)
{
    if (elemento >= 100 && elemento <= 999)
    {
        int a = elemento / 100;
        int b = (elemento % 100) / 10;
        int c = elemento % 10;
        int d = a * b * c;
        int e = 1;
        for (int i = 1; i <= c; i++)
        {
            e = e * i;
        }
        if (d < e)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
    else
    {
        return false;
    }
}

// funcion #3
void ImprimirArreglo(int A[], int n)
{

    for (int i = 0; i < n; i++)
    {
        if (Tranquilo(A[i]) == true)
        {
            cout << A[i] << " ";
        }
    }
    return;
}
