expenses = []

while True:
    print("\n===== STUDENT EXPENSE TRACKER =====")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Show Total Expense")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        category = input("Enter category: ")
        amount = float(input("Enter amount: "))

        expenses.append({
            "category": category,
            "amount": amount
        })

        print("Expense added successfully!")

    elif choice == "2":
        if not expenses:
            print("No expenses found.")
        else:
            print("\n--- Your Expenses ---")
            for i, expense in enumerate(expenses, 1):
                print(f"{i}. {expense['category']} - ₹{expense['amount']}")

    elif choice == "3":
        total = sum(expense["amount"] for expense in expenses)
        print(f"Total Expense: ₹{total:.2f}")

    elif choice == "4":
        print("Thank you for using Expense Tracker!")
        break

    else:
        print("Invalid choice. Try again.")
