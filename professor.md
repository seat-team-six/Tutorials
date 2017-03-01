# SEAT for professors


In order to create an assignment in SEAT three easy steps need to be followed:

### Set up a classroom
Log in to the SEAT dashboard with your university email. Click on `New clasroom` and give it a name
(e.g. COMP101 2016).

### Create a SEAT file
SEAT files contain the question and solutions for each exercice in an assignment. They are defined using a subset of the MarkDown
language and therefore no special software is required. The structure of the file should be like this:

```
# Exercise 1 explanation
## Question 1.1 explanation

```Haskell code that answers question 1.1```

## Question 1.2 
```Haskell code that answers question 1.1```

# Exercise 2 explanation
## Question 2.1 explanation

```Haskell code that answers question 1.1``
````

There's no limit in the amount of exercises or questions. The code provided for
every question can be of any length. If the code for a specific questions contains more that one 
function, the main function should be the placed first. Keep in mind that functions must have
their types definitions.

Once the file is written it has to be saved as a
text file, preferibly using the `.md` extension (although not required).

### Create an assignment
Once the SEAT file is created, it can be uploaded to the SEAT dashboard. In the Dashboard, select
a classroom (or create one) and click on `New assignment`. Give it a name which is meaningfull to 
students (e.g. Week 1 assignment), select the SEAT file and click `Save`.

Now you can just get the `.pla` file by clicking `Get file`, which contains the 
exercices and solutions. This is the file that should be distributed to students so they can
open it inside VS Code and befenit from the SEAT checking.

