- It's done now. *...*
  id:: 63d80b7d-c5b5-4b4a-90a2-cdc1efdeae93
  *Code displays below on console:**Added submitted Student Name, Email, Age, and Class*
  *Removed submitted Student Name, Email, Age, and Class*
- ```js
  // Arrays
  // const someNumber = 1;
  // const someString = "a string";
  
  ///
  // const anArr = [1, "a string", "another"];
  
  // Problem (IN): An admin needs an app to store a list of students and their basic info.
  
  // @TODO: Expand the app so we collect the student's age and email and it shows the result in the console
  ///     ... the goal is, when your user submits an entry, they see the following in the console:
  ///     ... "Student: <Submitted Student Name>, Email: <submitted@email>, Age: <Submitted age>, Class: <Submitted class>
  
  // HTML
  // create a form to get info from users
  // [x] an input:text#name
  // [x] an input:text#email
  // an input:text#age
  // an input:text#class
  
  // JS
  // 1. get the inputs into variables
  const formEl = document.querySelector("form");
  const fullNameEl = document.querySelector("#full-name");
  const emailEl = document.querySelector("#email");
  const ageEl = document.querySelector("#age");
  const classEl = document.querySelector("#s-class");
  
  const deleteEl = document.querySelector("#delete");
  
  // 3. The listener triggers a function that **saves the data**
  let students = [];
  //let studentsOriginal = ["One", "Two", "Three", 4, 5, 6, 7, 8];
  
  // 2. define an eventListener on the submission of the form
  formEl.addEventListener("submit", function (e) {
    e.preventDefault();
  
    const fullName = fullNameEl.value;
    const email = emailEl.value;
    const age = ageEl.value;
    const classs = classEl.value;
  
    const studentObjectLiteral = {
      full_name: fullName,
      an_email: email,
      s_age: age,
      s_class: classs
    };
  
    // adding an item to the array
  
    // to the end
    // students.push(fullName);
    // students.push(email);
  
    students.push(studentObjectLiteral);
  
    // to the start
    // students.unshift(fullName)
  
    fullNameEl.value = "";
    emailEl.value = "";
    ageEl.value = "";
    classEl.value = "";
  
    fullNameEl.focus();
  
    console.log(students);
  
    // console.log(students.length);
    //
    // console.log(students[students.length - 1]);
  
    for (let item of students) {
      console.log(
        `- Student: ${item["full_name"]}\n- Email:  ${item["an_email"]}\n- Age: ${item["s_age"]}\n- Class: ${item["s_class"]}`
      );
    }
  });
  ///     ... "Student: <Submitted Student Name>, Email: <submitted@email>, Age: <Submitted age>, Class: <Submitted class>
  
  deleteEl.addEventListener("click", function () {
    // remove an item from an array
  
    // from the end
    // studentsOriginal.pop();
  
    //from the start
    students.shift();
  
    console.log("item removed");
  
    // shows the items left
    if (students.length > 0) {
      for (let item of students) {
        console.log(
          `Student: ${item["full_name"]}, Email:  ${item["an_email"]}, Age: ${item["s_age"]}, Class: ${item["s_class"]}`
        );
      }
    } else {
      console.log("Nothing left to remove. Add new students");
    }
  });
  
  // console.log(students);
  // console.log(studentsOriginal);
  
  // Loop through items in an array
  
  // array = students
  
  // looping for ..of
  // let s;
  // studentsOriginal
  // for(  let item  of studentsOriginal ){
  
  //     console.log(s)
  
  // }
  // form.addEventListener("click", function (event){ .... })
  
  // ... forEach
  // studentsOriginal.forEach(function(item){  console.log(item)   })
  
  // studentsOriginal.forEach( item => console.log(item) );
  
  ```