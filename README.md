# Tom Tutone T3A1-Workbook

## Q1. Provide an overview and description of a standard source control process for a large project /6

When working on a large-scale project, backing up the project, tracking its changes and making it easily accessible to team members is a fundamental consideration. Using source control software, such as Git and Mecurial, is the industry standard for programmers and allows teams to share and work on projects concurrently. These tools monitor changes in a project's files, integrate them into a defined "main" collection and provide functions to update or regress files collection so that team members can access the project's most current stable files.

In a large-scale project, it is mandatory that team members agree upon a protocol for saving changes to the project's files. This includes designating standardised naming and commiting conventions, rules for the scope of each change and how the team will manage conflicting opinions and edits. In the context of using Git, a team must decide where the project will be hosted (typically on a remote repository using Github), how each commit message will be structured, protocol for updating code that multiple users concurrently depend on (such as a parent module), and designating the frequency of when changes should be merged to the main branch.

Notably, there are two distinct project repository structures which teams can choose from when initialising their project: the shared repository model or the fork and pull model (Github, 2024). The fork and pull model is typically utilised in open-sourced projects with mass contributors and requires individuals to fork a base repository which creates an independent copy repository of the entire project. These forked repositories are then advanced as required before the individual submits a pull request to merge their proposed changes to the main repository for an administrator to review and approve or reject. Alternatively, the shared repository model is more typically used in smaller teams and consists of team members all sharing access to a single remote repository. Linked to the main respository, team members create distinct branches, which segregate and track changes that deviate from the main repository branch, to focus on particular feature implementations or bug fixes. When the branch is complete, team members can either submit a pull request for the team to review the changes or simply merge the changes if they are confident that the changes are appropriate. The two strategies are broadly similar but require different levels of filtering and trust. In a project where the team is in constant communication, it is likely appropriate to use a shared repository.

Working on code in branches has distinct advantages in small teams as well. Sharing access to the same repository, team members can initialise as many branches as neccessary and host segregated development streams in a mutually accessible location. This allows team members to easily switch between branches as required and assist each other with challenges. Once a branch is finished, it can be merged to the main branch with a single commit message which clearly indentifies when it was integrated and its purpose. Typically, branches are squashed before they are committed to the main branch so that their commit timeline is not saved to the main branch and does not muddy the project's commit timeline (Ernst, 2024b).

There are various additional considerations when using a shared repository and branch-based development model however. When working on a branch, team members must make sure not to edit code that other branches depend on without consulting the team. Simple reconfiguration of a shared file can easily cause a branch to deviate from parallel branches and raise multiple time-consuming merge conflicts when each branch is finally merged (Ernst, 2024a). If a shared dependency must be updated, it should be edited in its own distinct branch and merged with the main branch as soon as possible so that any unfinished branches can sync these changes and continue working. For the same reason, it is crucial that in-progress branches sync changes from the main branch daily or more frequently depending on the project's update frequency. Finally, when commencing a branch, such as a bug fix patch, it is great practice to generate tests before work begins. Creating tests which initially fail but pass when the branch is complete gradually ensures the project's robustness and builds the project's collection of tests. It also assists in focusing the branch ensuring that its intented impact can be clearly tracked in the tests and these features can be preserved in future branches easily (Ernst, 2024b).

### References

Ernst, M. (2024a) _[How to create and review a GitHub pull request](https://homes.cs.washington.edu/~mernst/advice/github-pull-request.html)_, Computer Science & Engineering University of Washington Community Website, accessed 27 July 2024.

Ernst, M. (2024b) _[Version control concepts and best practices](https://homes.cs.washington.edu/~mernst/advice/version-control.html)_, Computer Science & Engineering University of Washington Community Website, accessed 22 July 2024.

Github (2024) _[About collaborative development models](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models)_, Github Docs Website, accessed 7 August 2024.

## Q2. What are the most important aspects of quality software? /6

Designing quality software requires a thorough understanding of the contexts within which the product needs to function. The software design process typically begins with considering one or more use cases for the tool, the challenges that users face in these scenarios and creating a solution suitable for these conditions. However, developing successful software requires developers to consider circumstances beyond these baseline applications and account for how the software will work over in varied use cases over an extended period of time. Boehm's (1976) software quality model and the ISO's (International Organization for Standardization) 25010 publication (ISO 25000, 2022) provide frameworks for describing and designing quality software.

Both Boehm and the ISO describe the importance of quality software being portable. Portablility refers to a software's ability to function on varied machines with varied hardware specifications. When designing, developers must account for the environments that they are developing in and how they differ from their end users'. Software provides no use to potential users if their computers or internet connections cannot handle an application. To account for these differences, developers should test their software on a variety of devices and, broadly, must consider their target users and the tools they use and have access to.

Boehm acknowledges that portability often works in opposition to efficiency as a program can be optimised for a particular system only to function worse on other systems yet, this tradeoff must be balanced carefully to create quality software (Boehm, 1976). Efficiency in quality software describes utilising the available resources for that software to run. This can refer to processing power but also refers to other system attributes. A common example of an efficiency tradeoff is designing web applications for desktops versus mobiles. Efficiency considerations in this context refer not only to the devices' processing power but also their efficiency in utilising screen space to communicate information. Quality software considers the limitations and strengths of different devices and leverages them in a resourceful way.

Scalability is an integral characteristic of quality software that is complimented by flexibility (ISO 25000, 2022). Developers need to consider how their tools can and will be implemented into workflows and account for varying scales of data that the software needs to handle. Quality software must scale to users' needs and handle large deployments and minimal deployments gracefully.

Both the ISO and Boehm identify interaction capability and the ease of use of software as a key quality trait (ISO 25000, 2022 & Boehm, 1976). The ISO's description extends on ease of use and describes that quality software must be reasonable to learn as well. Usability is a fundamental concern of software design as a tool fundamentally does not work if individuals cannot operate it. Learnability further accentuates the need for developers to understand user contexts and the different backgrounds of individuals who will use their software. Understanding a user base allows developers to tune the interface or functionality of software so it can be engaged with and learnt appropriately.

One point of difference between the two models is that the ISO 25010 describes security as a neccessity of quality software (ISO 25000, 2022) whereas Boehm's does not. This can likely be attributed to an increased emphasis on data privacy in the internet age when the ISO's standards were written. When designing software, developers must consider the risks that the tool generates for users including system vulnerabilities and the risks in storing their data. It is essential that users are guaranteed confidentiality when using a software as privacy is as much of a resource to consider for users as time and financial costs. Security also encompasses data integrity and confirmation that saved data is consistent and reliable. Software must implement reliable data storage and access to be considered effective.

Finally, both models value maintainability and the ease that software can be updated. At a coding level, maintainability means producing code that is clearly modularised and formatted so that bugs can be fixed cleanly and without large overhauls. At the user level, maintainability means users are able to install updates easily or update their own processes using the app logically.

Creating quality software requires clear planning and considerate implementation so that tools function as intended in varied, future-proofed contexts. Developers must strive to create portable, efficient, flexible, useable, maintainable and secure software and, to do so, must consider the different contexts that the software will be used in.

### References

ISO 25000 (2022) _[ISO/IEC 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)_, ISO 25000 website, accessed 27 July 2024.

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

## Q3. Outline a standard high level structure for a MERN stack application and explain the components /6

The MERN stack is a popular collection of technologies which can be used to create a dynamic web application. MERN stands for MongoDB, Express, React JS and Node.js, four tools which all use JavaScript syntax and complimentarily fill the roles required to generate webpages, handle interactions with them as well as store and serve their data.

React JS is the front-end component of the MERN stack and a web framework used to create fast-loading, responsive webpages. React uses JSX, a JavaScript syntax extension which hybridises JavaScript and HTML so that users can easily describe HTML webpages. The framework uses component-based design where the different elements of a HTML page are modularised to be reused, like building blocks, and pieced together to create varying webpage layouts. React is particularly useful for creating responsive webpages which can track state. Using the ```useState``` hook, developers are able to use getter and setter functions to track state changes based on user interaction such as clicking on a button. Combined with the ```useEffect``` hook, changes in state can trigger updates in the webpage layout and display differing data. React is able to rapidly update the display due to its underlying virtual DOM technologies. The virtual DOM is a recreation of the browser DOM (Document Object Model) which describes the elements of a loaded webpage as a JS object. React creates a virtual DOM as the page is initially rendered and creates a new copy whenever the webpage is to be changed in response to an updated state. The two iterations are compared to identify where there are differences and React compartmentally updates only the neccessary elements, preventing an entire page reload. These systems allows React to display display dynamic pages efficiently.

Express is a Node package used to create APIs and handle routing configuration, facilitating the connection and interaction between a web application's front-end and back-end. Using Express, a developer is able to define routers which describe how a webpage or API responds to different HTTP request types at defined URIs. Express allows for the use of middleware to handle requests and manipulate any data they are sent with or lack. A typical middleware used in Express is the ```express.json()``` function which converts a request's body into JSON, so that it can be manipulated in the application's back-end. Express is particularly effective for developers because its syntax and router objects allow for DRY, reuseable routing elements which helps speed up development (GeeksforGeeks, 2023).

Node.js is a runtime environment which allows the Express scripting of a web application to run. Express is built using JavaScript, a language which can typically only be executed by web browsers. Node provides an alternative environment to run JS scripts, including Express APIs, so that the webpage and server-side logic can be executed concurrently and written in the same language. In addition, Node.js is bolstered by a large developmental community that generates packages to extend server-side capabilities.

Finally, MongoDB is the database layer of the MERN stack. MongoDB is a NoSQL database that can be interacted with using JavaScript code. MongoDB databases can be run locally or using MongoDB Inc.'s cloud services. MongoDB is particularly valued due to its flexible data structures which allow developers to define, store and query instances without the strict formatting required by SQL databases (GeeksforGeeks, 2023). In the MERN stack, MongoDB is used to store the data that populates a page and to record users' posted data outside of the session scope.

Considering the MERN stack in totality, the React layer provides the tools to create webpages for users to interact with, the Express layer handles the user's interactions by requesting and handling the appropriate resources, Node.js allows Express to be executed outside of the broser and offers additional functionality and MongoDB stores the application's data. Besides effective performance, the key element that makes the MERN stack popular is its consistent use of JavaScript eliminating script conversions and allowing developers to easily learn the stack's syntax (MongoDB, n.d. & Kadam et. al., 2023).

### References

GeeksforGeeks (2023) _[MERN Stack](https://www.geeksforgeeks.org/mern-stack/)_, GeeksforGeeks website, accessed 27 July 2024.

GeeksforGeeks (2024) _[ReactJS Virtual DOM](https://www.geeksforgeeks.org/reactjs-virtual-dom/)_, GeeksforGeeks website, accessed 28 July 2024.

Kadam, Y., Goplani, A, Mattoo, S., Gupta, S. K., Amrutkar, D., Dhanke, J. (2023). 'Introduction to MERN Stack & Comparison with Previous Technologies', _European Chemical Bulletin_ 12(4), pp. 14382-14386. DOI: 10.48047/ecb/2023.12.si4.1300.

MongoDB (n.d.) _[Mern Stack Explained](https://www.mongodb.com/resources/languages/mern-stack-tutorial)_, MongoDB website, accessed 27 July 2024.

## Q4. A team is about to engage in a project, developing a website for a small business. What knowledge and skills would they need in order to develop the project? /6

To design and create a website for a business, a development team needs a specific understanding of the business' requirements. Considering Boehm's (1976) model for quality software, a website should be designed considering the contexts that it will be engaged with. Firstly, the development team must understand what core functionality the website needs to have to aid the business. By extension, the team needs to understand the typical website user so that the website can be designed to suit their hardware and interface requirements. For example, a general practice business will fundamentally need to display the business' contact information, service offerings and information about the clinic's doctors. On top of these base features, the business may require the application to host and track an online booking system implemented with dynamic webpages and form submissions. Alternatively, the company may want to keep these systems on site for simplicity. When designing the webpage, it is vital that the development team understands their client's desires. By extension, depending on the clinic's customer base, the site's typical user may have limited website literacy and require a simpler user interface to accomodate their abilities. To effectively develop a website for a business, the development team must fulfill Boehm's recommendations for usability and portability by understanding their end user. By extension, the team needs to understand the business' maintenance plans following the website's launch to ensure that it is appropriately future-proofed. If the business does not plan on updating the site frequently, the team needs to ensure that the website's layout and functionality is robust, a consideration that can shape the entire design process. It is key that a team understands the contexts that their website will be used in to successfully design and implement it.

There are also distinct technical skills a development team requires to create a website. In many contexts, the MERN stack provides all of the tools required to make an appropriate website for a small business. To use the MERN stack, the design team must know how to write JavaScript as well as the specific syntax of MongoDB, Express, React JS and how to configure and use Node.js. Besides these defined skills, there are complementary understandings the team must apply to use these tools. When designing the back-end and routing for the website, the developers must implement RESTful practices so that the website's database functions in a stable and maintainable way. This includes defining routes that are logical and send query results in a consistent way. Notably, creating a RESTful API requires a reliable database and consistant storage structure. Because MongoDB is a NoSQL database, the development team has full control over how instances are recorded, a trait that allows for quick initialisation but can also permit messy formatting. For these reasons, the development team must have a technical knowledge of the MERN stack but also a conceptual knowledge of how to design the website's database and backend to be robust and future-proofed.

In addition to project understanding and technical knowledge, the team members require project management and planning skills. In many contemporary projects, Agile methodologies are used to set goals, manage deadlines and respond to project challenges as they arise. Adopting Agile techniques including using Kanban boards to visually communicate progress and prioritise tasks, scheduling daily stand-ups and feedback sessions and dedicating resources based on team agreement are all beneficial practices that will bolster a team's productivity (Moe, et. all, 2014). Whilst a development team does not need to know Agile project management specifically, the team requires a structured division of work to ensure all tasks can be completed on schedule. In a technical context, project management requires a team to develop and enforce source control habits. Using Git or an alternative software, team members must know how to back-up and share their work and how to archive their progress with succinct commit messages and pull requests.

When creating a website, a development team requires technical and conceptual skills to handle the design, programming and project management elements of the task.

### References

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

Brede Moe, N., Dingsøyr, T., Dyba, T. (2014) 'Agile Project Management', in Ruhe, G., Wohlin, C. (eds.) _Software Project Management in a Changing World_. Berlin: Springer-Verlag, pp. 277-300.

## Q5. With reference to one of your own projects, discuss what knowledge or skills were required to complete your project, and to overcome challenges /6

Designing and creating a web server API using Flask and Postgres was a project that required distinct technical and conceptual skills. Within this project, I leveraged these tools as well as SQLAlchemy and marshmallow to deliver a parent-teacher communication API that features user authentication and allows parent and teacher accounts to exchange comments about students, parents to enter contact information for their child on different attendance days and endpoints for teachers to access this contact information.

A core challenge creating the application was designing the database to allow for RESTful endpoints. When I began the project, I found it challenging to identify what data needed to be stored and how to best structure the database tables. Specifically, the task of normalising the data was daunting. To handle this macro challenge, I broke down the task down into its technical and conceptual elements. First, I found it helpful to research similar API tools that childcare businesses used to facilitate their data and communication. I then identified the features that my application needed to emulate these applications and read reviews to get inspiration for how to improve them. For example, one key design choice that affected the database was to improve the security of the app by reducing the amount of personal input data required. To refine the tables, I completed additional research into ERD diagrams and compared my work to industry examples. Gradually, I improved the tables by considering the data that should be available at the different endpoints based on different imagined user stories. In addition, I continued to review the table designs throughout the API's implementation which highlighted simplifying changes such as using populated foreign keys with specific data to make the returns clearer and allowed me to remove repetitive columns.

In addition to database design skills, the task required me to improve my understanding of models and schemas as well as my ability to leverage software documentation. Connecting the Flask routes to the database was simple to implement yet, as I continued programming, I found that my models allowed users to input flawed data which would raise errors. marshmallow's validation tools proved a powerful and convenient way to prevent these errors but, I did not initially understand the breadth of methods available. For example, the API featured input routes where I wanted users choose one of three values yet I was not able to design a front-end solution to enforce this. In this instance, I was able to refer to the marshmallow documentation and find the ```OneOf()``` validator which was perfect for the situation. In addition, I had trouble handling data type errors which would arise when POST requests were submitted with  formatting inconsistencies. One example of this was, when handling a phone number, Python disregards an initial zero digit which, in turn, would raise a marshmallow validation error. This was challenging to identify but, after logging the data at each stage, I was able find the error and convert a number input to a string before adding the zero again, knowing that marshmallow can interpret both numbers and strings. Another example was handling boolean values for an ```is_admin``` attribute. The request body would inconsistently be interpretted and it took lengthy troubleshooting to recognise that an error would arise when the boolean was not submitted as a string. I solved this issue by generating a matching boolean value based on the input string allowing users to submit either a boolean or a string and get the same result. Each of these issues required patient research and a more through understanding of Flask, marshmallow and SQLAlchemy behaviours. Preventing these issues at the API level makes the project more robust and easy to incorporate into a front-end application.

Designing and creating a server API required technical knowledge of how to use a Flask, PostgreSQL, SQLAlchemy and marshmallow tech stack as well as the ability to troubleshoot errors in a pragmatic way. In addition, a key challenge of creating a successful API is designing the database in a considered way. With each challenge, I was able to overcome the problem with research and patience.

## Q6. With reference to one of your own projects, evaluate how effective your knowledge and skills were for this project, and suggest changes or improvements for future projects of a similar nature /6

One significant project I recently completed was creating a CLI application using Python. The application works by presenting the user with a string describing a mysterys Pokemon trading card. After receiving a hint, the user can guess the card or receive one or two more hints before guessing it. The user's guess is evaluated, with a simple validator that checks for typos to give the user a second chance, and the player receives points or the chance to play again if they are right or wrong. After each correct answer the user's score is compared to the leaderboard and, if it is higher, they can save their score with a name. Within the game there is an easy and hard mode as well. When creating this app, I had one week to design and implement it and I used a rudimentary Agile methodology to complete the task in time. Reflecting upon the project, there are clear improvements I would make to my project management processes and skills for future tasks.

When designing the app, I used a Kanban board on Trello to document what tasks needed doing, which tasks I was prioritising and deadlines for these tasks. I initially broke the assignment down into a list of steps and ordered them based on a logical sequence with matching deadlines however, when submitting the assignment, there were features that I did not have time to implement. During the coding process, the scoring system proved a bottleneck and I was forced to drop a cosmetic feature and simplify the scoreboard to function more linearly. Reflecting upon the assignment, I now realise that I omitted key Agile methodology steps after the initial planning stages. For example, a celebrated element of Agile workflows is a frequent stand-up meeting to discuss what's working, what's difficult and whether tasks should be reprioritised (Fernandez & Fernandez, 2008). Because I was working solo, I did not engage in this practice properly which meant I was not adjusting task deadlines to match my success or dificulties in different parts of the project. There were multiple instances where I labored through a task, such as implementing the scoreboard, with little success because I had scheduled it to be completed by a certain day, rather than reconsidering whether I could approach it after an easier task. Similarly, I left my documentation to the final day rather than working on it alongside the code's development. This was a particular mistake because documenting the task's progress and features would inherently prompted me to evaluate and emphasise the strongest features and highlight which elements were less important to complete early. I have since found much more success in other projects by actively evaluating the prior day's work each morning. This has made me feel more comfortable switching timelines on the fly and maximising my efficiency.

In regards to technical skills, this project highlighted my need to improve at writing and maintaining tests. Within the project, a JSON object is parsed to select a random object. The returned object would be largely consistent, but some data instances contained or lacked additional properties due to differing card formats. When ingesting the data to the project, I did not account for these types of issues but they quickly arose by throwing key errors. To handle them, I attempted to write automated tests to select and manipulate the JSON data but I found this task time-consuming and challenging. Again, I attempted to work through these challenges without reflecting upon whether this was good practice. This decision, ultimately, slowed down my workflow and held up my progress across days until I finally decided to abandon the automatic tests. These challenges emphasised two learning points for me. Firstly, it became clear that I need to improve my test writing and maintenance skills. Automated testing requires a firm technical and conceptual understanding of data types which I did not have at the time. To account for knowledge gaps such as these, I have since planned for and incorporated additional research time into learning the packages I am using in a project including testing options. Secondly, I have since defaulted to simpler, more stable, manual tests as a safety net to ensure my projects are functioning as expected. From a project management perspective, it was a poor decision to try and become proficient at a new technology whilst under time pressure and I have since planned fallbacks earlier. I also now recognise the importance of stable tests, even if they are simplified and not optimised.

The CLI app project I completed highlighted errors in my project management skills under time pressure. The task emphasised the need to use true Agile techniques to solve challenges and meet deadlines effectively. Fortunately, I have since been able to adapt my planning skills and refine my workflows.

### References

Fernandez, D. J. and Fernandez, J. D. (2008) ‘Agile Project Management —Agilism versus Traditional Approaches’, Journal of Computer Information Systems, 49(2), pp. 10–17. DOI: 10.1080/08874417.2009.11646044.

## Q7. Explain control flow, using an example from the JavaScript programming language /6

When JavaScript code is executed, it is typically interpreted line-by-line, in sequential order. This order can be altered by using control flow statements which make particular lines execute multiple times or be skipped based on certain conditions (MDN Web Docs, 2024a). In JavaScript, the ```if```, ```if else```, ```switch```, ```ternary operator``` and ```for loops``` are all techniques that can alter the order that lines are executed (MDN Web Docs, 2024b).

The ```if``` statement evaluates whether a condition is true and, if so, executes a designated code block before continuing the script. ```if else``` is an alternative method that can be used to evaluate multiple possible conditions and provide a default response if none of the conditions are evaluated as true. ```if``` and ```if else``` statements require the use of operators that return true or false. In JavaScript, a function that returns ```false```, ```undefined```, ```null```, ```0```, ```NaN```, ```""```, or a variable assigned one of these values, is considered falsy and will cause a particular ```if``` condition, checking for a truthy value, to not execute (MDN Web Docs, 2023a). Conditions can also be checked for loose quality or strict equality. Strict equality compares two values to check if they are both the same data type and have the exact same values whilst loose equality will complete an automatic type conversion to see if the values are the same when formatted in the same data type.

Below is an example of control flow using ```if``` statements:

``` JavaScript
function eval () {
var evaluation = ""
// Initialises 'evaluation' variable
var answer = "true"
// Initialises 'answer' variable and assigns it a string "true" value
if (evaluation) {
    return
// Checks if 'evaluation' is truthy
}
else if (answer === true) {
    evaluation = "Truly true"
    return
// Checks if 'answer' is strictly equal to the 'true' boolean value
}
else if (answer) {
    evaluation = "Sort of true"
    return
// Checks if 'answer' is truthy
}
else {
    evaluation = "Not, in any way, true"
    return
// Executes if none of the above if statements execute 
}
console.log(evaluation)
// Console shows:
// "Sort of true"
}

eval()

```

```eval``` first initialises the variables ```evaluation``` and ```answer``` and then begins assessing the ```if``` statements. The first ```if``` statement checks if ```evaluation``` is a truthy value which, because it is a blank string, a falsey value, it will not execute. The second ```if``` statement checks if ```answer``` is a boolean value equaling ```true```, however, it will not execute because answer is a string rather than a boolean meaning the values are not strictly equal. The third ```if``` statement checks if ```answer``` is any truthy value, not one of ```false```, ```undefined```, ```null```, ```0```, ```NaN``` or ```""```. Because the variable holds a truthy value, it evaluates to true, the linked code block executes and ```evaluation``` is set to a value of "Sort of true". The following else statement is skipped and the rest of the function executes so that the console displays "Sort of true". The else statement would execute if none of the other ```if``` statements were true but, in this example is not neccessary and does not execute.

Another control flow tool is the ```switch``` statement which describes the different possible conditions a variable could fulfill and executes the matching code block or, if no described cases match, a ```default``` code block executes. Otherwise, the ```ternary operator``` checks for a condition and executes a "true" code block or a "false" code block depending on what the condition evaluates to.

```Javascript
let x = 10
// Initialises variable 'x' with a value of 10
x > 9 ? console.log("x is greater than 9") : console.log("x is less than 9")
// A ternary operator, evaluates if 'x > 9' is truthy and executes the corresponding code
// Console shows:
// x is greater than 9
```

Loops are an alternative to conditional statements that can be used to control flow and execute code deviating from line-by-line sequencing. Specifically, JavaScript has various ```for``` loops as well as ```while``` loops. ```for``` loops repeat a block of code until it evaluates to false such as the ```for...in``` and ```for...of``` loops which iterate through each value in an iterable and allow the user to access the iteration indexes or data respectively. ```while``` statements similarly loop a block of code until a condition evaluates to false. ```while``` loops are particularly useful for looping an unknown number of times such as requesting a user input until a suitable value is provided. Similarly, ```do...while``` loops execute a block of code before evaluating a condition, stopping when the condition evaluates as falsey (MDN Web Docs, 2023b).

For example:

``` JavaScript
let counter = 0;
do {
    counter += 2;
    console.log(counter)
} while (counter != 10)
```

In this example, ```counter``` is initialised as 0. The ```do``` loop block adds 2 to ```counter``` each cycle and prints the updated value before the loop evaluates whether counter does not equal 10. The ```do``` block will thus loop 5 times until ```counter``` equals 10 then exit the loop and continue the script.

### References

MDN Web Docs (2024a) _[Control flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2024b) _[Control flow and error handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2023a) _[Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2023b) _[Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#do...while_statement)_, MDN Docs Glossary website, accessed 29 July 2024.

## Q8. Explain type coercion, using examples from the JavaScript programming language /6

Type coercion in JavaScript occurs when a value is implicitly converted from one data type to another automatically (MDN Web Docs, 2024a). This is different from conversions or generations that are explicitly declared such as the ```String()``` or ```Number()``` constructors. There are a variety of circumstances in which JavaScript will automatically change a data type when completing a process. The loose equality operator ```==``` will convert strings and booleans to numbers to compare their values against numbers (Samoshkin, 2018).

For example:

``` JavaScript
10 == "10"
// Returns true, "10" is converted into 10 for the comparison
'true' == true
// Returns false, true is converted to 1 whilst 'true' is converted to NaN
```

Similarly, using ```+``` will implicitly convert a number to a string when a number value is added to a string.

For example:

``` JavaScript
10 + '10'
// Returns '1010'
```

Other number-based operators including ```<```, ```>=```, ```-```, ```*```, ```%``` and the bitwise operators, which consider binary values, coerce a string value to a number.

For example:

```JavaScript
"10" - 5
// Returns 5
"15" / 3
// Returns 5
"5" ^ "3"
// Bitwise "XOR" operator
// JS implicitly converts "5" to 101 and converts "3" to 11
// 101 XOR 011 = 110
// Returns 7  
```

JavaScript will also cooerce values to booleans for evaluations such as ```if``` statements. Notably, logical operators use boolean coercion to calculate a result but return the original values (Samoshkin, 2018).

For example:

```JavaScript
Boolean("and")
// Returns true
"and" && 15
// Returns 15
"and" && false
// Statement evaluates to falsy
// Returns false
"and" && NaN
// NaN evaluates to falsy
// Returns NaN

```

In the above example, ```"and"``` evaluates to true when it is explicitly converted because it is not one of the values ```false```, ```undefined```, ```null```, ```0```, ```NaN``` or ```""```. The ```&&``` operator checks if the compared values are truthy by converting them implicitly to booleans. If both values are truthy, the last truthy value is returned. If one of the values is falsy, that value is returned, hence why ```false``` and ```NaN``` are returned in the last two comparisons (MDN Web Docs, 2024b).

When non-primitive values such as objects are compared or evaluated, they are coerced to a primitive data type (Samoshkin, 2018). If an array is compared using a loose equality operator or added to a string using ```+```, the contents of an array will be converted to a string for the process. Similarly, an object will be converted to a string as well. If a mathmetical operator is used, arrays and objects will be converted into numbers, resulting in a ```NaN``` value.

For example:

```JavaScript
["hello"] + "hello"
// Returns "hellohello"
["hello"] == "hello"
// Returns true
["hello"] === "hello"
// Returns false
{hello: "hello"} + "hello"
// Returns "[object Object]hello"
{"hello"} - 1
// Returns NaN
```

JavaScript type coercion is a useful feature which can reduce code by eliminating the need to explicitly convert of variable data types. However, the default coercion behaviour of some data types can lead to unexpected results if not accounted for.

### References

Alexey Samoshkin (2018) _[JavaScript type coercion explained](https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/)_, freeCodeCamp website, accessed 30 July 2024.

MDN Web Docs (2024a) _[Type coercion](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion)_, MDN Docs Glossary website, accessed 30 July 2024.

MDN Web Docs (2024b) _[Logical AND (&&)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)_, MDN Docs Glossary website, accessed 30 July 2024.

## Q9. Explain data types, using examples from the JavaScript programming language /6

In JavaScript, there are seven primitive data types: ```number```, ```string```, ```boolean```, ```null```, ```undefined```, ```symbol``` and ```bigInt```. Variables can be assigned values that are one of these data types or an object such as a function or an array. JavaScript is a dynamically typed language which allows any variable to be assigned any data type and allows variables to be changed at any time to a different data type (MDN Web Docs, 2024a). The primitive data types have a variety of methods and behaviours inherently linked to them that assist in their usage within JavaScript syntax. A variable's data type can be checked using the built-in ```typeof()``` operator.

For example:

```JavaScript
let example = "cat"
typeof(example)
// Returns 'string' 
example = 1
typeof(example)
// Returns 'number'
```

Primitive data types are immutable meaning that a primitive value cannot be altered. For example, the ```number``` ```4``` cannot be altered within JavaScript to equal ```5``` or the second index of a declared string "rabbits" cannot be changed by targeting its index and assigning it a new value. However, objects are mutable and can store nested values that are primitively typed to be changed later. Objects can be considered as a collection of primitive value properties. In addition, primitive data types have methods associated with them that can assist in modifying objects or variables that store them.

```JavaScript
let tree = "oak"
tree[0] = "bark"
console.log(tree)
// Console shows:
// 'oak' 
// The string value is immutable
tree = "bark"
// The tree variable can be changed however
console.log(tree)
// Console shows 'bark'

let forest = {trees: "oak"}
// Assigns forest an object value with a key-pair "trees: "oak""
console.log(forest.trees)
// Console shows:
/// 'oak'
forest.trees = "pine"
// Object attribute trees is reassigned
console.log(forest.trees)
// Console shows "pine"
// Objects are mutable
forest.trees.concat(" and redgums") 
// Uses the string data type's inbuilt concat() method
console.log(forest.trees)
// "oak and redgums"
```

There are particular quirks to some of the data types and their associated values. Notably, ```null``` and ```undefined``` behave similarly when used in operations but are intended for different uses (MDN Web Docs, 2024a). ```null``` is used to represent the absence of an object whereas ```undefined``` is the lack of a value. Similarly, ```NaN``` is a value that represents something that is not a number but the value itself is classified within the ```number``` data type. These qualities should be noted when using the loose equality operator.

For example:

```JavaScript
let example1 = null
typeof(example1)
// Returns 'object'
let example2 = undefined
typeof(example2)
// Returns 'undefined'
let example3 = NaN
typeof(example3)
// Returns 'number'
if (typeof(example3) == 'number') { console.log("It's a number")}
// Console shows:
// "It's a number"
```

```BitInt``` is a primitive data type used for handling numbers larger than the maximum value or smaller than the minimum value of the JavaScript ```number``` data type. For example, if a value is added to the maximum ```number``` value, JavaScript will round unpredictably. ```BitInt``` does not have this problem, however, and will add accurately. ```BitInt``` values can be generated dynamically by adding ```n``` to the end of a number value when it is being assigned or by using the ```BigInt()``` constructor (MDN Web Docs, 2024b). ```symbol``` is a data type used to create constants that are definitively unique. Symbols can be passed as a key value to an object ensuring the symbol value will not clash with a property assigned later and, when generating the symbol, a symbol can hold additional data also. Symbols are not enumerable meaning that they will not be considered when an object is iterated. This quality can be used to keep particular data more private, although the data can still be accessed in other ways (Playcode.io, n.d.). The ```BitInt``` and ```symbol`` data types allow for unique functionality.

For example:

``` JavaScript
let maxNumber = Number.MAX_SAFE_INTEGER
// Initialises maxNumber with the largest value: 
// 9007199254740991
maxNumber + 2
// 9007199254740992
// Value is incorrectly added

let bigIntMax = BigInt(Number.MAX_SAFE_INTEGER)
// 9007199254740991n
bigIntMax + 2n
// 9007199254740993n
// Must add using BitInt notation
// Successfully adds 2n

const house = Symbol("bricks")
let constructionPlans = {[house]: "pink"}
// Symbol can be passed as an object key
constructionPlans.house = "blue"
// Creates new constructionPlans attribute 'house'
// Does not overwrite symbol value 'house'
console.log(constructionPlans)
// Console shows:
// { house: 'blue', [Symbol(bricks)]: 'pink' }
console.log(Object.keys(constructionPlans))
// Console shows:
// ['house']
// Only the string value is shown, symbol attribute is not shown
console.log(constructionPlans[house])
// Console shows:
// pink
console.log(house)
// Console shows:
// Symbol(bricks)
// Symbol can be accessed out of the context of an object assigned with it as a key

```

The various primitive data types of JavaScript are used to handle different values and associate them with appropriate properties. For this reason, they all have specific methods built-in to manipulate them. Each primitive data type triggers default behaviour within the JavaScript language and these traits can be leveraged in objects to create advanced, descriptive data sets.

### References

GeeksforGeeks (2024) _[JavaScript type coercion explained](https://www.geeksforgeeks.org/javascript-data-types/)_, GeeksforGeeks website, accessed 30 July 2024.

MDN Web Docs (2024a) _[JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)_, MDN Web Docs website, accessed 30 July 2024.

MDN Web Docs (2024b) _[BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt)_, MDN Web Docs website, accessed 30 July 2024.

Playcode.io (n.d.) _[JavaScript Symbols](https://playcode.io/javascript/symbols)_, Playcode Website website, accessed 31 July 2024.

## Q10. Explain how arrays can be manipulated in JavaScript, using examples from the JavaScript programming language /6

Arrays are mutable objects used to store a collection of data in a single collection. Arrays are resizeable and can contain a mix of data types including nested objects. Arrays have an inherent length property which is related to the number of entries within the array. Values within an array are zero-indexed with a numbered key which can be used to target them. Notably, arrays can be explicitly altered to have their length extended and a value can be assigned to a non-sequential index. When this occurs, the indexes between the two values that are assigned values hold an ```undefined``` value.

For example:

```JavaScript
let colours = ['blue', 'pink', 'red']
console.log(colours)
// Console shows:
// [ 'blue', 'pink', 'red' ]
colours.length
// 3
colours[2]
// 'red'
colours[6] = 'green'
console.log(colours)
// Console shows:
// [ 'blue', 'pink', 'red', <3 empty items>, 'green' ]
colours.length
// 7
```

There are a variety of data type methods that can be used to alter arrays. These methods can be split into two categories: mutating methods and copying methods. Mutating methods alter the array that the method is applied to whilst copying methods create and return a shallow copy of the array with specified alterations. Mutating methods often have a non-mutating counterpart such as ```pop()```, a mutating method, and ```slice(0, -1)```, a non-mutating alternative both being functions that return a value from an array (MDN Web Docs, 2024). Other methods are used to change the values in an array such as ```push()``` which adds a value to the end of an array, ```reverse()``` which reverses the index order of an array and ```shift()``` which removes the first value of an array and returns it. Their non-altering alternatives are ```concat([x, arrayName])``` which mimics ```push()``` and returns a copy array of the given arguments with the x value as the first value(s), ```toReversed()``` which returns a reverse-ordered copy of an array and ```slice(1)``` which which returns a copy of the array with the values after the provided index.

For example:

```JavaScript
let colours = ["blue", "red", "green"]
// [ 'blue', 'red', 'green' ]
colours.slice(0, -1)
// [ 'blue', 'red' ]
colours
// [ 'blue', 'red', 'green' ]
// colours is unaltered by .slice()

colours.pop()
// 'green'
colours
// [ 'blue', 'red' ]
// colours was mutated by .pop()
```

Arrays also have a collection of iterative methods which consider all values in an array and parses each through a given callback function with different effects. Iterative methods are non-mutating. ```forEach()``` accepts a callback function and simply applies that function to all values in the array individually but does not return anything implicitly. ```filter()``` takes a callback function and returns a new array with only values that return a truthy value when passed to the provided function. ```map()``` applies a callback function to all values in an array and returns the results in a new array. ```sort()``` is an array method used to sort indexes of an array based on the criteria of a passed compare function. Notably, whilst ```sort()``` is similar to an iterative function, it mutates the array and sometimes invokes the callback function multiple times on a single index to sort the values meaning it is not a true iterative function.

For example:

``` JavaScript
colours = ["blue", "red", "green"]
colours.forEach((val) => {console.log(val)})
// Console shows:
// blue
// red
// green
colours.filter((val) => val[0] == "b")
// [ 'blue' ]
colours.map((val) => val + " and yellow")
// [ 'blue and yellow', 'red and yellow', 'green and yellow' ]
console.log(colours)
// Console shows:
// [ 'blue', 'red', 'green' ]
// colours was unaltered by .forEach(), .filter() and .map()
colours.sort((a, b) => a.length - b.length)
// [ 'red', 'blue', 'green' ]
// Callback function sorts by shortest length first
console.log(colours)
// Console shows:
// [ 'red', 'blue', 'green' ]
// colours array was mutated by .sort()
```

Arrays can be manipulated in various ways making them flexible tools for data storage. Arrays' iterative methods are particularly powerful for batch editing or altering according to sophisticated criteria. Essentially, arrays can be altered in mutative and non-mutative ways and there are always different techniques to achieve each type of alteration.

### References

MDN Web Docs (2024) _[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)_, MDN Web Docs website, accessed 31 July 2024.

## Q11. Explain how objects can be manipulated in JavaScript, using examples from the JavaScript programming language /6

Objects are used in JavaScript to store properties and assign values to them for reference or manipulation. Properties and their associated values create key-value pairs where the key value can be a name (a word without appostrophes), string, symbol or number datatype (MDN Web Docs, 2024). A property value can be a primitive data type or another object such as a function, an array or another nested object. A property that is a function is referred to as a method such as the functions accessible to each data type. Each object property can be accessed using dot notation or bracket notation, except for properties with spaces which must be accessed using bracket notation. By referring to an object's property key, it can typically be reassigned. If a property that has not been declared yet is assigned a value, a new property will be initialised with that value.

For example:

``` JavaScript
let identifier = "name"
let dog = {
    identifier: "Charles",
    // identifier is not wrapped in apostrophes
    "personality type": "friendly"
    // 'personality type' has a space and must be wrapped in apostrophes
}
console.log(dog)
// Console shows:
// { identifier: 'Charles', 'personality type': 'friendly' }
dog.identifier
// 'Charles'
dog['personality type']
// 'friendly
dog.enemy = "cats"
// dog.enemy is initialised with this line
console.log(dog)
// Console shows:
// { identifier: 'Charles', 'personality type': 'friendly', enemy: 'cats' }
```

Objects can be created by listing properties and values within the object initializer syntax ```{}```, using the ```Object.create()``` method or by using ```new ObjectName``` where ObjectName is a defined object constructor function. Defining an object constructor function allows a particular object structure to be reused as many times as required.

For example:

``` JavaScript
function Person(name, birthYear) {
    this.name = name,
    this.birthYear = birthYear,
    this.planet = "Earth"
    this.birthdaySong = function() {console.log("Happy birthday to me!")}
    // .birthdaySong() is initialised as a method of Person objects
}
let student1 = new Person("Kyle", 2000)
console.log(student1)
// Console shows:
// Person {
//  name: 'Kyle',
//  birthYear: 2000,
//  planet: 'Earth',
//  birthdaySong: [Function (anonymous)]
// }
student1.birthdaySong()
// Console shows:
// Happy birthday to me!
```

When an object constructor function contains a method like in the above example, the method is stored in each instance created using the constructor function. Alternatively, objects of the same type can share attributes without each instance containing them. Additional methods can be added this way by using the ```ObjectName.prototype``` syntax where ObjectName is a constructor name. The ```.constructor.name``` property of an instance returns the name of the constructor used to create it so that its prototype attributes can be changed.

Getter and setter methods can also be assigned to objects to obscure and abstract instance properties. These methods can be declared in a constructor function using the ```get``` and ```set``` keywords followed by a function that returns or alters an object property. Getters and setters can also be declared for a particular instance when it already exists by using the ```.defineProperties()``` function.

For example:

``` JavaScript
function Person(name) {
    this.name = name
}
let boy1 = new Person("Jeff")
let boy2 = new Person("Stu")
boy2.constructor.name
// 'Person'
Person.prototype.grade = 2
// Assigns grade property to all Person instances and sets it to value 2
console.log(boy1.grade)
// Console shows:
// 2
console.log(boy2.grade)
// Console shows:
// 2
Object.defineProperties(boy2, {
    getName: {
        get() {
            return this.name
        }
    },
    setName: {
        set(newName) {
            this.name = newName
        }
    }
})
// Assigns getter and setter functions for boy2
boy2.setName = "Charles"
// Calls boy2's name setter function
console.log(boy2.getName)
// Calls boy2's name getter function
// Console shows:
// 'Charles'
console.log(boy2.name)
// Alternative way to access boy2's name value
// Console shows:
// 'Charles'
```

Object properties can be iterated through for manipulation as well. The inbuilt ```Object.keys()``` returns all property key values that are enumerables which excludes values such as getter and setter functions as well as prototype properties. ```Object.getOwnPropertyNames()``` returns all key names including non-enumerable keys but excludes protype properties again. Otherwise, a ```for in``` loop can be used to iterate through an object and returns all emumerable properties including prototype properties but does not accesses getter or setter methods. Each property can then be used or manipulated in the associated loop code block.

For example:

``` JavaScript
// Using boy1 and boy2 as defined in the previous example block
Object.keys(boy2)
// [ 'name' ]
// Does not include .grade prototype property or getter or setter methods
Object.getOwnPropertyNames(boy2)
// [ 'name', 'getName', 'setName' ]
// Does not include prototype property
for (property in boy2) {console.log(property)}
// Console shows:
// name
// grade
// Iterates through properties but excludes getter and setter methods
for (property in boy2) {
    boy2[property] = "Freshman"
}
// Iterates through properties besides getter and setter methods and assigns them the string value "Freshman" in the code block for each loop
for (property in boy2) {console.log(boy2[property])}
// Console shows:
// Freshman
// Freshman
```

There are multiple, powerful ways to manipulate objects in JavaScript targeting individual instances or all instances creater using the same constructor. The different object methods have distinct use cases and can be chained creatively to alter stored data easily.

### References

MDN Web Docs (2024) _[Working with objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)_, MDN Web Docs website, accessed 31 July 2024.

## Q12. Explain how JSON can be manipulated in JavaScript, using examples from the JavaScript programming language /6

JSON (JavaScript Object Notation) is a text-based format designed for transporting data as a string that can be with converted to be interpreted as an object. Formatting data as a string means it can be handled by more applications, including apps built using different programming languages, making JSON files convenient for sharing information (MDN Web Docs, 2024b).

JSON can only handle particular JavaScript data types and has formatting rules that differ from typical JavaScript objects. JSON supports arrays, strings, booleans, the ```null``` value and nested objects that contain these values. However, strings must be contained in double-quotes, numbers cannot begin with 0 and the ```NaN``` and ```Infinity``` number values cannot be used. This also means that ```BigInt```, ```undefined``` and ```Symbol``` values cannot be stored in their natural formats, nor can functions.

JavaScript has a ```JSON``` global object with key methods to utilise and generate JSON files. ```JSON.parse()``` accepts a JSON string and returns a JavaScript object populated with the string's data. Inversely, ```JSON.stringify()``` converts a JavaScript object to a JSON string.

For example:

```Javascript
let cat = {'name': "Mr Wobbles"}
cat = JSON.stringify(cat)
console.log(cat)
// Console shows:
// '{"name":"Mr Wobbles"}'
// Note - "name" rather than 'name'
JSON.parse(cat)
// Returns: { name: 'Mr Wobbles' }
// Note - name rather than "name" or 'name'
let house = {occupants: null}
JSON.stringify(house)
// Returns: '{"occupants":null}'
let mrSquirell = {aspirations: undefined}
JSON.stringify(mrSquirell)
// Returns: '{}'
// JSON does not accept the undefined value
```

Once a JSON string has been converted to a JavaScript object, it can be manipulated in any way that an object can. By extension, any value in the object can be accessed using string or dot notation.

For example:

``` Javascript
cat = {name: "Trevor", hobbies: ["sleeping", {"martial arts": ["karate", "judo"]}]}
cat = JSON.stringify(cat)
// Converting cat to JSON string:
// '{"name":"Trevor","hobbies":["sleeping",{"martial arts":["karate","judo"]}]}'
cat = JSON.parse(cat)
// Converting cat from JSON string to JS object:
cat.hobbies[1]['martial arts'][0]
// 'karate'
// cat object can be manipulated like a typical JS object
```

Whilst JSON does not accept particular data types, developers can work around this by storing data in different formats for later conversion. For example, a phone number cannot be stored as a number value in JavaScript objects or JSON alike because it begins with a 0 and contains too many digits. Instead, a phone number could be stored as a string. In a unique case, ```BigInt``` values cannot be converted to JSON strings using ```JSON.stringify()``` and will raise an error but this can be worked around by writing a custom prototype function to handle the data type's automatic conversion (MDN Web Docs, 2024a and MDN Web Docs, 2024c).

The ```JSON.stringify()``` method provides another choice for manipulating JSON objects via its second parameter: ```replacer```. The ```replacer``` parameter can be an array containing designated key values, listed as strings, to contain in the returned JSON string, or it can be a function that returns any key or value to include.

For example:

```JavaScript
let bigObj = {value: 111222333444n}
bigObj
// { value: 111222333444n }
JSON.stringify(bigObj)
// Throws:
// Uncaught TypeError: Do not know how to serialize a BigInt
BigInt.prototype.toJSON = function () { return this.toString() }
// Defines a process for BigInt objects to be converted to the string data type when a BigInt value is parsed by the JSON.stringify() method
JSON.stringify(bigObj)
// Returns: 
// '{"value":"111222333444"}'

let numbers = {a: 2, b: 3}
JSON.stringify(example, (key, value) => {if (value != '2') {return value}})
// Returns:
// '{"b":3}'
// replacer parameter is passed a function that returns keys without a value of 2
JSON.stringify(example, ['b'])
// Returns:
// '{"b":3}'
// replacer parameter is set to key values of b, generated JSON string only contains key-pair value "b":3
```

Another useful way to utilise and manipulate JSON within JavaScript is to save and access it using a browser's ```sessionStorage``` or ```localStorage```. ```sessionStorage``` is an amount of memory in a browser that can hold data until the session ends whilst ```localStorage``` is an amount of memory that perseveres until a user deletes it. Both of these objects accept string data and can be accessed and altered in JavaScript scripts, making them perfect for caching JSON when creating web applications for fast loading (W3 Schools, 2024).

For example:

```JavaScript
let usefulData = {content: "Don't forget to brush your teeth each night"}
let usefulJSON = JSON.stringify(usefulData)
localStorage.setItem("storedExample", usefulJSON)
// Saves the usefulJSON JSON string as "storedExample" in brower's local storage

let retrievedString = localStorage.getItem("storedExample");
let retrievedJSON = JSON.parse(restievedString);
// The "storedExample" JSON string is retrieved from local storage and converted to a JSON object for later manipulation, mirroring the original usefulData object
```

JSON is a popular and convenient format to send and receive data to be handled by different coding languages. Within JavaScript, the ```JSON``` global object and its methods provide convenient conversion tools that allow users to handle JSON formatting easily. These methods have customisable options that should be considered to handle differently-typed data. In addition, JSON formatting is particularly useful for caching data in browsers when creating web applications.

### References

MDN Web Docs (2024a) _[JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)_, MDN Web Docs website, accessed 1 August 2024.

MDN Web Docs (2024b) _[Working with JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)_, MDN Web Docs website, accessed 31 July 2024.

MDN Web Docs (2024c) _[JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)_, MDN Web Docs website, accessed 31 July 2024.

W3 Schools (2024) _[JSON.stringify()](https://www.w3schools.com/js/js_json_stringify.asp)_, W3 Schools website, accessed 31 July 2024.
