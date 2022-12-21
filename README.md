# CRUD-Operations

import java.util.*;

class Employee {

    private String name;
    private String gender;
    private long dob;
    private String email;
    private long phone;

    Employee(String name, String gender, long dob, String email, long phone) {
        this.name = name;
        this.gender = gender;
        this.dob = dob;
        this.email = email;
        this.phone = phone;
    }

    public String getEmpName() {
        return name;
    }

    public String getGender() {
        return gender;
    }

    public long getDOB() {
        return dob;
    }

    public String getEmail() {
        return email;
    }

    public long getPhone() {
        return phone;
    }

    public String toString() {
        return name + " " + gender + " " + dob + " " + email + " " + phone;
    }
}

class CRUDoperations {
    public static void main(String[] args) {

    List<Employee> E = new ArrayList<Employee>();
        Scanner sc = new Scanner(System.in);
        Scanner sc1 = new Scanner(System.in);
        int ch;
        do {
            System.out.println("1.INSERT");
            System.out.println("2.DISPLAY");
            System.out.println("3.UPDATE");
            System.out.println("4.DELETE");
            System.out.println("5.EXIT");
            System.out.println("Enter Your Choice : ");
            ch = sc.nextInt();
            switch (ch) {
                case 1:
                    System.out.print("Enter Name: ");
                    String name = sc1.nextLine();
                    System.out.print("Enter Gender: ");
                    String gender = sc1.nextLine();
                    System.out.print("Enter DOB: ");
                    long dob = sc.nextInt();
                    System.out.print("Enter Email: ");
                    String email = sc1.nextLine();
                    System.out.print("Enter Phone: ");
                    long phone = sc.nextInt();

                    E.add(new Employee(name, gender, dob, email, phone));
                    break;

                case 2:
                    System.out.println("-------------------------------------------");
                    Iterator<Employee> i = E.iterator();
                    while (i.hasNext()) {
                        Employee e = i.next();
                        System.out.println(e);
                    }
                    System.out.println("-------------------------------------------");
                    break;
                case 3:
                    boolean found = false;
                    System.out.println("Enter Name to Update: ");
                    name = sc1.nextLine();
                    System.out.println("Enter Gender to Update: ");
                    gender = sc1.nextLine();
                    System.out.println("Enter DOB to Update: ");
                    dob = sc.nextInt();
                    System.out.println("Enter Email to Update: ");
                    email = sc1.nextLine();
                    System.out.println("Enter Phone to Update: ");
                    phone = sc.nextInt();
                    System.out.println("-------------------------------------------");
                    ListIterator<Employee> li = E.listIterator();
                    while (li.hasNext()) {
                        Employee e = li.next();
                        if (e.getEmpName() == name) {
                            System.out.println("Enter New Name: ");
                            name = sc1.nextLine();

                            System.out.println("Enter New Gender: ");
                            gender = sc1.nextLine();

                            System.out.println("Enter New DOB: ");
                            dob = sc.nextInt();

                            System.out.println("Enter New Email: ");
                            email = sc1.nextLine();

                            System.out.println("Enter New Phone: ");
                            phone = sc.nextInt();

                            li.set(new Employee(name, gender, dob, email, phone));
                            found = true;
                        }
                    }
                    if (!found) {
                        System.out.println("Record Not Found");
                    } else {
                        System.out.println("Record is Updaed Successfully...!");
                    }
                    System.out.println("-------------------------------------------");
                    break;
                case 4:
                    found = false;
                    System.out.println("Enter Name to Delete: ");
                    name = sc1.nextLine();
                    System.out.println("Enter Gender to Delete: ");
                    gender = sc1.nextLine();
                    System.out.println("Enter DOB to Delete: ");
                    dob = sc1.nextInt();
                    System.out.println("Enter Email to Delete: ");
                    email = sc1.nextLine();
                    System.out.println("Enter Phone to Delete: ");
                    phone = sc.nextInt();

                    System.out.println("-------------------------------------------");
                    i = E.iterator();
                    while (i.hasNext()) {
                        Employee e = i.next();
                        if (e.getEmpName() == name) {
                            i.remove();
                            found = true;
                        }
                    }
                    if (!found) {
                        System.out.println("Record Not Found");
                    } else {
                        System.out.println("Record is Deleted Successfully...!");
                    }
                    System.out.println("-------------------------------------------");
                    break;
                    case 5: 
                    System.out.println("Exit");
                    return;
            }
        } while (ch != 0);
    }

}
