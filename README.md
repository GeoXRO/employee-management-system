# employee-management-system
-Creating a Structured Employee Class: The Angajat class defines essential fields and methods for an employee (e.g., cnp, nume, prenume, email, salariu, and a static angajator). This structure organizes key employee attributes and actions, which helps me understand how to build reusable, organized object-oriented structures.

-Constructors for Flexibility: The class has two constructors for creating Angajat instances with or without the salariu field. This demonstrates constructor overloading, where multiple constructors handle different levels of detail for initializing objects, offering flexibility when creating instances.

-Implementing Salary Adjustments: The maresteSalariu(int bonus) method allows for salary adjustments by adding a bonus to the salariu field. This shows me how simple methods can update an object’s internal state in response to external factors, making the class adaptable to changes.

-Validating Employee ID (CNP): The valideazaCNP method performs checks to ensure a valid CNP, like confirming its length and that it only contains digits, and validates specific parts like the month and day. The helper methods isValidMonth and isValidDay break down validation, making code more modular. This teaches me to structure validation logic clearly, separating smaller tasks for maintainability.

-Dynamic Data Representation with toString: The toString method returns a formatted string with details about the employee, such as their name, CNP, salary, and employer. This overrides the default toString behavior to provide a meaningful and easy-to-read description of the object. I see how defining this method customizes output, which can be useful for displaying object data in logs or interfaces.

-Calculating Annual Bonuses: The calculeazaBonusAnual method calculates a bonus based on specific digits in the salary. By counting instances of specific digits (e.g., 5 and 9) and applying a formula based on the count, this method uses helper methods (like numaraCifre) to isolate functionality, demonstrating how to implement complex logic in a readable, reusable way.

-Static Fields and Methods for Shared Data: The static angajator field and associated getAngajator and setAngajator methods manage data that applies to all instances of the class, not just one instance. This illustrates how static fields and methods can centralize information that’s constant across all instances.

-Testing with the Main Class: The Main class allows testing of various features, such as creating employees, updating fields, validating CNPs, and calculating bonuses, using different test cases in a switch statement. This setup shows me how testing specific cases can validate each method’s functionality, helping ensure that code behaves as expected.

Overall, this code teaches me how to design a class with fields, constructors, and methods that represent and manipulate employee data while adding flexible, structured functionality. It combines object-oriented principles with practical applications, making it a solid example of a class that could be used in a business application.
