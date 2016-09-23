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

//--------------LUIBIA TORRES----------------//

int x=0; // utilizado no for ;
int quantidade=0; //controlar quant de produtos a vender;
float totalValorVendas= 0; // total a pagar ;
boolean encontrou; //ref pesquisa;
String texto; // texto scanner ;
String textoMais=null; // texto scanner add produtos ;
String produtosVendidos[][]= new String[300][3]; //PARA TESTAR A MATRIZ  EDITE P/ TAMANHO [3],[3] PORQUE ESTÁ COM 300 COMO FOI PEDIDO;
String clienteVendas[][]= new String[300][2]; //PARA TESTAR A MATRIZ  EDITE P/ TAMANHO [3],[2] PORQUE ESTÁ COM 300 COMO FOI PEDIDO;

System.out.println();

do {
	encontrou=false;
	textoMais=null;
		
	System.out.print ("Digite o Nome do produto a vender ('FIM' para encerrar): ");
		texto = leia.next();
			if(texto.equalsIgnoreCase("FIM")) { System.out.println("Encerrado com sucesso");
			break; }
	
	System.out.print ("Informe a quantidade desejada: ");
		quantidade=leia.nextInt();
			while(quantidade==0) { System.out.println("Informe a quantidade acima de zero");
			quantidade=leia.nextInt();
			}

	//Pesquisar produto e preço
		
			 for (x = 0; x < produtosCodNome.length; x++) {
				 				 
				 if (texto.equalsIgnoreCase(produtosCodNome[x][1])) {
					encontrou=true;
					produtosVendidos[x][1]=produtosCodNome[x][1]; //+ produtosValor[x]; //teste
					break;
				 	} 
				}
			 
			 	System.out.println("Produto encontrado - "  + produtosVendidos[x][1] + "  " + produtosValor[x] );
				System.out.println("total a pagar: R$ " + (quantidade * produtosValor[x]));
				totalValorVendas= totalValorVendas + (quantidade * produtosValor[x]);
				
			if (encontrou=false) {System.out.println("Produto não cadastrado");
	 			System.out.println("Deseja procurar outro produto? (Sim para continuar...  )");
				textoMais=leia.next();
	 				if(textoMais.equalsIgnoreCase("SIM")) { System.out.println("Escolha outro produto ... ");
	 				} else { break; } 
				}
	 		
			else { System.out.println("Deseja acrescentar produtos? (SIM ou NAO:) ");
			textoMais=leia.next();
				if(textoMais.equalsIgnoreCase("SIM")) { System.out.println(" Escolha outro produto ... ");
				} else if(textoMais.equalsIgnoreCase("Nao")) { 
				System.out.println("Prosseguir com a compra ..."); 
				}
				}
		
	//Pesquisar Cliente

		if(textoMais.equalsIgnoreCase("sim"))  {System.out.print(" ");}	
		 else { System.out.print("Digite o nome do Cliente: ");	
				texto=leia.next();
			
				for( x=0; x < cadastroCliente.length; x++) {
				 				
				if (texto.equals(cadastroCliente[x][1])) {
				encontrou=true;
				clienteVendas[x][1]=cadastroCliente[x][1];
				break;
				}
				}
				
				System.out.println("Cliente ("+ clienteVendas[x][1] + ") encontrado");
			
			}	
		
		
	//Realizar Vendas
				
	 if(textoMais.equalsIgnoreCase("sim"))  {System.out.print(" ");}	
			
	 else { System.out.println("Conferir o(s) produto(s)");
	 	for(int n=0; n < produtosVendidos.length; n++) { 
	 		System.out.println("Produto " + produtosVendidos[n][1] + " para o cliente " + (clienteVendas[x][1]));}
	 	System.out.println("Confirmar venda? SIM ou NAO: ");
	 	texto=leia.next();
	if(texto.equalsIgnoreCase("SIM")){ System.out.println("O total do valor das vendas é R$ " + totalValorVendas);
		} else{ System.out.println("Venda cancelada");
		break;}
	 }
	 	  //"? ('SIM' para confirmar)");
	 		
	
} while (texto!="FIM");

System.out.println("o total vendido foi: " + totalValorVendas);
System.out.println();
System.out.println("Finalizado com sucesso");

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

