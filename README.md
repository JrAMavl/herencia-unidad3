# herencia-unidad3
herencia-unidad3
public class Empleado {
    protected String nombre;
    protected double salario;

    public Empleado(String nombre, double salario) {
        this.nombre = nombre;
        this.salario = salario;
    }

    public void mostrarInformacion() {
        System.out.println("Empleado: " + nombre + ", Salario: $" + salario);
    }

    public double calcularBono() {
        return salario * 0.10;
    }
}
public class Gerente extends Empleado {
    private String departamento;

    public Gerente(String nombre, double salario, String departamento) {
        super(nombre, salario);
        this.departamento = departamento;
    }

    @Override
    public double calcularBono() {
        return salario * 0.20;
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Departamento: " + departamento);
    }
}


public class Vendedor extends Empleado {
    private int ventas;

    public Vendedor(String nombre, double salario, int ventas) {
        super(nombre, salario);
        this.ventas = ventas;
    }

    @Override
    public double calcularBono() {
        return salario * 0.10 + (ventas * 50);
    }
}

public class Main {
    public static void main(String[] args) {
        Gerente g1 = new Gerente("Ana", 20000, "Ventas");
        Vendedor v1 = new Vendedor("Luis", 10000, 15);

        g1.mostrarInformacion();
        System.out.println("Bono: $" + g1.calcularBono());
        System.out.println();

        v1.mostrarInformacion();
        System.out.println("Bono: $" + v1.calcularBono());
    }
}
