
		     // get the user inputs until all are valid.
    // The username should only be output once
    Console.Write("Enter first name: ");
    firstName = Console.ReadLine();
    Console.Write("Enter last name: ");
    lastName = Console.ReadLine();
    Console.Write("Enter age: ");
    age = Convert.ToInt32(Console.ReadLine());
    Console.Write("Enter Password: ");
    password = Console.ReadLine();
    Console.Write("Enter email address: ");
    emailAddress = Console.ReadLine();


    //username = createUserName(firstName, lastName, age);
    //Console.WriteLine($"Username is {username}, you have successfully registered please remember your password");

    //  Test your program with a range of tests to show all validation works
    // Show your evidence in the Readme

}
static bool ValidName(string name)
{
    // name must be at least two characters and contain only letter
    int namelenght = name.Length;
    for (int i = 0; i < namelenght; i++)
    {
        int assicvalue = Convert.ToInt32(name[i]);
        if (assicvalue < 65 || assicvalue > 60 && assicvalue < 97 || assicvalue > 122)
        {
            if (namelenght < 2)
            {
                return false;
            }
        }

        

    }
    return true;
}

static bool validAge(int age)
{
    //age must be between 11 and 18 inclusive
    if (age >= 11 && age <= 18)
    {
        return true;
    }
    return false;

}


static bool ValidPassword(string password)
{
    // Check password is at least 8 characters in length
    if (password.Length < 8)
    {
        return false;
    }


    // Check password contains a mix of lower case, upper case and non letter characters
    // QWErty%^& = valid
    // QWERTYUi = not valid
    // ab£$%^&* = not valid
    // QWERTYu! = valid
    bool hasUpper = false;
    bool hasLower = false;
    bool hasspecial = false;
    for (int i = 0; i < password.Length; i++)
    {
        if (password[i] < 65 || password[i] > 90 && password[i] < 97 || password[i] > 122)
        {
            hasspecial |= true;
        }
        if (password[i] > 64 && password[i] > 91)
        {
            hasUpper = true;
        }
        if (password[i] > 96 && password[i] < 123)
        {
            hasLower = true;
        }
    }
    if (hasUpper == false && hasLower == false && hasspecial == false)
    {
        return false;
    }

    // Check password contains no runs of more than 2 consecutive or repeating letters or numbers
    // AAbbdd!2 = valid (only 2 consecutive letters A and B and only 2 repeating of each)
    // abC461*+ = not valid (abC are 3 consecutive letters)
    // 987poiq! = not valid (987 are consecutive)
    for (int i = 0; i < password.Length - 2; i++)
    {

        if (password[i] == password[i + 1] && password[i] == password[i + 2])
        {
            return false;
        }
    }
    return true;
    static bool validEmail(string email)
    {
        // a valid email address
        // has at least 2 characters followed by an @ symbol
        // has at least 2 characters followed by a .
        // has at least 2 characters after the .
        // contains only one @ and any number of .
        // does not contain any other non letter or number characters
        int atCount = 0;
       int atposition = 0 ;
        int dotposition = 0 ;
        int dotcount = 0; 
        int afterAt = 0 ;
        int afterDot = 0 ;
        for (int i = 0; i == email.Length; i++)
        {
            int assciValue = Convert.ToInt32(email[i]);
            if (assciValue == 40)
            {
                atCount++;
                
            }
            while (atCount < 0)
            {
                atposition++;
            }
            if ( assciValue == 46)
            {
                 dotcount = 1;
            }
            while (dotcount < 1)
            {
                dotposition++;
            }
            afterAt = atposition - email.Length;
            afterDot = dotposition - email.Length;
            if (assciValue > 65 && assciValue < 90 && atCount == 1 && afterAt > 2  & afterDot >= 2|| assciValue > 97 && assciValue < 122 && atCount == 1 && afterAt > 2 & afterDot >= 2)
            {

                return true;
            }

           

        }
        return false;
       
    }
    static string createUserName(string firstName, string lastName, int age)
    {
        // username is made up from:
        // first two characters of first name
        // last two characters of last name
        // age
        //e.g. Bob Smith aged 34 would have the username Both34
        int firstNameLength = firstName.Length;
        int lastNameLength = lastName.Length;
        string firstPart = firstName.Length >= 2 ? firstName.Substring(0, 2) : firstName;
        string lastPart = lastName.Length >= 2 ? lastName.Substring(lastName.Length - 2) : lastName;
        string username = firstPart + lastPart + Convert.ToString(age);
        return username;

	}
} 

code all here due to not commiting from my laptop 

![image](https://github.com/user-attachments/assets/44080e2d-5518-4edd-84c6-6acacd20527f)

error here that wont let me run the code so cant get a screen clipping 
