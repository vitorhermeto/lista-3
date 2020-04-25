# lista-3
lista de exercicios

exercicio 1
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int i, aux, troca, V[10];

int main(){

    for(i=0; i<10; i++)
    {
        printf("\nDigite um número: \t");
        scanf("%d",&V[i]);
    }

    troca = 1;
    while (troca == 1) {
        troca = 0;        
        for (i = 0; i <= 8; i++)
        {
            if (V[i] < V[i + 1])
            {
                troca = 1;
                aux = V[i];
                V[i] = V[i + 1];
                V[i + 1] = aux;
            }
        }
    }
    printf("\n Valores ordenados \n");
    imprimir();

    return 0;
}

void imprimir(){

    for (i=0; i<10; i++){

        printf("%d\n", V[i]);
    }
}

exercicio2

#include <stdlib.h>
#include <stdio.h>
#include <string.h>

struct armazenar{
    char nome[10][20];
    int salario[10];
};

int main (){
    struct armazenar f;
    int i, troca, aux, j, x, menor;
    char aux1[10];

    for(i=0;i<10;i++){
        printf("nome do funcionario ");
        scanf("%s", f.nome[i]);
        printf("salario do funcionario: ");
        scanf("%d", &f.salario[i]);
    }


    for(i=0;i<10;i++){
        printf("nome : %s --> ", f.nome[i]);
        printf(" salario: %d \n", f.salario[i]);
    }
    
troca = 1;
    while (troca == 1) {
        troca = 0;        
        for (i = 0; i <= 8; i++)
        {
            if (f.salario[i] < f.salario[i + 1])
            {
                troca = 1;
                aux = f.salario[i];
                f.salario[i] = f.salario[i + 1];
                f.salario[i + 1] = aux;
            }
        }
    }
	
	for(i = 0; i < 10 - 1; i++)
        {
                x = 0;
                menor = i;
                for(j = i + 1; j < 10; j++)
                {
                    x = 0;
                    while(f.nome[menor][x] == f.nome[j][x])
                    {
                            x++;
                    } 
                    if(f.nome[menor][x] > f.nome[j][x])
                    {
                         menor = j;
                    }
                }
                if(menor != i)
                {
                        strcpy(aux1, f.nome[menor]);
                        strcpy(f.nome[menor], f.nome[i]);
                        strcpy(f.nome[i], aux1);
                }
        }
	
	for (i=0; i<10; i++){

        printf("%d\n", f.salario[i]);    
}
for (i=0; i<10; i++){

        printf("%s%c \n", f.nome[i]);    
}
    return 0;
}

exercicio3

#include <stdlib.h>
#include <stdio.h>
#include <string.h>

struct armazenar{
    char descricao[10][100];
    int preco[10], codigo[10];
};
struct produto{
	char nome[10][20];
	struct armazenar conjunto[10];
};

int main(){

    struct produto f;
    int i, troca, aux, j, x, menor;
    char aux1[10];

    for(i=0;i<10;i++){
        printf("nome do produto: ");
        scanf("%s", f.nome[i]);
        printf("codigo do produto: ");
        scanf("%d", &f.conjunto[i].codigo);
        printf("preço do produto: ");
        scanf("%d", &f.conjunto[i].preco);
        printf("descrição do produto: ");
        scanf("%s", f.conjunto[i].descricao);
    }

	for(i = 0; i < 10 - 1; i++)
        {
                x = 0;
                menor = i;
                for(j = i + 1; j < 10; j++)
                {
                    x = 0;
                    while(f.nome[menor][x] == f.nome[j][x])
                    {
                            x++;
                    } 
                    if(f.nome[menor][x] > f.nome[j][x])
                    {
                         menor = j;
                    }
                }
                if(menor != i)
                {
                        strcpy(aux1, f.nome[menor]);
                        strcpy(f.nome[menor], f.nome[i]);
                        strcpy(f.nome[i], aux1);
                }
        }
	
	for (i=0; i<10; i++){

        printf("%s\n", f.nome[i]);
		printf("%d\n", f.conjunto[i].codigo);
		printf("%d\n", f.conjunto[i].preco);
		printf("%s\n", f.conjunto[i].descricao);    
}

    return 0;
}
