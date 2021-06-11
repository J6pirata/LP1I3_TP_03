# LP1I3_TP_003
import java.util.Scanner;

class Hora{
    private int hora;
    private int minuto;
    private int segundo;

    Scanner scanner = new Scanner(System.in);

    public Hora() {
        this.setHor();

        System.out.print("Digite o minuto: ");
        this.minuto = scanner.nextInt();

        System.out.print("Digite o segundo: ");
        this.segundo = scanner.nextInt();
    }

    public Hora(int hora, int minuto, int segundo){
        this.setHor(hora);
        this.minuto = minuto;
        this.segundo = segundo;
    }

    public int getHor(){
        return hora;
    }

    public void setHor(int hora){
        this.hora = hora;
    }

    public void setHor(){
        boolean fim = false;
        while(!fim) {
            try {
                System.out.print("Digite a hora: ");
                this.hora = Integer.parseInt(scanner.nextLine());
                if (this.hora < 0 || this.hora > 23) {
                    System.out.println("Digite novamente...");
                } else { 
                    fim = true; 
    
            } catch(Exception e){
                System.out.println("Digite novamente...");
            }
        }
    }

    public int getMinuto(){
        return minuto;
    }

    public void setMinuto(int minuto){
        this.minuto = minuto;
    }

      public int getSegundo(){
        return segundo;
    }

    public void setSegundo(int segundo){
        this.segundo = segundo;
    }

    public void getHora1() {
        System.out.println(this.getHor() + ":" + this.minuto + ":" + this.segundo);
    }

    public void getHora2() {
        int hora = this.getHor();
        if (hora > 12) {
            hora = hora - 12;
        }
        if (hora == 0) {
            hora = 12;
        }

        String am_pm = " PM";
        
        if (this.getHor() < 12) {
          String am_pm = " AM ";
        }

        System.out.println(hora + ":" + this.minuto + ":" + this.segundo + am_pm);
    }
}

public class Programa {
    public static void main(String args[]){
        Hora horas = new Hora();
        horas.getHora1();
        horas.getHora2();
        System.out.println((((horas.getHor() * 60) + horas.getMinuto()) * 60) + horas.getSegundo());
    }
}
