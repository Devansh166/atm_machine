import time
print('Please insert your ATM Card')
time.sleep(5)
pin = int(input('Enter your 4 digit ATM Pin'))
balance = 1000
if pin == 1234:
    while True:
        print("1 = Check Balance")
        print("2 = Withdraw Money")
        print("3 = Deposit Money")
        print("4 = Change pin")
        print("5 = Exit")
        try:
            option = int(input('Choose any option above'))
        except:
            print("Please choose the valid option")
        if  option == 1:
            print('----------------------------------')
            print(f'Your current balance is {balance}')
        if option == 2:
            withdraw_money = int(input('Enter the Withdraw Amount'))
            if withdraw_money < balance:
                balance = balance - withdraw_money
                print('----------------------------------')
                print(f'{withdraw_money} is debited from your account')
                print(f'Your current balance is {balance}')
            else:
                print('You do not have sufficient balance')
        if option == 3:
            deposit_money = int(input('Enter the deposit amount'))
            balance = balance + deposit_money
            print('----------------------------------')
            print(f'{deposit_money} is credited to your account')
            print(f'Your current balance is {balance}')
        if option == 4:
            new_pin = input("Enter new PIN: ")
            confirm_new_pin = input("Confirm new PIN: ")
            if new_pin == confirm_new_pin:
                result = (pin, new_pin)
                print('result confirm of change pin.')
            else:
                print("PINs do not match. Please try again.")
        if option == 5:
            print('Thank you for visiting our ATM Machine...See you Again')
            break

else:
    print('You entered the wrong pin...Try Again')
