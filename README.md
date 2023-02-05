# javascript/react-clean_code
One liner clean code snippets in javascript/react with ES6 syntax


> Click :star:if you like the project and follow [@KrishnaKant](https://www.linkedin.com/in/krishna980/) for more updates.

---

### Table of Contents

| No. | Questions                                                                                                                                                                                                                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     |                                                                                                                                                                                                                  |
| 1   | [Conditional statement](#conditional-statement)                                                                                                                                                                                                 |
| 2   | [Add a key-value pair in object conditionally](#add-a-key-value-pair-in-object-conditionally)                                                                                                                                                   |
| 3   | [Deleting a particular key from object](#deleting-a-particular-key-from-object)                                                                                                                                                                                                    |
| 4   | [Filling array with dummy values](#filling-array-with-dummy-values)                                                                                                                    |

| 5   | [Call function if it exists](#call-function-if-it-exists)                                                                                                                    |

| 6   | [String to Number](#string-to-number)                                                                                                                    |

| 7   | [Console related optimisation](#console-related-optimisation)                                                                                                                    |

| 8   | [Overwrite by default values](#overwrite-by-default-values)                                                                                                                    |

| 9   | [Conditional default value assignment for numbers](#conditional-default-value-assignment-for-numbers)                                                                                                                    |

---


1. ### Conditional Statement


   
   **Plain conditional operation**

      ```javascript
        const is_employee=true;
        let company
        if(is_employee){
          company='Inventives.ai';
        }
        else{
          company=null;
        }
      ```


   - We will use Ternary operator
   
     ```javascript
        const is_employee=true;
        let company = is_employee?company='Inventives.ai':company=null;
      ```

    **[⬆ Back to Top](#table-of-contents)**




2. ### Add a key-value pair in object conditionally
   
   **Plain conditional operation**

      ```javascript
        const is_employee=true;

        const student={
            name:'Krishna Kant',
            roll:'AD203'
        };

        if(is_employee){
            student.company='Inventives.ai';
        };
      ```


   We will use Spread operator to spread new object with one property inside the previously defined object and the conditional operator `&&` to achieve the task conditionally

   1. **While defining the object:**

     - We are injecting the new property at time of defining the object only

      ```javascript
        const is_employee=true;

        const student={
            name:'Krishna Kant',
            roll:'AD203',
            stream:'MERN stack web development',
            ...(is_employee && {company:'Inventives.ai})
        };
      ```

   2. **After object has been defined**

     - We are injecting the new property after the object has been defined with its default key value pairs.

      ```javascript
         const is_employee=true;
         let student={
          name:'Krishna Kant',
          roll:'AD203'
         };

         student={
          ...student,
          ...(is_employee && {company: 5})
         };
      ```

      **[⬆ Back to Top](#table-of-contents)**



3. ### Deleting a particular key from object

   **Plain conditional operation**

      ```javascript
        const is_employee=true;

        const student={
            name:'Krishna Kant',
            roll:'AD203',
            stream:'MERN stack web development',
            company:'Inventives.ai'
        };

        delete student.salary;
      ```


   - We will use Spread operator to delete one property inside the previously defined object.
   
     ```javascript
        let student={
            name:'Krishna Kant',
            roll:'AD203',
            stream:'MERN stack web development',
            company:'Inventives.ai'
        };

        let {company, ...newStudent} = student;
        student=newStudent;

      ```

    **[⬆ Back to Top](#table-of-contents)**


 - More code snippets are being added


4. ### Filling array with dummy values


   
   **Plain conditional operation**

      ```javascript
        const arr_length=6;
        for(let i=0;i<arr_length;i++){
          dummyArr[i] {'written_by' : 'Krishna Kant'};
        }
      ```


   - We will use Array instance with Higher Order Function--> array.map()
   
     ```javascript

        const arr_length=6;
        let dummyArr = new Array(arr_length).fill(null).map(()=>({'written_by' : 'Krishna Kant'}));
      ```

    **[⬆ Back to Top](#table-of-contents)**


5. ### Call function if it exists
 
   **Plain javascript conditional calling**

      ```javascript
        const fun=()=>{
          <!-- do something -->
        }

       <!-- call fun function if it exists -->
        if(fun){
          fun();
        }
      ```


   - We will use logical AND operator to achieve same task
   
     ```javascript

       const fun=()=>{
          <!-- do something -->
        }

       <!-- call fun function if it exists -->
        fun && fun();

      ```

      - Better way to do this
   
     ```javascript

       const fun=()=>{
          <!-- do something -->
        }

       fun?.();

      ```

    **[⬆ Back to Top](#table-of-contents)**



6. ### String to Number

   **Plain javascript conversion**

      ```javascript
        const num = '22';

        console.log(Number(num));
      ```
    - Better way to do this using unary plus operator

      ```javascript
        const num = '22';

        console.log(+num);
      ```


    **[⬆ Back to Top](#table-of-contents)**


7. ### Console related optimization

   **i. Plain javascript conditional console**

      ```javascript
        const country = 'India';

        if(country){
          console.log(`country is:${country}`);
        }
      ```
    - Better way to do console using ***console.assert***

      ```javascript
        const country = 'India';
        console.assert(country, `country is ${country}`);
      ```


   **ii. Named variable console**
    
    - Often we need to console for debugging, to keep track of variable, part and line of code, variable named console can be done by using object format.

      ```javascript
         const name = 'Krishna Kant';
         
         console.log(name);
      ```
  - Better way to do it

      ```javascript
        const name = 'Krishna Kant';

        console.log({name});
      ```


   **iii. Grouping a set of console together**
    
  - Often we need to console a set of variables in a given component or function for debugging, to keep track of variable, part and line of code, we can bind them together using ***console.group***

      ```javascript
        const name = 'Krishna Kant';
        const country = 'India';

        const employee_details = {
          organisation: 'Inventives.ai',
          project: 'health care product',
          team_size:'5'
        }
        
        console.group('general');

        console.log({name});
        console.log({country});

        console.groupEnd();


        console.group('employe_details');

        console.log({name});
        console.log({country});

        console.groupEnd();

      ```


    **[⬆ Back to Top](#table-of-contents)**


8. ### Overwrite blocked variables by default values

  - There might be instances where some variables from database could have undefined/null values and could break the code operation potentially, so we need to replace them by default values set by us manually.

  **Noob assignment**

      ```javascript
          let name = 'Krishna Kant';
          let organisation = 'Inventives.ai';
          let project = 'health care product';
          let team_size = '5';

        function print(name, organisation, project, team_size){
          const employee_name = name || 'Krishna';
          const employee_organisation = organisation || 'Inventives';
          const project = project || 'health care startup project';
        }
        
      ```
  - Better way to achieve this task using default parameters, what it does is if the value is not null or undefined, it will be assigned to the new variable otherwise new variable value assignment will pick up default values.

     ```javascript
          let name = 'Krishna Kant';
          let organisation = 'Inventives.ai';
          let project = 'health care product';
          let team_size = '5';

        function redefine(name ='Krishna', organisation = 'Inventives', project = 'health care startup project', team_size = 'five'){
          const employee_name = name;
          const employee_organisation;
          const project = project;
        }
        
      ```


9. ### Conditional default value assignment for numbers

   - Using *** || *** operator with number data types might be problematic while logical default value assignment if some variables have value 0 because 0 is read as falsey value by logical operators, 

  **Plain logical assignment by || operator**

      ```javascript
          const age = 0;
          const pending_tasks =0;
          const team_size = 5;

          const age_copy = age || 1;    <! --results 1 -->
          const pending_tasks_copy = pending_tasks || 1; <! --results 1 -->
          const team_size_copy = team_size || 2; <! --results 5 -->

        
      ```
  - Better way to achieve this task using default parameters, what it does is if the value is not null or undefined, it will be assigned to the new variable otherwise new variable value assignment will pick up default values.

      ```javascript
          const age = 0;
          const pending_tasks =0;
          const team_size = 5;

          const age_copy = age ? 1;    <! --results 0 -->
          const pending_tasks_copy = pending_tasks || 1; <! --results 0 -->
          const team_size_copy = team_size || 2; <! --results 5 -->

        
      ```

    **[⬆ Back to Top](#table-of-contents)**


- More code snippets are being added




## Disclaimer

These code snippets are not to understand how to do a task from scratch, assuming that you already know how to achieve a given task successfully, above snippets focus more on clean, reusability, optimisation and lesser-code principle to make the code simple, organised and enhanced.
The code snippets mentioned in this repository are the summary of frequently used codes in Javascript and/or React with ES6 syntax. We cannot guarantee that only these snippets will actually make the code cleaner, smoother and optimised, nor should you focus on copying and pasting them all. The primary purpose is for you to get a sense of how some bulk codes might be replaced with one-liner ES6 conditional and operational statements!


Happy Coding 😊

---

