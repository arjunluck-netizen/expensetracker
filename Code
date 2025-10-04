file_name = "expense.txt"
cap_limit = 1000
def write_file(details):
  a = open(file_name, "w")
  a.write(details)
  a.close()
def view_expenses():
  a = open(file_name, "r")
  a = a.read()
  print(a)
  if a:
    a = eval(a)
    print("read", a)
    return a
def check_budget():
    total_amt = 0
    expense = view_expenses()
    for exp in expense:
        amt= exp.get('amount')
        total_amt = int(total_amt) + int(amt)
    print("your total amount is ", total_amt)
    if total_amt < cap_limit:
        print("You are in safe Zone")
    else:
        print("You have exceeded your budget!")
def save_budget():
    data = view_expenses()
    import pandas as pd
    df = pd.DataFrame(data)
    df.to_csv('output.csv', index = False)
def add_expense():
    date = input("Enter Date")
    cat = input("Enter category")
    amt = input("Enter amount")
    expense_list = view_expenses()
    print("view", expense_list)
    if not expense_list:
         expense_list = []
    expense_list.append({'date':date, 'category':cat, 'amount':amt})
    print("expense_list", expense_list)
    write_file(str(expense_list))
def main():
    print("1: add Expense")
    print("2: view Expenses")
    print("3: check Budget")
    print("4: save Budget")
    print("5: exit")
    inp = 0
    while inp != 5:  # Loop until user enters 5
            inp = int(input("Enter option: "))
            if inp == 1:
                add_expense()
            elif inp == 2:
                view_expenses()
            elif inp == 3:
                check_budget()
            elif inp == 4:
                save_budget()
            elif inp == 5:
                print("Exiting...")
            else:
                print("Invalid option. Please enter a number from 1 to 5.")
# To run the program, you would call main() once, outside the function.
if __name__ == "__main__":
    main()
