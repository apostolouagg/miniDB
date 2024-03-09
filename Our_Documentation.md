## DATABASE MANAGEMENT SYSTEMS 2021-2022
### PDF: [BASEIS_DEDOMENWN.pdf](https://github.com/apostolouagg/miniDB/files/14547063/BASEIS_DEDOMENWN.pdf)

### ACID Exercise

For the ACID exercise, we created 3 functions in the database.py file: 

• begin_transaction (initiates the transaction process – adds a checkpoint) 

• rollback (reverts changes) 

• commit (saves changes) 

Initially, inside the init function, we declare a flag called checkpoint, which will help us know if there is a checkpoint or not. Then, in the mdb.py file, we added 3 new keywords (begin transaction, rollback, and commit) to the keywords (in the interpret function) so that we can use them. 
In the begin_transaction function, we first check if the checkpoint is true. If it is, it means that there is already a checkpoint and the transaction has already started, so an error is displayed. If not, we create a checkpoint by setting checkpoint = True. 
In the rollback function, we first check if the checkpoint is true. If it is, we set checkpoint = False, meaning we remove the checkpoint, and load the existing database, which obviously has no changes, by calling self.load_database(). If it is false, an error is displayed as there is no checkpoint to rollback and revert changes. 
In the commit function, we again check what the checkpoint is. If it is true, we remove the checkpoint by setting it to false, and then save any changes by calling self.save_database(). If it is false, an error is displayed as there is nothing to commit.

-- Execution Example

![image](https://github.com/apostolouagg/miniDB/assets/61296853/720ee72c-5e23-4a30-9e1a-7fedaffc618e)

### Distinct Exercise

Initially, we set a variable distinct = False. Then we check if the user typed the word distinct as a command. If yes, we remove it from the commands (so that the rest of the code works smoothly), but we set distinct = True. A little later, we create an if statement where we check if the user wrote the word distinct, and inside it, we wrote all the code needed. 
Firstly, we create a list that will take the data of each row and their index. We run a for loop through the rows, which contain the index of the records to be displayed. In each iteration, the following happens: We add to the rowsData list 2 elements. The row, which is the id of the table row, and an empty list that will accept the elements of a row. Then, with another for loop going through each column of the table, inside we execute rowsData[-1][1].append(self.data[row][colID]). This means that in the most recent element of the rowsData list ([rows,[]]), we target the empty list and add the elements of the current row to it. So now we have a list with the elements of the table, and filtering follows. 
We create 2 lists, newRowsID, which will accept the index of the rows to be displayed in the end, and newRows, which will accept the values to be displayed in the end. We run a for loop on rowsData and take the idx (index) and row (the elements). If the elements do NOT exist in newRows, we add the elements to newRows and their index to newRowsID. With this command, we check if something exists twice in the final lists, so the filtering is successful.

-- Execution Example

![image](https://github.com/apostolouagg/miniDB/assets/61296853/5b3cd087-4c3e-4803-8d96-a787ac7c77c0)

![image](https://github.com/apostolouagg/miniDB/assets/61296853/19746fb9-a92c-4ce3-b25a-f7ea61ece1e4)

![image](https://github.com/apostolouagg/miniDB/assets/61296853/d541986e-456c-41c4-a715-773b5e8bc997)

![image](https://github.com/apostolouagg/miniDB/assets/61296853/fb86cbcf-509c-4304-a949-62721f053b39)

![image](https://github.com/apostolouagg/miniDB/assets/61296853/337f03a6-8e1f-4f52-a8a7-abbc031c3e9b)

![image](https://github.com/apostolouagg/miniDB/assets/61296853/0805c057-1404-4e64-a035-0878672e0332)
