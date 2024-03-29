# Lab10

Must follow standards cited here:
https://github.com/olekaspt/LabStandards/blob/main/README.md

## Objective:
The objective of this Lab is to explore creating and using Hash Tables.

For this lab implement this using Smart Pointers and using Templates.

Since this template based, do not created a shared library.

DECISION POINT DUPLICATES : Decide if you are going to allow duplicate keys or reject them.  If you prevent duplicates, you will make the get case easier.  If you do allow duplicates the the Get method will need to return all items that match that key.

## Task 1:  Create a Hash Table that uses linear probing.
Design and implement a Hash Table class using linear probing as described in class.  
The data type being stored is to be Template, and the key will be a int.  For the purpose of this lab you can just have the stored value be the string representation of the key.  For example-  Key = 1234, value is “1234”.

1. Data Node
  *	The data type being stored will be a class with the following public members.  You may create any additional members are desired/required.
  *	int key.
  *	Node data.  This will be a template.
1.	The HashTable class should have the following methods fully implemented.
  *	Constructor –  No default constructor.  The construsctor will have an input indicating the maximum number of items the Hash table can store.  
  *	Hash – This should normally is private function that accepts a int and returns an int.  But for testing purposes make it public. For this, we are going to take the modulus by the maximum size of the table.
  Normally we would depend upon the hash function being defined for the class type.  But in this case we are going to cheat and force it be int, but keep the Template declations.  So use this as your Hash method.
```
  template<class keyType, class valueType> int hash_table<keyType,valueType>::hash(keyType& key)
  {
    //take keytype casted to an int and modulus with max size
    int return_value;
    int temp = (int)key;
    return_value = temp % max_size;
   }
```
  
  *	AddItem – adds an item to list.  SEE DECISION POINT DUPLICATES about duplicates.  If you allow duplicates,  you have to worry about returning a vector of smart pointers for the get case.
  *	GetItem – searches the list for a given item.  If found, it returns a pointer to the item but doesn’t remove it from the list. SEE DECISION POINT DUPLICATES about duplicates - if you allow duplicates, you will be returning a vector of smart pointers.
  *	Contains – returns an int indicating the number of items in the table.
  *	Destructor
2.	All items passed to or from the class should be done so via a pointer rather than by value.  I.e. GetItem should return a pointer to the Data Node, and not a copy of it.


## Task 2:  Create unit test your Hash class including all functions (except constructor and destructor).
Additionally Provide Unit Tests as well, with rule of thumb at least 2 per method in Task 1 except constructor and destructor.

## Task 3:  Modify your program from the Heaps and Priority Queue lab to test the performance of adding 500, 1,000, 2,000, and 5,000 random items to both the Hash class.  
The HashTable should be sized to hold 150% of the maximum number of items being stored.  Record your results in the lab report.
 
## Task 4:  Rerun the HashTable portion of task 3 with the Hash sized to hold 100%, 200%, and 500% of the maximum number of items being stored. 
Record your results and discuss the speed differences of differently sized hash tables.

## Task 5:  Bad Hash function
Change the hash function to be really bad, for example always return 0.

Rerun the Hash portion of task 3 with the Hash sized to hold 150% of the maximum number of items being stored. 
Record your results and discuss the speed differences of differently sized hash tables.

## Lab Submission:
1.	Write a lab report including the following information:
*	The sections from each task indicated to be included in the lab report.
*	Graph your results.
* Participation Rubric
*	Include a discussion of why you think the results for Task 4 were what they were.  This should suggest ideas for further investigation.
Participation rubric of teammates.  List out for your all team members how much they participated.  This will go into your Lab report.
```
	             Member1	Member2	Member3
Member1 (opinion)	33	     33	     33
Member2 (opinion)	33	     33	     33
Member3 (opinion)	33	     33	     33
```			
			
Example 			
```
	             Member1	Member2	Member3
Member1 (opinion)	33	     33	     33
Member2 (opinion)	20	     40	     40
Member3 (opinion)	20	     40	     40
```

2. Package everything needed to build your program into a tar file. 
3. Submit the tar file and Lab Report in a PDF format

## Lab Grading:
1.	30% - Task 1 has been correctly implemented and meets all requirements.
2.	10% - Task 2 has been correctly implemented and meets all requirements. 
3.	20% - Task 3 has been correctly implemented and meets all requirements. 
4.	20% - Task 4 has been correctly implemented and meets all requirements.
5.	20% - Lab report contains all required information and is well written.
If program fails to compile, 0% will be given for that Task.
