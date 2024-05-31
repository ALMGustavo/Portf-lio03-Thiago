#include <stdio.h>

#define MAX_ITENS 100

int main() {
    char id[MAX_ITENS][6];
    char nome[MAX_ITENS][50];
    float unitario[MAX_ITENS];
    int qtde[MAX_ITENS];
    float total_item[MAX_ITENS];
    int num_itens;
    float total_final = 0.0;

    printf("Quantos itens deseja inserir?\n ");
    scanf("%d", &num_itens);

    for (int i = 0; i < num_itens; i++) {
        printf("\nItem %d\n", i + 1);

        printf("ID (Codigo do item): ");
        scanf("%s", id[i]);

        printf("Nome: ");
        scanf("%s", nome[i]);

        printf("Valor Unitario: ");
        scanf("%f", &unitario[i]);

        printf("Quantidade: ");
        scanf("%d", &qtde[i]);

        total_item[i] = unitario[i] * qtde[i];
        total_final += total_item[i];
    }

    printf("\nCODIGO\tNOME\t\t\tQTDE\tUNIT\tTOTAL\n");
    for (int i = 0; i < num_itens; i++) {
        printf("%s\t%-20s\t%d\t%.2f\t%.2f\n", id[i], nome[i], qtde[i], unitario[i], total_item[i]);
    }

    printf("\nTOTAL FINAL\t\t\t\t\t%.2f\n", total_final);

    return 0;
}
