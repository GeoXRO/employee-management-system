import java.io.*;
import java.lang.reflect.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

class Angajat {
  //I. Define all the necessary fields here
  private final String cnp;
  private String nume;
  private final String prenume;
  private String email;
  private int salariu;
  private static String angajator;
  //II. Define all the necessary constructors and methods here
  public Angajat(String cnp, String nume, String prenume, String email) {
    this.cnp = cnp;
    this.nume = nume;
    this.prenume = prenume;
    this.email = email;
  }

  public Angajat(String cnp, String nume, String prenume, String email, int salariu) {
    this(cnp, nume, prenume, email);
    this.salariu = salariu;
  }

  public void maresteSalariu(int bonus) {
    //III.a. Enter your code here
    this.salariu += bonus;
    //You can also define any additional methods
  }
 
  public boolean valideazaCNP() {
    //III.b. Enter your code here
    return cnp.length() == 13 && cnp.matches("\\d+") && cnp.charAt(0) != '0' &&
    isValidMonth(cnp.substring(3, 5)) && isValidDay(cnp.substring(5, 7));
    //You can also define any additional methods
    
    //Remove the line below after you implement the method!
  }

  private boolean isValidMonth(String month) {
    int numericValue = Integer.parseInt(month);
    return numericValue >= 1 && numericValue <= 12;
  }

  private boolean isValidDay(String day) {
    int numericValue = Integer.parseInt(day);
    return numericValue >= 1 && numericValue <= 31;
  }
 
  public String toString() {
    //III.c. Enter your code here
    return "Angajatul " + nume + " " + prenume + ", CNP " + cnp +
    " are salariul de " + salariu + " RON/luna si lucreaza la " + angajator + "."; 
    //You can also define any additional methods
    
    //Remove the line below after you implement the method!
  }
  
  public int calculeazaBonusAnual() {
    //III.d. Enter your code here
    int cifra5 = numaraCifre(5, salariu);
    int cifra9 = numaraCifre(9, salariu);
    int bonus = 0;

    if (cifra5 > cifra9) {
      bonus = (int) Math.pow(10, cifra5);
    } else if (cifra9 > 0) {
        bonus = (int) Math.pow(10, 2 * cifra9);
    }

    //You can also define any additional methods
    
    //Remove the line below after you implement the method!
    return bonus;
  }

  private int numaraCifre(int cifra, int numar) {
    int count = 0;
    while (numar > 0) {
      if (numar % 10 == cifra) {
        count++;
      }
      numar /= 10;
    }
    return count;
  }

  public static String getAngajator() {
    return angajator;
  }

  public static void setAngajator(String angajator) {
    Angajat.angajator = angajator;
  }

  public String getNume() {
    return nume;
  }

  public void setNume(String nume) {
    this.nume = nume;
  }

  public String getPrenume() {
    return prenume;
  }

  public String getEmail() {
    return email;
  }

  public void setEmail(String email) {
    this.email = email;
  }

  public int getSalariu() {
    return salariu;
  }
  
  /*-----------------------------------------------------------
   * The methods below are used for Testing Purposes only.
   * Do not modify them.
   -----------------------------------------------------------*/
  protected void printObjectFields() {
    System.out.println("Employee " + this.nume + " " + this.prenume + ", CNP " 
           + this.cnp + ", current salary " + this.salariu
           + " lei/month and works at " + Angajat.angajator + ".");
  }

 
  public String getCnp() {
    return this.cnp;
  }
}
public class Main {
  
  public static void main(String[] args) {
    
    Scanner sc = new Scanner(System.in);
    int testNumber = sc.nextInt();
    sc.close();
    
    switch (testNumber) {
      case 0:
        // TEST 0 - Sanity check (no compilation / running errors in the system)
        System.out.println("Ok! Let's start!");
        break;
      case 1:
        // TEST 1 - Testing class Angajat constructors, getters & setters
        Angajat emp11 = new Angajat("1911221999999", "Pop", "Andreea", "an.d331.re@ge.com");
        Angajat emp12 = new Angajat("1810221943254", "Nascar", "Marius", "m.nascar21@outlk.com");
        
        System.out.println("Employee name: " + emp11.getNume() + " " + emp11.getPrenume());
        emp11.setNume("Popescu");
        System.out.println("Employee name updated to: " + emp11.getNume() + " " + emp11.getPrenume());
        
        System.out.println("Employee email: " + emp11.getEmail());
        emp11.setEmail("andreea.popescu@ggl.com");
        System.out.println("Employee email updated to: " + emp11.getEmail());
        
        emp11.setAngajator("Devmind");
        emp12.setAngajator("Devwork");
        System.out.println("Employees work for: " + emp11.getAngajator() + " and " + emp12.getAngajator());
        Angajat.getAngajator();
        
        emp11.printObjectFields();
        emp12.printObjectFields();
        
        try {
          Arrays.asList(Angajat.class.getDeclaredFields()).stream()
            .filter(f -> f.getName().equalsIgnoreCase("cnp"))
            .map(f -> Modifier.isFinal(f.getModifiers())).forEach(System.out::println);
        } catch (Exception e) {
          e.printStackTrace();
        }
        break;
      case 2:
        // TEST 2 - Testing method maresteSalariu(int)
        Angajat emp2 = new Angajat("1911221999999", "Diaconu", "Andrei", "diaconu.andr3@yay.com");
        emp2.setAngajator("{dev}mind");
        emp2.printObjectFields();
        emp2.maresteSalariu(20);
        emp2.printObjectFields();
        emp2.maresteSalariu(400);
        emp2.printObjectFields();
        break;
      case 3:
        // TEST 3 - Testing method valideazaCNP()
        Arrays.asList(
            new Angajat("191122199999", "A", "A", "a.a@yay.com"),
            new Angajat("191a122199999", "A", "A", "a.a@yay.com"),
            new Angajat("191122199999.", "A", "A", "a.a@yay.com"),
            new Angajat("0911221999999", "A", "A", "a.a@yay.com"),
            new Angajat("1911921999999", "A", "A", "a.a@yay.com"),
            new Angajat("1911233999999", "A", "A", "a.a@yay.com"),
            new Angajat("1910229999999", "A", "A", "a.a@yay.com"),
            new Angajat("1910101999999", "A", "A", "a.a@yay.com"),
            new Angajat("1910330999999", "A", "A", "a.a@yay.com")).stream()
          .map(a -> a.getCnp() + "\t-> " + a.valideazaCNP()).forEach(System.out::println);
        break;
      case 4:
        // TEST 4 - Testing method toString()
        Angajat emp4 = new Angajat("2880722497039", "Pop", "Daniela", "daniela.pop@devwork.com");
        emp4.setAngajator("DardrusEV");
        emp4.maresteSalariu(2500);
        System.out.println(emp4.toString());
        break;
      case 5:
        // TEST 5 - Testing method calculeazaBonusAnual()
        Angajat emp5 = new Angajat("2880722497039", "Rinor", "Anca", "anca.rinor@devwork.com");
        emp5.maresteSalariu(59405);
        emp5.printObjectFields();
        System.out.println(emp5.getPrenume() + "primeste un bonus anual de: " + emp5.calculeazaBonusAnual());
        emp5.maresteSalariu(40498);
        emp5.printObjectFields();
        System.out.println(emp5.getPrenume() + " primeste un bonus anual de: " + emp5.calculeazaBonusAnual());
        break;
      default:
        System.err.println("No such test case. Number: " + testNumber);
    }
  }
}
