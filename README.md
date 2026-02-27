# movimento-pecas-xadrez-c
Trabalho da faculdade 

#include <stdio.h>

#define TAM 8

void mostrarTabuleiro() {
    for(int i = 0; i < TAM; i++) {
        for(int j = 0; j < TAM; j++) {
            printf("[ ]");
        }
        printf("\n");
    }
}

void movimentoTorre(int linha, int coluna) {
    printf("\nMovimentos possíveis da Torre:\n");

    for(int i = 0; i < TAM; i++) {
        if(i != linha)
            printf("(%d, %d)\n", i, coluna);
    }

    for(int j = 0; j < TAM; j++) {
        if(j != coluna)
            printf("(%d, %d)\n", linha, j);
    }
}

void movimentoBispo(int linha, int coluna) {
    printf("\nMovimentos possíveis do Bispo:\n");

    for(int i = 1; i < TAM; i++) {
        if(linha + i < TAM && coluna + i < TAM)
            printf("(%d, %d)\n", linha + i, coluna + i);

        if(linha - i >= 0 && coluna - i >= 0)
            printf("(%d, %d)\n", linha - i, coluna - i);

        if(linha + i < TAM && coluna - i >= 0)
            printf("(%d, %d)\n", linha + i, coluna - i);

        if(linha - i >= 0 && coluna + i < TAM)
            printf("(%d, %d)\n", linha - i, coluna + i);
    }
}

int main() {
    int opcao, linha, coluna;

    mostrarTabuleiro();

    printf("\nEscolha a peça:\n");
    printf("1 - Torre\n");
    printf("2 - Bispo\n");
    printf("Opção: ");
    scanf("%d", &opcao);

    printf("Digite a linha (0-7): ");
    scanf("%d", &linha);

    printf("Digite a coluna (0-7): ");
    scanf("%d", &coluna);

    if(opcao == 1)
        movimentoTorre(linha, coluna);
    else if(opcao == 2)
        movimentoBispo(linha, coluna);
    else
        printf("Peça inválida!\n");

    return 0;
}
