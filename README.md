## Python Tips


 ### Encapsulation
```arm
class BankAccount:
    def __init__(self, account_holder, balance):
        self.account_holder = account_holder      # Public attribute
        self.__balance = balance                  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"Deposited ${amount}. New balance: ${self.__balance}")
        else:
            print("Deposit amount must be positive.")

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrew ${amount}. Remaining balance: ${self.__balance}")
        else:
            print("Insufficient funds or invalid amount.")

    def get_balance(self):
        return self.__balance
```
### Output
```arm
account = BankAccount("Alice", 1000)

account.deposit(200)         # Deposited $200. New balance: $1200
account.withdraw(500)        # Withdrew $500. Remaining balance: $700

print(account.get_balance()) # 700

# Trying to access private attribute directly:
print(account.__balance)     # AttributeError: 'BankAccount' object has no attribute '__balance'
```
