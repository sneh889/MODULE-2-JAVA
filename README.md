# MODULE-2-JAVA
import java.util.*;

class Professor {
    private String name;
    private String employeeId;
    private String specialization;

    Professor() {
    }

    Professor(String name, String employeeId, String specialization) {
        this.name = name;
        this.employeeId = employeeId;
        this.specialization = specialization;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmployeeId() {
        return employeeId;
    }

    public void setEmployeeId(String employeeId) {
        this.employeeId = employeeId;
    }

    public String getSpecialization() {
        return specialization;
    }

    public void setSpecialization(String specialization) {
        this.specialization = specialization;
    }

    public String toString() {
        return "Name: " + name + ", ID: " + employeeId +
               ", Specialization: " + specialization;
    }
}

class Department {
    private String deptName;
    private String hodName;
    private List<Professor> professors;

    Department() {
        professors = new ArrayList<>();
    }

    Department(String deptName, String hodName) {
        this.deptName = deptName;
        this.hodName = hodName;
        professors = new ArrayList<>();
    }

    public String getDeptName() {
        return deptName;
    }

    public void setDeptName(String deptName) {
        this.deptName = deptName;
    }

    public String getHodName() {
        return hodName;
    }

    public void setHodName(String hodName) {
        this.hodName = hodName;
    }

    public List<Professor> getProfessors() {
        return professors;
    }

    public void setProfessors(List<Professor> professors) {
        this.professors = professors;
    }

    public void addProfessor(Professor p) {
        professors.add(p);
    }

    public String toString() {
        String result = "Department: " + deptName + "\n";
        result += "HOD: " + hodName + "\n";
        result += "Professors:\n";

        for (Professor p : professors) {
            result += p + "\n";
        }

        return result;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] dept = sc.nextLine().split(",");
        Department d = new Department(dept[0], dept[1]);

        int n = Integer.parseInt(sc.nextLine());

        for (int i = 0; i < n; i++) {
            String[] p = sc.nextLine().split(",");
            Professor professor = new Professor(p[0], p[1], p[2]);
            d.addProfessor(professor);
        }

        System.out.print(d);
    }
}
