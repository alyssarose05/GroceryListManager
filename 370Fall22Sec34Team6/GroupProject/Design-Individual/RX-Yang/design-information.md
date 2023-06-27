## Assignment 5 *GroceryListManager*

#### Rongxin Yang

1. **A grocery list consists of items the users want to buy at a grocery store. The application must allow users to add items to a list, delete items from a list, and change the quantity of items in the list (e.g., change from one to two pounds of apples).** 

   I have a class **User** with **username**, **phone**, and **email** attributes so that these information can connect users with our application. In order to let users to manage items such as add item, delete item, and change item quantity, I have a class **GroceryList** which has methods, such as **add_item()**, **delete_item()**, **set_quantity()**, to manage items. There is a default list, so **GroceryList** starts from 1. 



2. **The application must contain a database (DB) of items and corresponding item types.**

   I added to the design a class **Database** with attributes **item** and **item_type**. Class **Database** can get item and the corresponding item type from database, and it can add a item with its name and type. Between class **Database** and class **Item**, I use composition relationship because item is a part of DB and if DB is destroyed, items will not exist.

 

3. **Users must be able to add items to a list by picking them from a hierarchical list, where the first level is the item type (e.g., cereal), and the second level is the name of the actual item (e.g., shredded wheat). After adding an item, users must be able to specify a quantity for that item.** 

   In order to pick items from a hierarchical list, I create class **ItemType** as first level and class **Item** as second level with inheritance relationship. Between class **ItemType** and class **Database**, they are composition relationship because item type is a part of DB and if DB is destroyed, items type will not exist. Users search items begin with item type by association relationship, which users and item types both are 0 or more, then search actual items and add items to list if users want by method **add_to_list()** when the attribute **isAdd** is true. Inside of method **add_to_list()** has method **set_quantity()** so that users can be able to specify a quantity for that item after add the item. Between class **GroceryList** and class **Item**, I use dependence and aggregation relationship since **items** attribute uses class **Item** as an Object type in class **GroceryList**, and item is a part of list.



4. **Users must also be able to specify an item by typing its name. In this case, the application must look in its DB for items with similar names and ask the users, for each of them, whether that is the item they intended to add. If a match cannot be found, the application must ask the user to select a type for the item and then save the new item, together with its type, in its DB.** 

   There is a association relationship from class **User** to class **Database** because users search an item by name from the DB. Then rest conditions can use **if else** statement of method **search_name()** to determine to add or not. If cannot be found, to call **add_item_db(item: String, item_type: String)** method to add new item and its type into DB.

 

5. **Lists must be saved automatically and immediately after they are modified.**

   I add method **save()** in class **GroceryList** so that it can be called in other methods in this class and then list can be saved automatically and immediately.

 

6. **Users must be able to check off items in a list (without deleting them).**

   To achieve this, I add a method **check_off()** in class **User**, and add the association relationship between class **User** and class **GroceryList** with an association class **CheckOff**. 

 

7. **Users must also be able to clear all the check-off marks in a list at once.**

   I add method **clear_checkOff()** in class **GroceryList**.

 

8. **Check-off marks for a list are persistent and must also be saved immediately.**

   I add method **save()** in class **CheckOff** to save check-off marks immediately.

 

9. **The application must present the items in a list grouped by type, so as to allow users to shop for a specific type of product at once (i.e., without having to go back and forth between aisles).** 

   I use method **group_by_type()** in class **GroceryList** to group same type item together. This method can be called in method **show_item()** which can show all items in the list.

 

10. **The application must support multiple lists at a time (e.g., “weekly grocery list”, “monthly farmer’s market list”). Therefore, the application must provide the users with the ability to create, (re)name, select, and delete lists.** 

    In order to show multiple lists, I use class **ListManager** to manage the multiple lists. No matter users do what to list, they must select a list or create a list first. Therefore I add association relationship between class **ListManager** and class **User** so that users can manage lists. Between class **ListManager** and class **GroceryList**, there are composition and dependence relationship. One list manager can manage one or more lists and if class **ListManager** disappears, the class **GroceryList** will not work. And class **ListManager** uses GroceryList as object so that it depends on class **GroceryList**.

 

11. **The User Interface (UI) must be intuitive and responsive.**

​		Not considered because it does not affect the design directly.
