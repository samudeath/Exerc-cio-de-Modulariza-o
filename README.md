# Exerc-cio-de-Modulariza-o



// © Samuel Gomes Rocha © 
//Bacharelado em Sistemas de Informação 
//IFG - campus Inhumas
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
#include <locale.h>

//Declaração de uma variável global;
int i;

//Declaração de todas as funções no escopo estruturado e sequencial;
void meni();
void exUm();
void exDois();
void exTres();
void exQuatro();
void exCinco();
void exSeis();
void exSete();
void exOito();
void exNove();
void exDez();
void exOnze();
int tabuSoma(int nsoma);
int tabuSub(int nsub);
int tabuMult(int nmul);
float tabuDiv(float ndiv);
float dolar(float cota, float dola);
int min(int a, int b);
int max(int a, int b);
float media (float a, float b);
unsigned long int elevado(int x, int y);
int mult(int x, int y);
int anuidade(int d, int m, int a);
int calcIdade (int anof, int anoo, int diaf, int diao, int mesf, int meso);
int fatora(int n);

//Função principal;
int main(){
	setlocale(LC_ALL, "Portuguese");
	int verificador;
	
 	meni();
	printf(" Exercício correspondente ao número: ");
		scanf("%d", &verificador);
		
		printf("\n");
	
	
	if(verificador == 1){exUm();}
	
	if(verificador == 2){exDois();}
	
	if(verificador == 3){exTres();}
	
	if(verificador == 4){exQuatro();}
	
	if(verificador == 5){exCinco();}
	
	if(verificador == 6){exSeis();}
	
	if(verificador == 7){exSete();}
	
	if(verificador == 8){exOito();}
	
	if(verificador == 9){exNove();}
	
	if(verificador == 10){exDez();}
	
	if(verificador == 11){exOnze();}
	return 1;
}


//Funções void;
void meni(){
		
	printf("\n");	
	printf(" _______________________Menu_Principal___________________________\n");	
	printf("| Digite o número correspondente ao exercício a ser solucionado: |\n");
	printf("|                                                                         |\n");
	printf("| Exercício 1 = '1';                                              |\n");
	printf("| Exercício 2 = '2';                                             |\n");
	printf("| Exercício 3 = '3';                                             |\n");
	printf("| Exercício 4 = '4';                                             |\n");
	printf("| Exercício 5 = '5';                                             |\n");
	printf("| Exercício 6 = '6';                                             |\n");
	printf("| Exercício 7 = '7';                                              |\n");
	printf("| Exercício 8 = '8';                                             |\n");
	printf("| Exercício 9 = '9';                                             |\n");
	printf("| Exercício 10 = '10';                                         |\n");
   	printf("| Exercício 11 = '11';                                           |\n");
	printf("|________________________________________________________________|\n");
}

void exUm(){
        printf("                  ## Bem-vindx ao exercício 1: DATA GREGORIANA## \n \n");
        
   	int dia, mes, ano;
	
	printf("Digite uma data no formato (dd, mm, aaaa) e saiba se ela se encaixa no nosso calendário gregoriano:");
	scanf("%d", &dia);
	scanf("%d", &mes);
	scanf("%d", &ano);
	
	if(anuidade(dia, mes, ano) == 1){
		printf("  A data: %d/%d/%d corresponde à uma data gregoriana\n", dia, mes, ano);
	}
	
	if(anuidade(dia, mes, ano) == 0){
	printf("  A data %d/%d/%d não corresponde à uma data gregoriana\n", dia, mes, ano);}
	
	
}

void exDois(){
		printf("                  ## Bem-vindx ao exercício 2: TABUADA DE MULTIPLICAÇÃO ## \n \n");

	int n, res;
	
	printf("Digite um número entre 1 e 10 para saber sua tabuada (de multiplicação):");
	scanf("%d", &n);
		
		if(n < 0 || n >10){
			printf("Digite apenas valores que estejam entre os números inteiros 1 e 10\n");
		} else{
		
	printf("\n");
	printf("A tabuada do %d é:\n", n);
		
		for(i >= 0; i <= 10; i++){
			printf("\t %d x %d = %d\n", i, n, tabuMult(n));
		}
}
}

void exTres(){
		printf("                  ## Bem-vindx ao exercício 3: TABUADAS ## \n \n");
			int n;
			char x, vs;

	printf(" ______________________________________________________\n");	
	printf("| Conceituação das funções dos operadores artiméticos: |\n");
	printf("| '+' = Adição                                           |\n");
	printf("| '-' = Subtração                                      |\n");
	printf("| '*' = Multiplicação                                |\n");
	printf("| '/' = Divisão                                           |\n");
	printf("|______________________________________________________|\n");
	
	printf("\nDigite: número e operador aritmético, correspondentes à tabuada que deseja:");
	
	scanf("%d %c", &n, &x);
	
	printf("\n");
	
	if(x == '+'){
		printf("A tabuada de soma do %d é:\n", n);
			for(i >=0 ; i<=10; i++){
				printf("\t %d + %d = %d\n", n, i, tabuSoma(n));	
		}
	}
	
	if(x == '-'){
		printf("A tabuada de subtração do %d é:\n", n);
			for(i >=0 ; i<=10; i++){
				printf("\t %d - %d = %d\n", n, i, tabuSub(n));	
		}
		
	}
	
	if(x == '*'){
		printf("A tabuada de multiplicação do %d é:\n", n);
			for(i >=0 ; i<=10; i++){
				printf("\t %d * %d = %d\n", n, i, tabuMult(n));		
		}
		
	}
	
	if(x == '/'){
		printf("A tabuada de divisão do %d é:\n", n);
			for(i >=0 ; i<=10; i++){
		
				printf("\t %d / %d = %.2f\n", n, i, tabuDiv(n));		
		
				}
		
	}
	

}

void exQuatro(){
		printf("                  ## Bem-vindx ao exercício 4: IDADE ## \n \n");
		
	int af, ao, mf, mo, df, doo;
	
	printf("Digite a data de nascimento (dd, mm, aaaa): ");
	scanf("%d %d %d", &doo, &mo, &ao);
	
	printf("Digite a data atual (dd/ mm/ aaaa): ");
	scanf("%d %d %d", &df, &mf, &af);

	if(af==ao && mf==mo && df<doo){
		printf("Impossível calcular!");
	}
	if(af==ao && mf<mo){
		printf("Impossível calcular!");
	}
	
	if(af < ao){
		printf("Impossível calcular!");
	}
	
	if( calcIdade(af, ao, df, doo, mf, mo) > 1){
	printf("Idade: %d anos", calcIdade(af, ao, df, doo, mf, mo));
}
	if( calcIdade(af, ao, df, doo, mf, mo) == 1){
	printf("Idade: %d ano", calcIdade(af, ao, df, doo, mf, mo));		
	}

}

void exCinco(){
    printf("                  ## Bem-vindx ao exercício 5: CONVERSÃO DE MOEDA ## \n \n");
	
	float c, d;

	printf("Digite a cotação do dólar em reais: R$");
	scanf("%f", &c);
	printf("\n");
	
	printf("Digite o valor em dólar que deseja converter para reais: US$");
	scanf("%f", &d);
	printf("\n");
	
	printf("$%.2f é igual à R$%.2f\n", d, dolar(c, d));
	//No dia 04 de setembro de 2019 a cotação do dólar estava à R$ 4,13;
		
}

void exSeis(){
	printf("                  ## Bem-vindx ao exercício 6: FATORIALZERA## \n \n");
	int nf;
	
	printf("Digite um número inteiro: ");
	scanf("%d", &nf);
	printf("\n");
	
	printf("O fatorial de %d é: %d\n", nf, fatora(nf));
		
}

void exSete(){
	printf("                  ## Bem-vindx ao exercício 7: MÍNIMO ## \n \n");
	int x, y;
	
	printf("Digite dois valores inteiros distintos: ");
	scanf("%d %d", &x, &y);

	printf("Dentre %d e %d, %d é o menor!", x, y, min(x, y));
}

void exOito(){
	printf("                  ## Bem-vindx ao exercício 8: MÁXIMO ##\n \n");
		
	int x, y;
	
	printf("Digite dois valores inteiros distintos: ");
	scanf("%d %d", &x, &y);

	printf("Dentre %d e %d, %d é o maior!", x, y, max(x, y));
}

void exNove(){
	printf("                  ## Bem-vindx ao exercício 9: MÉDIA ARITMÉTICA ## \n \n");

	float x, y;
	
	printf("Digite dois números para saber sua média aritmética: ");
	scanf("%f %f", &x, &y);
	
	printf("\n");
	
	printf("A média aritimética entre %.1f e %.1f é: %.2f\n", x, y, media(x, y));
	
}

void exDez(){
	printf("                  ## Bem-vindx ao exercício 10: POTÊNCIA ## \n \n");
		
	unsigned long int xm, ym;
	
	printf("Digite a base e o expoente do seu cálculo de potenciação: ");
	scanf("%d %d", &xm, &ym);
	
	printf("\n");
	
	printf("O resultado de %lu elevado à %lu é: %lu\n", xm, ym, elevado(xm, ym));
}

void exOnze(){
	printf("                  ## Bem-vindx ao exercício 11: VALORES MÚLTIPLOS ## \n \n");

	int a, b;
	
	printf("Digite dois valores inteiros: ");
	scanf("%d %d", &a, &b);	
	
	if(mult(a, b) == 1){
	
	printf("%d e %d são múltiplos\n", a, b);
}else{
	printf("%d e %d não são múltiplos\n", a, b);
}
}


//Funções que retornam valores;
int tabuSoma(int nsoma){
	int  tsoma;
	
	for(i >=0; i <=10; i++){
	return	tsoma = nsoma+i;
	}
}

int tabuSub(int nsub){
	int  tsub;
	
	for(i >= 0; i <= 10 ; i++){
	return	tsub = nsub-i;
	}
}

int tabuMult(int nmul){
	int  tmul;
	
	for(i >=0; i <=10; i++){
	return	tmul = nmul*i;
	}
}

float tabuDiv(float ndiv){
	float  tdiv;
	
	for(i >=0; i <=10; i++){
	return	tdiv = ndiv/i;
	}
	
}

float dolar(float cota, float dola){
	float real;
	
	return real = dola*cota;
	
}

int min(int a, int b){
	if (a < b){
		return a;
	}
	if(b < a){
		return b;
	}
	
}

int max(int a, int b){
	if (a > b){
		return a;
	}
	if(b > a){
		return b;
	}
	
}

float media (float a, float b){
	float resultado;
	return resultado = (a+b)/2;	
}

unsigned long int elevado(int x, int y){
	
	unsigned long int res;
	return res = pow(x, y);
}

int mult(int x, int y){
	if(x%y == 0 || y%x == 0){
		return 1;
	}else{
		return 0;
	}	
}

int anuidade(int d, int m, int a){

	if((m >= 1 && m <= 12) && (d >= 1 && d<=31)){
	if((m == 2 && d == 29) && ((a%4) == 0) && ((a%100) != 0 )|| ((a%400) == 0)){return 1;}
	if((d <= 30) && (m ==4 || m == 6 || m==9 || m == 11)){return 1;}
	if((d <=31) && (m == 1 || m == 3 || m == 5 || m == 7 || m == 8 || m == 10 || m == 12)){return 1;}
	else{
	return 0;	
	}
													
}else{
	return 0;
}
}

int calcIdade (int anof, int anoo, int diaf, int diao, int mesf, int meso){
	int idade, mensalidade;
	
	return idade = anof - anoo;
	
	if (anof==anoo && mesf < meso){
	return 	idade = idade-1;
	}	
	
	if(anof == anoo && mesf == meso && diaf < diao){
	return 	idade = idade -1;
	}	
}
int fatora(int n){
	int fat = 1;
	
	for(; n > 1; n=n-1){
		fat=fat*n;
	}
		return fat;
}
