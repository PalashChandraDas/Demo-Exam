1. Construct a system that evaluates the current temperature and displays a message based on
 defined ranges. If the temperature is 20°C or below, it shows "It's cold. Wear a jacket." For
 temperatures between 21°C and 30°C, it displays "The weather is pleasant." If the
 temperature is between 31°C and 40°C, it outputs "It's getting hot. Stay hydrated." For
 temperatures above 40°C, the system shows "Heat alert! Avoid going outside."
-----------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the temperature in °C: ");
        string input = Console.ReadLine();

        // Try to convert input to an integer
        if (int.TryParse(input, out int temperature))
        {
            if (temperature <= 20)
            {
                Console.WriteLine("It's cold. Wear a jacket.");
            }
            else if (temperature <= 30)
            {
                Console.WriteLine("The weather is pleasant.");
            }
            else if (temperature <= 40)
            {
                Console.WriteLine("It's getting hot. Stay hydrated.");
            }
            else
            {
                Console.WriteLine("Heat alert! Avoid going outside.");
            }
        }
        else
        {
            Console.WriteLine("Invalid input. Please enter a number.");
        }
    }
}




 2. Construct a system that evaluates a driver's speed and shows a message based on how much
 it exceeds the 60 km/h speed limit. If the speed is 60 or below, the message is "You are
 within the speed limit." For speeds between 61 and 70 km/h, it shows "Warning: Slightly
 over the speed limit." If the speed falls between 71 and 90 km/h, the system outputs "Fine:
 Moderate speeding." For any speed above 90 km/h, it shows "Heavy fine: Excessive
 speeding!".
--------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the speed of the vehicle (km/h): ");
        int speed = int.Parse(Console.ReadLine());

        if (speed <= 60)
        {
            Console.WriteLine("You are within the speed limit.");
        }
        else if (speed <= 70)
        {
            Console.WriteLine("Warning: Slightly over the speed limit.");
        }
        else if (speed <= 90)
        {
            Console.WriteLine("Fine: Moderate speeding.");
        }
        else
        {
            Console.WriteLine("Heavy fine: Excessive speeding!");
        }
    }
}




 3. Design a system that checks the current temperature and responds with an appropriate
 message based on specific temperature ranges. When the temperature is 20°C or lower, it
 displays "It's cold. Wear a jacket." If the temperature is between 21°C and 30°C, the system
 responds with "The weather is pleasant." For temperatures ranging from 31°C to 40°C, it
 shows "It's getting hot. Stay hydrated." If the temperature exceeds 40°C, it warns with the
 message "Heat alert! Avoid going outside."
------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the current temperature (°C): ");
        int temperature = int.Parse(Console.ReadLine());

        if (temperature <= 20)
        {
            Console.WriteLine("It's cold. Wear a jacket.");
        }
        else if (temperature <= 30)
        {
            Console.WriteLine("The weather is pleasant.");
        }
        else if (temperature <= 40)
        {
            Console.WriteLine("It's getting hot. Stay hydrated.");
        }
        else
        {
            Console.WriteLine("Heat alert! Avoid going outside.");
        }
    }
}




4. Construct a system that uses the ternary operator to categorize the temperature into four
 categories: "Freezing" if the temperature is below 0°C, "Cold" if the temperature is between
 0°C and 15°C, "Warm" if the temperature is between 16°C and 30°C, and "Hot" if the
 temperature is above 30°C.
------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter the temperature (°C): ");
        int temp = int.Parse(Console.ReadLine());

        string category = temp < 0 ? "Freezing" :
                          temp <= 15 ? "Cold" :
                          temp <= 30 ? "Warm" :
                          "Hot";

        Console.WriteLine("Temperature category: " + category);
    }
}




5. Construct a system that uses the ternary operator to categorize a person based on age into
 four groups. If the age is below 13, the person is classified as "Child"; if the age is between
 13 and 19, they are labeled "Teenager"; if the age is between 20 and 59, they are considered
 "Adult"; and if the age is 60 or above, they fall into the "Senior" category.
-------------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter age: ");
        int age = int.Parse(Console.ReadLine());

        string category = age < 13 ? "Child" :
                          age <= 19 ? "Teenager" :
                          age <= 59 ? "Adult" :
                          "Senior";

        Console.WriteLine("Age category: " + category);
    }
}




6. Construct a system that uses the ternary operator to evaluate a student's performance based
 on their marks. If the marks are below 40, the result is "Fail"; if the marks are between 40
 and 59, it shows "Pass"; if the marks are between 60 and 79, it displays "Merit"; and if the
 marks are 80 or above, it shows "Distinction".
-------------------

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter student's marks: ");
        int marks = int.Parse(Console.ReadLine());

        string result = marks < 40 ? "Fail" :
                        marks <= 59 ? "Pass" :
                        marks <= 79 ? "Merit" :
                        "Distinction";

        Console.WriteLine("Performance: " + result);
    }
}




 7. Evaluate the design and functionality of a movie ticket booking system that records details
 like movie name, seat number, and ticket price. The system enables users to input ticket
 data, calculate total costs for multiple tickets, and generate a booking summary. Justify that
 the object-oriented design approach effectively supports usability, performance, and
 scalability.
------------------

using System;
using System.Collections.Generic;

class Ticket
{
    public string MovieName { get; set; }
    public string SeatNumber { get; set; }
    public double TicketPrice { get; set; }

    public Ticket(string movieName, string seatNumber, double ticketPrice)
    {
        MovieName = movieName;
        SeatNumber = seatNumber;
        TicketPrice = ticketPrice;
    }

    public void Display()
    {
        Console.WriteLine($"Movie: {MovieName}, Seat: {SeatNumber}, Price: {TicketPrice:C}");
    }
}

class BookingSystem
{
    private List<Ticket> tickets = new List<Ticket>();

    public void AddTicket(Ticket ticket)
    {
        tickets.Add(ticket);
    }

    public double CalculateTotalCost()
    {
        double total = 0;
        foreach (var ticket in tickets)
        {
            total += ticket.TicketPrice;
        }
        return total;
    }

    public void ShowSummary()
    {
        Console.WriteLine("\n--- Booking Summary ---");
        foreach (var ticket in tickets)
        {
            ticket.Display();
        }
        Console.WriteLine($"Total Cost: {CalculateTotalCost():C}");
    }
}

class Program
{
    static void Main()
    {
        BookingSystem bookingSystem = new BookingSystem();

        Console.Write("How many tickets do you want to book? ");
        int count = int.Parse(Console.ReadLine());

        for (int i = 0; i < count; i++)
        {
            Console.WriteLine($"\nEnter details for ticket #{i + 1}:");
            Console.Write("Movie Name: ");
            string movie = Console.ReadLine();

            Console.Write("Seat Number: ");
            string seat = Console.ReadLine();

            Console.Write("Ticket Price: ");
            double price = double.Parse(Console.ReadLine());

            Ticket ticket = new Ticket(movie, seat, price);
            bookingSystem.AddTicket(ticket);
        }

        bookingSystem.ShowSummary();
    }
}




8. Evaluate the design and functionality of an online food ordering system that records details
 such as food item name, quantity, and item price. The system allows users to input order
 details, calculate the total bill for multiple items, and generate an order summary. Justify that
 using an object-oriented design approach enhances usability by organizing food items as
 objects, improves performance through efficient data handling, and supports scalability by
 allowing easy integration of new features like discounts, delivery tracking, or menu updates.
------------------

using System;
using System.Collections.Generic;

class FoodItem
{
    public string Name { get; set; }
    public int Quantity { get; set; }
    public double PricePerItem { get; set; }

    public FoodItem(string name, int quantity, double pricePerItem)
    {
        Name = name;
        Quantity = quantity;
        PricePerItem = pricePerItem;
    }

    public double GetTotalPrice()
    {
        return Quantity * PricePerItem;
    }

    public void Display()
    {
        Console.WriteLine($"Item: {Name}, Quantity: {Quantity}, Unit Price: {PricePerItem:C}, Total: {GetTotalPrice():C}");
    }
}

class OrderSystem
{
    private List<FoodItem> orderList = new List<FoodItem>();

    public void AddItem(FoodItem item)
    {
        orderList.Add(item);
    }

    public double CalculateTotalBill()
    {
        double total = 0;
        foreach (var item in orderList)
        {
            total += item.GetTotalPrice();
        }
        return total;
    }

    public void ShowOrderSummary()
    {
        Console.WriteLine("\n--- Order Summary ---");
        foreach (var item in orderList)
        {
            item.Display();
        }
        Console.WriteLine($"Total Bill: {CalculateTotalBill():C}");
    }
}

class Program
{
    static void Main()
    {
        OrderSystem order = new OrderSystem();

        Console.Write("How many food items do you want to order? ");
        int itemCount = int.Parse(Console.ReadLine());

        for (int i = 0; i < itemCount; i++)
        {
            Console.WriteLine($"\nEnter details for item #{i + 1}:");
            Console.Write("Food Name: ");
            string name = Console.ReadLine();

            Console.Write("Quantity: ");
            int quantity = int.Parse(Console.ReadLine());

            Console.Write("Price per item: ");
            double price = double.Parse(Console.ReadLine());

            FoodItem foodItem = new FoodItem(name, quantity, price);
            order.AddItem(foodItem);
        }

        order.ShowOrderSummary();
    }
}




9. Evaluate the design and functionality of a library management system that records details
 such as book title, author, borrower name, and due date. The system allows users to input
 book lending data, track borrowed books, calculate overdue fines, and generate lending
 summaries. Justify that the object-oriented design approach supports usability by
 encapsulating book and borrower details, enhances performance by streamlining data access
 and updates, and ensures scalability for adding new features like digital book access,
 member categories, or automated notifications.
-----------------

using System;
using System.Collections.Generic;

class FoodItem
{
    public string Name { get; set; }
    public int Quantity { get; set; }
    public double PricePerItem { get; set; }

    public FoodItem(string name, int quantity, double pricePerItem)
    {
        Name = name;
        Quantity = quantity;
        PricePerItem = pricePerItem;
    }

    public double GetTotalPrice()
    {
        return Quantity * PricePerItem;
    }

    public void Display()
    {
        Console.WriteLine($"Item: {Name}, Quantity: {Quantity}, Unit Price: {PricePerItem:C}, Total: {GetTotalPrice():C}");
    }
}

class OrderSystem
{
    private List<FoodItem> orderList = new List<FoodItem>();

    public void AddItem(FoodItem item)
    {
        orderList.Add(item);
    }

    public double CalculateTotalBill()
    {
        double total = 0;
        foreach (var item in orderList)
        {
            total += item.GetTotalPrice();
        }
        return total;
    }

    public void ShowOrderSummary()
    {
        Console.WriteLine("\n--- Order Summary ---");
        foreach (var item in orderList)
        {
            item.Display();
        }
        Console.WriteLine($"Total Bill: {CalculateTotalBill():C}");
    }
}

class Program
{
    static void Main()
    {
        OrderSystem order = new OrderSystem();

        Console.Write("How many food items do you want to order? ");
        int itemCount = int.Parse(Console.ReadLine());

        for (int i = 0; i < itemCount; i++)
        {
            Console.WriteLine($"\nEnter details for item #{i + 1}:");
            Console.Write("Food Name: ");
            string name = Console.ReadLine();

            Console.Write("Quantity: ");
            int quantity = int.Parse(Console.ReadLine());

            Console.Write("Price per item: ");
            double price = double.Parse(Console.ReadLine());

            FoodItem foodItem = new FoodItem(name, quantity, price);
            order.AddItem(foodItem);
        }

        order.ShowOrderSummary();
    }
}

