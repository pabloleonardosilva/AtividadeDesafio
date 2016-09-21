# AtividadeDesafio

// Carolina Mascarenhas - cadastro de Produtos

import java.util.*;

public class Cadastro_Produtos2 {

	public static void main(String[] args) {
		
		Scanner leia = new Scanner(System.in);
		
		int quantProdutos; 
						
		System.out.print("Digite o número de produtos a serem cadastrados: ");
		quantProdutos = leia.nextInt();
		
		String produtosCodNome[][] = new String[quantProdutos][2];
		float produtosValor[] = new float[quantProdutos];
		
		for (int i = 0; i < produtosValor.length; i++) {
			
			System.out.print("Digite o CÓDIGO do produto "+i+" (* FIM * PARA ENCERRAR CADASTRO): ");
			produtosCodNome[i][0] = leia.next();
			
			if (produtosCodNome[i][0].equalsIgnoreCase("FIM")) {
				break;
			}
			
			System.out.print("Digite o NOME do produto "+i+": ");
			produtosCodNome[i][1] = leia.next();
					
			do {
				System.out.print("Digite o VALOR do produto "+i+": ");
				produtosValor[i] = leia.nextFloat();
					
				if (produtosValor[i] <= 0) {
					System.out.println("ERRO! Digite valor maior que 0");
				} 
			
				
			} while (produtosValor[i] <= 0);
		
			System.out.println(); // SOMENTE PARA DAR ESPAÇO
			System.out.println("Cadastro Produto de número " + i + " finalizado!");
			System.out.println(); // SOMENTE PARA DAR ESPAÇO
			
		} 
		System.out.println(); // SOMENTE PARA DAR ESPAÇO
		System.out.println("Sistema de Cadastro de produtos Encerrado/Finalizado");
		
	} 
		
}

// Arthur Teixeira - Cadastro de Pessoas

public class CadastroPessoas {
public static void main(String[] args) {

    // LIGANDO O SCANNER - LEIA
    Scanner leia = new Scanner(System.in);

    // entrada de dados
    int quantCad; // VARIAVEL

    System.out.println("Digite Quantos Clientes quer Cadastrar: ");
    quantCad  = leia.nextInt(); 

    // VARIAVEIS CADASTRO
    int i = 0  ;                                            //Contador do Cadastro
    String [][] cadastroCliente = new String [quantCad][2];         // Matriz


    // entrada de dados - LOOP

    for (i = 0; i < cadastroCliente.length; i++) {


        System.out.println("Digite o código do Cliente " + i + " (* FIM * PARA ENCERRAR CADASTRO): ");
        cadastroCliente[i][0] = leia.next();

        if (cadastroCliente[i][0].equalsIgnoreCase("FIM")) {
            break;
        }

        System.out.println("Digite o nome do Cliente " + i + " (* FIM * PARA ENCERRAR CADASTRO): ");
        cadastroCliente[i][1] = leia.next();

        if (cadastroCliente[i][0].equalsIgnoreCase("FIM")) {
            break;
        }

        System.out.println();

        System.out.println("Cadastro de número " + i + " Concluído");

        System.out.println();

        if (cadastroCliente[i][1].equalsIgnoreCase("FIM")) {
            break;
        }

    }

    System.out.println("Cadastro Finalizado/Interrompido"); 

    }
    }
/** CAMILA COSTA **/

    System.out.println(); // SOMENTE PARA DAR ESPAÇO
    System.out.println("LISTAS DE CLIENTES");

    int idx = 0;
    for (String[] c : cadastroCliente) {
        System.out.println("Cliente: " + c[0] + "-" + c[1]);
    }

    System.out.println(); // SOMENTE PARA DAR ESPAÇO
    System.out.println("LISTAS DE PRODUTOS");
    idx = 0;
    for (String[] p : produtosCodNome) {            
        System.out.println("Produto: " + p[0] + "-" + p[1] + " Valor: " + produtosValor[idx]);
        idx++;
    }       
    leia.close();
}
}
//MENU PABLO import java.util.Scanner; public class TrabalhoATP {

public static void main(String[] args) {
    // TODO Auto-generated method stub

    // Carolina Mascarenhas - cadastro de Produtos


        Scanner leia = new Scanner(System.in);

        int quantProdutos; 
        int opcaoMenu;
        int quantCad;
        char conf='s';

        // PABLO LEONARDO
        while(conf=='s'){// controla se o cliente quer continuar no sistema ou se quer sair

            System.out.println("****************************************SEJAM BEM VINDO AO SISTEMA BLA BLA BLA****************************************");
            System.out.println(" ");
            System.out.println("-----------------DIGITE O NÚMERO CORRESPONDENTE À OPÇÃO DESEJADA OU DIGITE # PARA ENCERRAR O PROGRAMA-----------------");

            System.out.println("");


            //lista de opções
            System.out.println("1 - CADASTRAR PESSOAS");
            System.out.println("2 - CADASTRAR PRODUTOS");
            System.out.println("3 - EMITIR RELATÓRIO DE PESSOAS CADASTRADAS");
            System.out.println("4 - EMITIR RELATÓRIOS DE PRODUTOS CADASTRADOS");
            System.out.println("5 - REALIZAR UMA VENDA");


            opcaoMenu=leia.nextInt();


            switch (opcaoMenu) {
                case 1:
                     // VARIAVEL

                    System.out.println("Digite Quantos Clientes quer Cadastrar: ");
                    quantCad  = leia.nextInt(); 

                    // VARIAVEIS CADASTRO
                    int i = 0  ;                                            //Contador do Cadastro
                    String [][] cadastroCliente = new String [quantCad][2];         // Matriz


                    // entrada de dados - LOOP

                    for (i = 0; i < cadastroCliente.length; i++) {


                        System.out.println("Digite o código do Cliente " + i + " (* FIM * PARA ENCERRAR CADASTRO): ");
                        cadastroCliente[i][0] = leia.next();

                        if (cadastroCliente[i][0].equalsIgnoreCase("FIM")) {
                            break;
                        }

                        System.out.println("Digite o nome do Cliente " + i + " (* FIM * PARA ENCERRAR CADASTRO): ");
                        cadastroCliente[i][1] = leia.next();

                        if (cadastroCliente[i][0].equalsIgnoreCase("FIM")) {
                            break;
                        }

                        System.out.println();

                        System.out.println("Cadastro de número " + i + " Concluído");

                        System.out.println();

                        if (cadastroCliente[i][1].equalsIgnoreCase("FIM")) {
                            break;
                        }

                    }

                    System.out.println("Cadastro Finalizado/Interrompido"); 
                    break;


                case 2:
                    System.out.print("Digite o número de produtos a serem cadastrados: ");
                    quantProdutos = leia.nextInt();

                    String produtosCodNome[][] = new String[quantProdutos][2];
                    float produtosValor[] = new float[quantProdutos];

                    for (i = 0; i < produtosValor.length; i++) {

                        System.out.print("Digite o CÓDIGO do produto "+i+" (* FIM * PARA ENCERRAR CADASTRO): ");
                        produtosCodNome[i][0] = leia.next();

                        if (produtosCodNome[i][0].equalsIgnoreCase("FIM")) {
                            break;
                        }

                        System.out.print("Digite o NOME do produto "+i+": ");
                        produtosCodNome[i][1] = leia.next();

                        do {
                            System.out.print("Digite o VALOR do produto "+i+": ");
                            produtosValor[i] = leia.nextFloat();

                            if (produtosValor[i] <= 0) {
                                System.out.println("ERRO! Digite valor maior que 0");
                            } 


                        } while (produtosValor[i] <= 0);

                        System.out.println(); // SOMENTE PARA DAR ESPAÇO
                        System.out.println("Cadastro Produto de número " + i + " finalizado!");
                        System.out.println(); // SOMENTE PARA DAR ESPAÇO

                    } 
                    System.out.println(); // SOMENTE PARA DAR ESPAÇO
                    System.out.println("Sistema de Cadastro de produtos Encerrado/Finalizado");


            case 3:
                // colocar aqui o código de emitir relatório de pessoas
                break;

            case 4:
                // colocar aqui código de emitir relatório de produtos
                break;

            case 5:
                // colocar aqui o código de fazer vendas
                break;



            } // fim do switch case

            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");

            System.out.println("Deseja realizar outra operação? S - SIM      N-NÃO");
            conf=leia.next().charAt(0);
        }// fim do while

