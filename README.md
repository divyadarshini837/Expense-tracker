# Expense-tracker
The primary goal of the project is to provide users with insights into their spending habits, enabling them to make informed financial decisions. My project helps users to check their expense.
import pandas as pd

# Initialize an empty DataFrame to store expenses
expenses = pd.DataFrame(columns=['Description', 'Amount'])

def add_expense(description, amount):
    global expenses
    # Append the new expense directly to the DataFrame
    expenses.loc[len(expenses)] = [description, amount]
    print(f"Added expense: {description}, Amount: ${amount:.2f}")

def view_expenses():
    if expenses.empty:
        print("No expenses recorded.")
    else:
        print("\nExpenses:")
        print(expenses)

def total_expenses():
    total = expenses['Amount'].sum()
    print(f"\nTotal Expenses: ${total:.2f}")

def main():
    while True:
        print("\nExpense Tracker")
        print("1. Add Expense")
        print("2. View Expenses")
        print("3. Total Expenses")
        print("4. Exit")

        choice = input("Choose an option: ")

        if choice == '1':
            description = input("Enter expense description: ")
            amount = float(input("Enter expense amount: "))
            add_expense(description, amount)
        elif choice == '2':
            view_expenses()
        elif choice == '3':
            total_expenses()
        elif choice == '4':
            print("Exiting the Expense Tracker.")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
