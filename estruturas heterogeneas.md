## ESTRUTURAS HETEROGÊNEAS

### **REGISTROS (STRUCTS)**

**Definição:** um tipo de estrutura da linguagem C que permite armazenar dados de tipo de diferentes tipos em uma única amostra ( objeto - não confundir com orientação a objeto -, instância).

Por exemplo: como definir as propriedades de um jogador de futebol no FIFA (jogo de videogame)?

1. definir quais são essas propriedades e seus respectivos de dados;
2. reuni-los numa estruct;
3. declarar a struct como um tipo de dados.


```

#include <stdio.h>
#include <string.h>

struct atleta {
    int velocidade;
    char nome[51];
    double altura_pulo;
}; 
  // não esquecer do ponto e virgula dps de fechar as chaves da struct.

typedef struct atleta Atleta;
 // entao o typedef cria um tipo a partir da estrutura(registro) criada.

void imprimeJogadores (Atleta jogs[30], int n){
    int i;

    for (int i = 0; i < n; i++){
    printf("\nDados do Jogador %d\n", i+1);
    printf("Nome: %s\n", jogs[i].nome);
    printf("%d\n", jogs[i].velocidade);
    printf("Altura do pulo: %.2lf\n", jogs[i].altura_pulo);
    }

}

int main (){
    int i, n;
    Atleta elenco[30];

    scanf("%d", &n);

    for(int i = 0; i < n; i++){
        scanf("%d", &elenco[i].velocidade);
        scanf("%d", &elenco[i].altura_pulo);
        getchar();
        scanf("%s", elenco[i].nome);
    }
  


    imprimeJogadores(elenco,n);

    return 0;
}
