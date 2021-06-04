import java.util.Scanner;

public class Avaliacao7 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Digite o número 1: ");
        int numero1 = Integer.parseInt(scanner.nextLine()); // ao ler do teclado, utilize somente o método nextLine()

        System.out.print("Digite o número 2: ");
        int numero2 = Integer.parseInt(scanner.nextLine()); // ao ler do teclado, utilize somente o método nextLine()

        System.out.print("Os números pares entre " + numero1 + " e " + numero2 + " são:");
        for (int numero = numero1; numero <= numero2; numero++) {
            if (numero % 2 == 0) {
                System.out.print(" " + numero);
            }
        }
        scanner.close();
    }
}
Exemplo de saída do programa:

Digite o número 1: 5
Digite o número 2: 39
Os números pares entre 5 e 39 são: 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38
2



hugokotsubo
Set '20
Complementando a resposta do @staroski acima, você não precisa fazer o for de 1 em 1 e testar todos os números para saber se são pares.

Basta testar se o primeiro número é par ou ímpar. Se ele for ímpar, some 1, assim você tem certeza que começa de um número par, e aí basta iterar de 2 em 2. Assim:

Scanner scanner = new Scanner(System.in);
System.out.print("Digite o número inicial: ");
int inicio = Integer.parseInt(scanner.nextLine());
System.out.print("Digite o número final: ");
int fim = Integer.parseInt(scanner.nextLine());

System.out.printf("Os números pares entre %d e %d são:", inicio, fim);
if (inicio % 2 != 0) { // se o número inicial é ímpar, adiciona 1
    inicio++; // assim, ele passa a ser par
}

// como agora eu sei que o início é par, posso iterar de 2 em 2, para ter somente números pares
for (int numero = inicio; numero <= fim; numero += 2) { // itero de 2 em 2
    System.out.printf(" %d", numero);
}
Já o número final não precisa fazer isso, pois o for irá parar corretamente, independente dele ser par ou ímpar.

Outro detalhe é que não precisa fechar o System.in (outros recursos são importantes de serem fechados, mas o System.in é “especial” e não precisa - veja aqui 2 para mais detalhes).
