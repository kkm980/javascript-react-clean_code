# javascript/react-clean_code
One liner clean code snippets in javascript/react with ES6 syntax


> Click :star:if you like the project and follow [@KrishnaKant](https://www.linkedin.com/in/krishna980/) for more updates.

---

### Table of Contents

| No. | Questions                                                                                                                                                                                                                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |                                                                                                                                                                                                                 |
| 1   | [Conditional statement](#conditional-statement)                                                                                                                                                                                                 |
| 2   | [Add a key-value pair in object conditionally](#add-a-key-value-pair-in-object-conditionally)                                                                                                                                                   |
| 3   | [Deleting a particular key from object](#deleting-a-particular-key-from-object)                                                                                                                                                                                                    |
| 4   | [filling-array-with-dummy-values](#deleting-a-particular-key-from-object)                                                                                                                    |



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





## Disclaimer

The code snippets mentioned in this repository are the summary of frequently used codes in Javascript and/or React with ES6 syntax. We cannot guarantee that only these snippets will actually make the code cleaner, smoother and optimised, nor should you focus on copying and pasting them all. The primary purpose is for you to get a sense of how some bulk codes might be replaced with one-liner ES6 conditional and operational statements!


Happy Coding 😊

---

