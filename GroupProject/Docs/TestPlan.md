# Test Plan

**Author**: Team 6 (Alyssa Ayala, Juan Bermeo, Zheng Huang, Hongtao Jiang, Rongxin Yang)

## 1 Testing Strategy

### 1.1 Overall strategy

All tests below will be performed by the proposed verifiers in the project plan. As the developers write the code, the verifiers will check that the code is correct and usable.

- Unit Testing: Each unit test is associated with an action that we would do in the app. It is important that the changes that we make to our lists are reflected in the database, in which the main point of these tests will be to check that the database has been modified.

- Integration Testing: This type of test will see if there any ways in which a specific action of the GLM app could possible interfere with the actions of another. For example, if a list could be created but then prevent any more lists from being created, then this change has negatively affected the app.

- System Testing: Test to see if the app works as expected. The app should be able to not crash at any point while the app is running, so long as there is a user that is logged in after the login screen and being brought to the User activivity page. In which case, there must always be a user that is logged in throughout the rest of the app.

- Regression Testing: This application must be able to run on at least API 21. We will be checking that this app can be run on lower APIs using different emulators with different APIs, getting lower as the tests continue.

### 1.2 Test Selection

While a component of the application is being developed, we will use whitebox testing to ensure that the code is written properly. After a component is done being developed, we will use black box testing to see if we perhaps missed something, and if an issue is found, we will go back to address it.

### 1.3 Adequacy Criterion

We will assess the quality of test cases by discussing and trying to find edge cases that may cause the application to behave incorrectly. We will create an account in the app that we will use to test the app's different functions. During the development of a component, we will focus on whitebox testing and when specific component is done being developed we will test it using blackbox testing.

### 1.4 Bug Tracking

Debugging will be done through the process of going through what worked last time. Any edits that were made after that may have something to do with what may be causing a bug. We will then track this line of code down and modify it to the point where the application works again, while working on a permanent solution.

### 1.5 Technology

These tests are done manually with the help of a test account in the app. With it, we will modify lists and items to ensure that everything works, as explained in the "Steps" column below.

## 2 Test Cases

Final results below:

| Test case                                                   | Purpose                                                      | Steps                                                        | Expected result                                              | Actual result | Pass/Fail |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------- | --------- |
| Search for Item                                       | To check when user input an item name, does the application returns back the correct item. | Login and go to "SEARCH BY NAME" or "SEARCH BY TYPE". Type in a query and press "SEARCH".| Search results pop up for all items with same name or type |  Search results pop up for all items with same name or type       |  Pass                                                                  |                                                              |               |           |
| Add Item to List                                          | Check that user can successfully add the item to  their list. | Login and go to "ITEMS". Type in the item's name, type, quantity, and list name. Then press the "ADD/UPDATE" button. | Item added/updated in list     | Item added/updated in list             |   Pass       |
| Delete from the list                                      | Allows user to remove item(s) from their list.               | Login and go to "ITEMS". Type in the item's name, type, and list name. Then press the "DELETE" button. | Deleted item from list                       |  Deleted item from list            |  Pass        |
| Set Quantity                                           | Allows user to set the quantity of item(S).                  | Login and go to "ITEMS". Type in the item's name, type, quantity, and list name. Then press the "ADD/UPDATE" button. | Item updated                                   | Item updated              | Pass     |
| Check Off Marks                                      | Allows user to check off marks.                              | Login and go to "ITEMS". Type in the item's name, type, and list name. Then press the "CHECK/UNCHECK" button. | Item checked/unchecked                                                      |  Item checked/unchecked            |  Pass         |
| Clear Check Marks                                            | Allows user to clear check marks at once.                          | Login and go to "LISTS". Long click a list and click "VIEW ITEMS". Click on the "CLEAR CHECK OFFS" button. | Check offs cleared                    |  Check offs cleared             |   Pass        |
| Leave User Name and(or) Password empty fail to create account. | User cannot create account nor log in if user name and(or)password are left empty. | Click on the "REGISTER TEXT" and leave any fields empty.              | Returned error message                                        |  Returned error message             |  Pass         |
| Create List                                                | Allows user to create new list.                              | Login and go to "LISTS". Click on the "ADD button and type a new list name, then click "CREATE". | New list created                                       | New list created      |  Pass         |
| Delete List                                              | Allows user to delete list.                                  | Login and go to "LISTS". Long click on a list. Press the "DELETE" button, then when asked to confirm, press "DELETE" again. | Deleted list                         |  Deleted list           |  Pass         |
| Rename List                                       | Allows user to rename a list.                                | Login and go to "LISTS". Long click on a list. Press the "RENAME THE LIST" button. Type a new list name, then click "RENAME." | List renamed                                        |   List renamed            |  Pass         |
| Save Changes | To check if all changes are saved to the database. | After making modifications to the account, press the "LOGOUT" button on the "USER" page (or restart the app) and login again, making sure that everything is just as you left it. | All data persists | All data persists | Pass |
