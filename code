/*Patricia Rocha*/
#include <cstdlib>
#include <iostream>
#include <fstream>
#include <string.h>
using namespace std;
/*Criação da estrutura.*/
struct transacao{
    string tipo;
    int cod;
    int qnt;
    double valor;
    transacao *prox,*prim,*ultimo;
};
void compra(int qnt, double valor, int cod, transacao*&vet ){
    /*Função compra: recebe informações do usuário e salva nas variaveis da struct*/
        cout<<"Informe o codigo da transação: "<<endl;
        cin>>cod;
        cout<<"Informe a quantidade de ações compradas: "<<endl;
        cin>>qnt;
        cout<<"Informe o valor (unitário) das ações: "<<endl;
        cin>>valor;
        
        if(vet==NULL){
            vet=new transacao;  
            /*O vetor recebe as informações do usuario*/
        vet->cod=cod;
        vet->qnt=qnt;
        vet->valor=valor;
        vet->prim=vet;
        vet->ultimo=vet;
        vet->prox=NULL;
        vet->tipo="compra";/*Transação do tipo compra.*/
        }
        else{
         /*O vetor recebe as informações do usuario*/
        vet->ultimo->prox=new transacao;
        vet->ultimo=vet->ultimo->prox;
        vet->ultimo->cod=cod;
        vet->ultimo->qnt=qnt;
        vet->ultimo->valor=valor;
        vet->ultimo->prox=NULL;
        vet->tipo="compra";/*Transação do tipo compra.*/
        }
}
void venda(int qnt, double valor, int cod, transacao*&vet){
    /*Função venda: recebe informações do usuário e salva nas variaveis da struct*/
        cout<<"Informe o codigo da transação: "<<endl;
        cin>>cod;
        cout<<"Informe a quantidade de ações vendidas: "<<endl;
        cin>>qnt;
        cout<<"Informe o valor (unitário) das ações: "<<endl;
        cin>>valor;
    if(vet==NULL){
            vet=new transacao;
            /*O vetor recebe as informações do usuario*/
            vet->cod=cod;
        vet->qnt=qnt;
        vet->valor=valor;
        vet->prim=vet;
        vet->ultimo=vet;
        vet->prox=NULL;
        vet->tipo="venda";/*Transação do tipo venda.*/
        }
        else{
        /*O vetor recebe as informações do usuario*/
         vet->ultimo->prox=new transacao;
         vet->ultimo=vet->ultimo->prox;
         vet->ultimo->cod=cod;
         vet->ultimo->qnt=qnt;
         vet->ultimo->valor=valor;
         vet->ultimo->prox=NULL;
         vet->tipo="venda";/*Transação do tipo venda.*/
        }
}
int saldoTotal (int sal, transacao *vet){
    /*Mostra o resultado final das operações de compra e venda.*/
    sal=0;
    int auxc,auxv;
    while(vet != NULL){
        if(vet->tipo=="compra"){
            auxc=vet->qnt*vet->valor;
           sal -=auxc;
        }
        if(vet->tipo=="venda"){
            auxv=vet->qnt*vet->valor;
            sal +=auxv;
        }       
        vet=vet->prox;
    }
    /*O valor de 'compras' é subtraido de 'vendas'.*/
    cout<<sal;
    return 0;
}
void exibirTrans(transacao* vet){
    /*Imprime na tela os dados das transações.*/
    while(vet != NULL){
        cout<<"Código  Quantidade de ações     Valor unitário"<<endl;
        cout<<vet->cod<<vet->qnt<<vet->valor;
        vet=vet->prox;
    } 
}
void pesquisar(int cod,transacao *vet){
    /*Busca com o codigo fornecido pelo usuario*/
    cout<<"Código da transação: ";
    cin>>cod;
    while(vet!=NULL){
        /*Verifica se o código é igual.*/
        if(vet->cod==cod){
        cout<<"Código  Quantidade de ações     Valor unitário"<<endl;
        cout<<vet->cod<<vet->qnt<<vet->valor; 
        }
        vet=vet->prox;
   }
}

int main(int argc, char** argv) {
    int op = 10000;
    int cod,qnt,valor,sal,n;
    transacao *vet;
    vet=NULL;
    
    while (op!=0){
        /*Imprimir o menu.*/
		cout<<"\t"<<"MENU"<<endl;
                cout<<".............................."<<endl;
		cout<<"1. Compra de ações."<<endl;
		cout<<"2. Venda de ações."<<endl;
		cout<<"3. Exibir saldo de capital."<<endl;
		cout<<"4. Exibir transações."<<endl;
                cout<<"5. Pesquisar transação."<<endl;
                cout<<"6. Sair."<<endl;
		cout<<".............................."<<endl;
                cin>>op;
                cout<<endl;
        switch (op){
            /*Cada caso faz uma chadada de função.*/
            case 1:{
                    compra(qnt,valor,cod, vet);
            }
            break;
            case 2:{
                    venda(qnt,valor,cod, vet); 
            }
            break;
            case 3:{
            saldoTotal (sal,vet);
            }
            break;
            case 4:{
                exibirTrans(vet);
            }
            break;
            case 5:{
                pesquisar(cod,vet);
            }
                break;
            case 6:
                return 0;
            break;
            /*Caso o usuario digite uma opção inválida.*/
              default:
                  cout<<"Opcao inexistente. "<<endl;
        }
    }
    return 0;
}
