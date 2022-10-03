import java.util.Scanner;
public class forca
{
    private static char nextGuess(Scanner in){
        char guess;
        String line;
        line = in.nextLine();
        guess = line.charAt(0);
        return guess;
    }
    
    private static void printHeader(){
        System.out.println("=============");
        System.out.println("JOGO DA FORCA");
        System.out.println("=============");
    }
    
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);        
        char guess;       // a letra que foi digitada
        String secret;    // a palavra que deve ser adivinhada
        String word;
        String wrongs; 
                
        printHeader();
        
        secret = "hangman";
        word = "_______";
        wrongs = "";
        
        System.out.printf("Palavra:    %s\n", word);
        System.out.print("Tentativa: ");
        guess = nextGuess(in);
        
        System.out.println(guess);
        
        if(secret.contains("" + guess)){
            System.out.printf("Tentadas: %s\n", wrongs);
        }
        else{
            wrongs = wrongs + guess + " ";
        }
        System.out.printf("Erradas:     %s\n", wrongs);
        
        
        in.close();
    }
}
