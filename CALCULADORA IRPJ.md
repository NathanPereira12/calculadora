import java.util.Scanner;

public class CalculadoraImpostoRenda {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Digite a receita bruta anual da empresa: ");
        double receitaBruta = scanner.nextDouble();

        System.out.print("Digite o total de despesas dedutíveis anuais da empresa: ");
        double despesasDedutiveis = scanner.nextDouble();

        double lucroReal = calcularLucroReal(receitaBruta, despesasDedutiveis);
        double irpj = calcularIRPJ(lucroReal);
        double csll = calcularCSLL(lucroReal);

        System.out.println("Lucro Real: " + lucroReal);
        System.out.println("IRPJ devido: " + irpj);
        System.out.println("CSLL devida: " + csll);

        scanner.close();
    }

    public static double calcularLucroReal(double receitaBruta, double despesasDedutiveis) {
        return receitaBruta - despesasDedutiveis;
    }

    public static double calcularIRPJ(double lucroReal) {
        return lucroReal * 0.15;
    }

    public static double calcularCSLL(double lucroReal) {
        return lucroReal * 0.09;
    }
}
