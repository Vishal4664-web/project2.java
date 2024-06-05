import java.util.Scanner;

class Employee {
    private String name;
    private double hourlyRate;
    private int hoursWorked;

    public Employee(String name, double hourlyRate) {
        this.name = name;
        this.hourlyRate = hourlyRate;
        this.hoursWorked = 0;
    }

    public String getName() {
        return name;
    }

    public double getHourlyRate() {
        return hourlyRate;
    }

    public int getHoursWorked() {
        return hoursWorked;
    }

    public void addHours(int hours) {
        hoursWorked += hours;
    }

    public double calculatePay() {
        return hourlyRate * hoursWorked;
    }
}

public class PayrollManagementSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter employee name: ");
        String name = scanner.nextLine();

        System.out.print("Enter hourly rate: ");
        double hourlyRate = scanner.nextDouble();

        Employee employee = new Employee(name, hourlyRate);

        System.out.print("Enter hours worked: ");
        int hoursWorked = scanner.nextInt();
        employee.addHours(hoursWorked);

        double totalPay = employee.calculatePay();
        System.out.println("Total pay for " + employee.getName() + " is $" + totalPay);

        scanner.close();
    }
}

