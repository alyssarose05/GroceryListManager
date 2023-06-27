# Supplementary requirements

**Author**: Team 6 (Alyssa Ayala, Juan Bermeo, Zheng Huang, Hongtao Jiang, Rongxin Yang)

- Each item must be organized into different types for the user to search through. All of the items under that type across multiple lists should appear in the search results.

- Users must also be able to search for an item by name. Multiple items may pop up if there are items with the same name but different types. They may be in either the same list or different lists.

- The user must be able to change their username and password to their account.

- When creating a new account, the user should be prompted to give a full name, username, email, and password.

- If the user forgets their password, they should be able to receive an email with their password in it. 

- When adding a new item, the user will be asked for the name, quantity type, and list name. If it doesn't already exist, it'll be automatically created. If it already exists, it'll be updated.

- The user is able to go back to where they were by pressing the "GO BACK" button on applicable activity pages.

- In addition to the list database, there should be a ListModel and ItemModel class to represent lists and items, where each list holds an array of items, and each item has a type associated with it. 

- Any required fields should not be left empty. When modifying a list, it must already exist. Anything being deleted should already exist. Lastly, anything that is being created must not exist yet. If any of these conditions are not satisfied, the requested action will not be done and will instead give an error message.
