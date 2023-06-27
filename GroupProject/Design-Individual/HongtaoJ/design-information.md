1. **A grocery list consists of items the users want to buy at a grocery store. The application must allow users to add items to a list, delete items from a list, and change the quantity of items in the list (e.g., change from one to two pounds of apples).**

   - I start out with two classes one is User, another one is application manger which have the following operations user can add items to a list, delete items from a list, and change the quantity of items in the list. On User side the user has an ID that uniquely defined each user and helps the application manger to determine each user.
2. **The application must contain a database (DB) of items and corresponding item types.**

   - I had created a database to store all the items and the item types, only application manger can access the DB and it has two attributes which are items and the item types.
3. **Users must be able to add items to a list by picking them from a hierarchical list, where the first level is the item type (e.g., cereal), and the second level is the name of the actual item (e.g., shredded wheat). After adding an item, users must be able to specify a quantity for that item.**

   - I had created a class called hierarchical list which the user can access it via application manger, once the user reaches this class, user can add the item directly to the list and it consisted of three operations, which are:

   - getItemType() - Stores all the item types
   - getActualItem() -  Stores all the actual items with their names.
   - quantity() - able to change the amount of an item.
4. **Users must also be able to specify an item by typing its name. In this case, the application must look in its DB for items with similar names and ask the users, for each of them, whether that is the item they intended to add. If a match cannot be found, the application must ask the user to select a type for the item and then save the new item, together with its type, in its DB.**

   - Users request search specific item name via application manger, then application manger will forward the request to the database, if the database has the match item, send back the item to application manger, then application manger will forward the message to the user. If the match cannot be found the application manger will forward the message to the user and ask for the item type.
5. **Lists must be saved automatically and immediately after they are modified.**
   - It does not affect the design directly because once the list is modified, it will be saved in the DB.
6. and 7 **Users must be able to check off items in a list (without deleting them). Users must also be able to clear all the check-off marks in a list at once****
   - I had created a class called List with operations:
   - CheckOffItems - users can check off item without deleting them.

   - ClearMarks - users can clear the mark all at once.
7.  Combined 6 and 7 together.
8. **Check-off marks for a list are persistent and must also be saved immediately.**
   - It does not affect the design directly since all the lists are link to the DB, so it will be saved after each modification.
9. **The application must present the items in a list grouped by type, so as to allow users to shop for a specific type of product at once (i.e., without having to go back and forth between aisles).**
   - The class hierarchical list has the operation getItemType(), the user can access it via the  application manger, so it is not necessary to create another class to store the item type.
10. **The application must support multiple lists at a time (e.g., “weekly grocery list”, “monthly farmer’s market list”). Therefore, the application must provide the users with the ability to create, (re)name, select, and delete lists.**
   - I had a different class called multiple lists which is an extended class from the lists class, so that the list class also can use the following operations. Multiple lists it has two attributes and four operations: 
   - ListType(attribute) - users can specify the list type.
   - ListName(attribute) - users can specify the list name.
   - createList() - users can create a list.
   - renameList() - users can rename current list.
   - deleteList()- users can delete list by the list name.
11. **The User Interface (UI) must be intuitive and responsive.**
    - Not consider because it does not affect the design directly.