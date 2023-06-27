<b>1. A grocery list consists of items the users want to buy at a grocery store. The application must allow users to add items to a list, delete items from a list, and change the quantity of items in the list (e.g., change from one to two pounds of apples).</b><br/>
After a grocery list is created, the Created class has the ability to add an item to it by specifying its name in the Name class. There is an aggregation of * on both sides between them to assume that there can be multiple items in a list. The deletion of items is not considered since it doesn't affect my design directly. There is a quantity attribute in the Added class that may be changed by the user.

<b>2. The application must contain a database (DB) of items and corresponding item types.</b><br/>
The GroceryListManager class is connected to the GroceryListName class so that the user can see existing grocery lists by name. This is connected to the ItemName class since a grocery list has item names in it. The ItemName class inherits the ItemType class to specify its type.

<b>3. Users must be able to add items to a list by picking them from a hierarchical list, where the first level is the item type (e.g., cereal), and the second level is the name of the actual item (e.g., shredded wheat). After adding an item, users must be able to specify a quantity for that item.</b><br/>
The Item class is inherited by the ItemType class, and the ItemType class is inherited by the ItemName class. The Added class then makes the user specify the value of the quantity attribute after adding the item to the list.

<b>4. Users must also be able to specify an item by typing its name. In this case, the application must look in its DB for items with similar names and ask the users, for each of them, whether that is the item they intended to add. If a match cannot be found, the application must ask the user to select a type for the item and then save the new item, together with its type, in its DB.</b><br/>
The Name class makes the user specify the name and type of item. There is an aggregation between this class and the Item class with values * (closest to Item) and 1 (closest to Name) to assume that multiple items can have the same name. The name is saved into the ItemName class, while its type is saved into the ItemType class that it inherits.

<b>5. Lists must be saved automatically and immediately after they are modified.</b><br/>
This isn't considered since it doesn't change my design directly.

<b>6. Users must be able to check off items in a list (without deleting them).</b><br/>
For each added item, there is a boolean checkedOff attribute that is true if the item was checked off, and false otherwise.

<b>7. Users must also be able to clear all the check-off marks in a list at once.</b><br/>
This isn't considered since it doesn't change my design directly.

<b>8. Check-off marks for a list are persistent and must also be saved immediately.</b><br/>
This isn't considered since it doesn't change my design directly.

<b>9. The application must present the items in a list grouped by type, so as to allow users to shop for a specific type of product at once (i.e., without having to go back and forth between aisles).</b><br/>
Since the ItemName class inherits the ItemType class as described for the 3rd requirement, the user can reference an item type to get the names of all items under the specified type.

<b>10. The application must support multiple lists at a time (e.g., “weekly grocery list”, “monthly farmer’s market list”). Therefore, the application must provide the users with the ability to create, (re)name, select, and delete lists.</b></br>
To create a list, the NameList class takes the name of the list, in which its aggregation between the GroceryListManager class has * on both sides to assume that there can be multiple lists at a time. There is also an aggregation of 1 on both sides between this class and the GroceryList class to assure that each list has a different name. The selection, renaming, and deletion of items are not considered since they don't affect my design directly.

<b>11. The User Interface (UI) must be intuitive and responsive.</b></br>
This isn't considered since it doesn't change my design directly.

<b>Additional information:</b>
- The Item class itself has nothing to do with the name or type of an item. The ItemType class inherits the Item class since there are different types of items. Likewise, there are named items that are a specified type.
- The GroceryList class can be assumed to hold different "types" of grocery lists, which by that I mean their names.
- If at any point a list or item is deleted, the classes "Created" and "Added" no longer apply, in which you can't access those methods for the object in question.
- The Pounds class is a utility class used solely for the quantity attribute in the Added class as a way to measure the quantity in pounds (lbs).
