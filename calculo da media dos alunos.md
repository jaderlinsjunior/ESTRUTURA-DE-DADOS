ESTRUTURA-DE-DADOS
==================

SISTEMAS DE INFORMAÇÃO

//INÍCIO//

#include <stdlib.h>
#include <iostream>
#include <time.h>

using namespace std;
int const alunos = 15, nota = 4;
struct Aluno{
       int mat;
       float notas[nota], media;
       string status;
};


Aluno aluno1;

void mostrar_aluno();
void carrega_aluno();

int main(){
    srand(time(NULL));
    cout << "mat\t";
    for (int i = 1;i <= nota; i++){
        cout << "nota" << i << "\t";
    }
    cout << "media\tstatus\n";
    for(int i = 1;i<=alunos;i++){
    aluno1.mat = i;
    carrega_aluno();
    //mostrar_aluno();
    }
    
    system("PAUSE>null");
    return 0;
}


void carrega_aluno(){
     float soma = 0;
     for(int i = 0;i < nota;i++){
           aluno1.notas[i] = (float)(rand() % 91 + 10)/10;
           soma = soma + aluno1.notas[i];
     }
     aluno1.media = soma/nota;
     if (aluno1.media  >= 6) {
        aluno1.status = "Aprovado";
     } else {
       aluno1.status = "Reprovado";
     }
     mostrar_aluno();
}


void mostrar_aluno(){
     
     cout << aluno1.mat << "\t";
     for(int i = 0;i < nota;i++)
             cout << aluno1.notas[i] << "\t";
     cout << aluno1.media << "\t" << aluno1.status << "\n";     
}

//FIM//
