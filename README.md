# AtividadeDesafio

//Carolina Mascarenhas
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

// Arthur Teixeira
