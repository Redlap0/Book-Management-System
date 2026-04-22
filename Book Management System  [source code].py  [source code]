inventoryarc = {}
salesrep = []


def AddBook():
    refnum = input("Enter ISBN code (eg:978-0441172719): ")
    Name = input("Enter book name: ")
    Author = input(f"Who is the author of {Name}: ")

    
    try:
        Price = float(input("Enter price of the book: "))
        Netquan = int(input("Enter quantity of book: "))
    except ValueError:
        print("Invalid input! Price and quantity must be numbers.")
        return

    print(f"{Netquan}, books of  {Name} added for the affordable price of {Price} ₹ each")
    inventoryarc[refnum] = {
        "name": Name,
        "author": Author,
        "price": Price,
        "quantity": Netquan
    }
    print(f"{Name} has been stored in inventory")


def DelBook():
    ref = input("Please enter the reference number of book to be deleted: ")
    if ref in inventoryarc:
        del inventoryarc[ref]
        print("Desired book is deleted")
    else:
        
        print("Book not found!")


def Viewinventory():
    if not inventoryarc:
        print("You have no books, add some to the inventory")
        return

    print("Name | Author | Price | Quantity | ISBN")
    print("-" * 50)  
    for refnum, book in inventoryarc.items():
        print(
            f"{book['name']} | {book['author']} | ₹{book['price']} | {book['quantity']} | {refnum}")


def SellBook():
    soldref = input("Enter ISBN code of the book to be sold: ")
    if soldref in inventoryarc:
        books = inventoryarc[soldref]

        
        if books['quantity'] > 0:
            books['quantity'] -= 1
            salesrep.append(books['price'])
            print(f"Book sold and earned {books['price']} ₹")

            if books['quantity'] == 0:
                print("Book is now out of stock.")
                del inventoryarc[soldref]
        else:
            print("Out of stock!")
    else:
        
        print("Book not found!")


def SalesRep():
    print("you have earned a grand total of:")
    print(f"{sum(salesrep)} ₹")


def menuu():
    print("    ")
    print("""============BOOK STORE MANAGEMENT SYSTEM===========
===================================================
 What do you want to manage today?""")
    print("  ")
    print(""" 1. Add Book
 2. Delete Book
 3. Inventory
 4. Sell Book
 5. Sales
 6. Exit   
===================================================
""")


while True:
    menuu()

    
    try:
        option = int(input("Choose your management option: "))
    except ValueError:
        print("Please enter a valid number.")
        continue

    if option == 1:
        AddBook()
    elif option == 2:
        DelBook()
    elif option == 3:
        Viewinventory()
    elif option == 4:
        SellBook()
    elif option == 5:
        SalesRep()
    elif option == 6:
        break
    else:
        print("please choose a given option up above.")
