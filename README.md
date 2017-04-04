# jeff-aps01

package matrixGenerator;
import java.io.BufferedReader;
import java.io.File;
import java.io.FileReader;
import java.io.IOException;


/* Implementar um programa, que lê um arquivo contendo a descrição de uma matriz contendo 
apenas os valores 1 e 0, e imprimir, na tela, a matriz contida no arquivo. 
Com a matriz carregada em memória, criar duas cópias da matriz, 
e, em uma delas, trocar os valores 1 para 2, e na outra, trocar os valores 0 para 2.
*/

public class Main {
	
	public static void main(String [] args){
	
		int[][] numArray;
		
	try {
		File file = new File("src/matrixGenerator/teste.txt");
		FileReader fileReader = new FileReader(file);
		BufferedReader bufferedReader = new BufferedReader(fileReader);
		StringBuffer stringBuffer = new StringBuffer();
		String 	line = bufferedReader.readLine();
		//String pulaCabecalho =  bufferedReader.readLine();	
			
		//Tamanho da matrix
		String[] dimensao = line.split("\\s+");
		  int rows = Integer.parseInt(dimensao[0]);
	        int cols = Integer.parseInt(dimensao[1]);

	    	System.out.println(dimensao[0]);
	    	System.out.println(dimensao[1]);
	        
	                
	        numArray = new int[rows][cols];
	        
	        int row = 0;
	        
	        while ((line = bufferedReader.readLine()) != null && row < numArray.length) {
	            String[] tokens = line.split("\\s+");
	            
	            
	            for(int column = 0; column < tokens.length; column++) {
	               
	                    int value = Integer.parseInt(tokens[column]);
	                    numArray[row][column] = value; 
	            }
	            row++;
	        }            
	        printaMatrix(numArray);	
	        System.out.println();
	        umPraDois(numArray);
	        System.out.println();
	        zeroPraDois(numArray);
	        
		fileReader.close();
		
	} catch (IOException e) {}	
	}
	
	public static void printaMatrix(int[][] numArray){

	 for (int row = 0; row < numArray.length; row++) {
	        for (int column = 0; column < numArray[row].length; column++) {
	            System.out.print(numArray[row][column]);
	        }
	        System.out.println();
	 	}
	}
	
	public static void umPraDois(int[][] numArray){
	}
	
	public static void zeroPraDois(int[][] numArray){
	}
	
}
