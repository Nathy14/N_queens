#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h> 
#define tam 4

//verifica se é possível colocar a dama em determiada posição
//do tabuleiro de xadrez
bool verifica(int tabuleiro[tam][tam], int linha, int coluna){
  int i,j;
   //Verifica a linha
  for (i = 0; i < coluna; i++) 
    if (tabuleiro[linha][i]==1) 
      return false; 

    // Verifica a diagonal superior
  for (i = linha, j = coluna; i >= 0 && j >= 0; i--, j--) 
    if (tabuleiro[i][j]==1) 
      return false; 
  
    //Verifica a diagonal inferior
  for (i = linha, j = coluna; j >= 0 && i < tam; i++, j--) 
    if (tabuleiro[i][j]==1) 
      return false; 
  
  return true; 
} 

bool n_queens(int tabuleiro[tam][tam], int coluna){
    //se todas as damas estão corretas
    if (coluna >= tam){ 
      return true;
    } 
    //alternando as linhas e fixando uma coluna
    for (int i = 0; i < tam; i++) { 
        if (verifica(tabuleiro, i, coluna)) { 
            tabuleiro[i][coluna] = 1;
            //testando as próximas colunas e alternando as linhas
            if (n_queens(tabuleiro, coluna + 1)==true) 
                return true; 
            
            tabuleiro[i][coluna] = 0;  
        } 
    } 
    return false; 
} 

int main(void) {
  int tabuleiro[tam][tam] = {  { 0, 0, 0, 0 }, 
                               { 0, 0, 0, 0 }, 
                               { 0, 0, 0, 0 }, 
                               { 0, 0, 0, 0 } };

  bool teste = n_queens(tabuleiro, 0);
  if (teste == false)  
        printf("Não existe solução para este problema\n"); 
  for (int i = 0; i < tam; i++) { 
        for (int j = 0; j < tam; j++) 
            printf(" %d ", tabuleiro[i][j]); 
        printf("\n"); 
  }
}
