#include<iostream>
using namespace std;

char vetor[3][3];

void jogadorVencedor(char vetor[][3], int i, int j){
    if (vetor[i][j]== 'X')
    {
        cout<<"Jogador 2 venceu.\n";
    } else{
        cout<<"Jogador 1 venceu.\n";
    }
    
}
bool jogoAcabou(char vetor[][3], int n){
    char teste, aux;
    bool flag=false;
    // diagonal principal
    for (size_t i = 1; i < n; i++) {
        if(vetor[i][i]==vetor[i-1][i-1]){
            flag = true;
        } else{
            flag = false;
            break;
        }
    }
    if (flag == true){
        jogadorVencedor(vetor, 1, 1);
        return flag;
    }

    //diagonal secundaria 00 01 02 / 10 11 12 / 20 21 22
    for (size_t i = 1; i < n; i++)
    {   
        for (size_t j = 0; j < n; j++)
        {   
            
            if (i+j == n-1)
            {
                if (vetor[i][j]==vetor[i-1][j+1])
                {
                    flag = true;
                    
                } else {
                    flag = false;
                    break;
                }
                
            }
            
        }
        if(flag==false){
            break;
        }
        
    }
    if (flag == true){
        jogadorVencedor(vetor, 1, 1);
        return flag;
    }
    
    // Vertical 1
    for (size_t i = 1; i < n; i++)
    {   
        if (vetor[i][0] == vetor[i-1][0])
        {
            flag = true;
        } else{
            flag = false;
            break;
        }
        
    }
     if (flag == true){
        jogadorVencedor(vetor, 1, 0);
        return flag;
    }
    //Vertical 2
    for (size_t i = 1; i < n; i++)
    {   
        if (vetor[i][1] == vetor[i-1][1])
        {
            flag = true;
        } else{
            flag = false;
            break;
        }
        
    }
     if (flag == true){
        jogadorVencedor(vetor, 1, 1);
        return flag;
    }
    //Vertical 3
    for (size_t i = 1; i < n; i++)
    {   
        if (vetor[i][2] == vetor[i-1][2])
        {
            flag = true;
        } else{
            flag = false;
            break;
        }
        
    }
     if (flag == true){
        jogadorVencedor(vetor, 1, 2);
        return flag;
    }
    // Horizontais
    for (size_t i = 0; i < n; i++)
    {   flag = true;
        int j;
        for (j = 1; j < n && flag==true; j++)
        {
            if (vetor[i][j]== vetor[i][j-1])
            {
                flag = true;
            } else {
                flag = false;
                break;
            }
        }
        if (flag == true){
            jogadorVencedor(vetor, i, 2);
            return flag;
        }   
    }
    
    return flag; 
}
bool coloca(char vetor[3][3], int linha, int coluna, int jogador){
    char valor;
    
    if(jogador==1){
        valor = 'O';
    } else{
        valor = 'X';
    }
    //Verifica o range 
    if(!((linha-1 < 3 && linha - 1 >=0) && (coluna-1 < 3 && coluna >=0)) ){
        cout<<"Posicao escolhida fora do tamanho da matriz."<<endl;

        return false;
    }
    //Verifica se  a posicao esta ocupada, se f significa q esta vazia
    if(vetor[linha-1][coluna-1]== 'f'){
        vetor[linha-1][coluna-1] = valor;
        return true;
    } 
    cout<<"Essa posicao ja esta ocupada, escolha novamente!"<<endl;
    
    return false;
    
}

void imprime (char vetor[3][3], int n){
    for (size_t i = 0; i < n; i++)
    { 
        if (i==0)
        {
            cout<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<endl;
        }            
        cout<<'#';
        for (size_t j = 0; j < n; j++)
        {   
            if(vetor[i][j]== 'f'){
                cout<<" - ";
            } else {
                cout<<" "<< vetor[i][j]<<" ";
            }
        }
        cout<<'#';
        cout<<"     Linha "<< i+1;
        cout<<endl;        
        if(i==2){
            cout<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<'#'<<endl;
        }
    }
    
}
int main(int argc, char const *argv[])
{   
    bool posicaoCorreta=false;
    int n=3, jogador=1, linha, coluna,contaJogada=1;
    for (int i = 0; i < n; i++)
    {   
        for (int j = 0; j < n; j++)
        {
            
            vetor[i][j] = 'f' ;
            
        }
        
    }
    // Coloca o Bola e o X
    imprime(vetor, n);
    bool flag = false;
    while(contaJogada <= 9 && !flag){
        
        while(posicaoCorreta==false){
            cout<<"Player "<< jogador<<endl;
            cout<<"-----Escolha sua posicao-----"<< endl;
            cout<<"Linha: ";
            cin>>linha;
            cout<<"Coluna: ";
            cin>>coluna;
            
            posicaoCorreta = coloca(vetor, linha, coluna, jogador);      
        }
        
        if(jogador==1){
            jogador++;
        }   else {
            jogador--;
        } 
        posicaoCorreta = false;
        system("cls");      
        imprime(vetor, n);
        
        if (contaJogada>4)
        {
           flag = jogoAcabou(vetor, n);
        }
        
        contaJogada++;
    }
    cout<<"O jogo acabou."<<endl;
    system("pause");
    return 0;
}
