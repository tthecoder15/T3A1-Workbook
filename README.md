# Tom Tutone T3A1-Workbook

- Due 18.8.24 (3 weeks)
- [https://ait.instructure.com/courses/5200/assignments/56761]

Sources:

- consider if people in the industry would trust it e.g./ AWS data

## Q1. Provide an overview and description of a standard source control process for a large project /6

When working on a large-scale project, backing up the project, tracking its changes and making it easily accessible to team members is a fundamental consideration. Using source control software, such as Git and Mecurial, is the industry standard for programmers and allows teams to share and work on projects concurrently. These tools monitor changes in a project's files, integrate them into a defined "main" collection and provide functions to update or regress files collection so that team members can access the project's most current stable files.

In a large-scale project, it is mandatory that team members agree upon a protocol for saving changes to the project's files. This includes designating standardised naming and commenting conventions, rules for the scope of each change and how the team will manage conflicting opinions and edits. In the context of using Git, a team must decide where the project will be hosted (typically on a remote repository using Gtihub), how each commit message will be structured, protocol for updating code that multiple users concurrently depend on (such as a parent module), and designating the frequency of when changes should be merged to the main branch.

Notably, there are two distinct project repository structures which teams can choose from when initialising their project: the shared repository model or the fork and pull model (Github, 2024). The fork and pull model is typically utilised in open-sourced projects with mass contributors and requires individuals to fork a base repository which creates an independent copy repository of the entire project. These forked repositories are then advanced as required before the individual submits a pull request to merge their proposed changes to the main repository for an administrator to review and approves or reject. Alternatively, the shared repository model is more typically used in smaller teams and consists of team members all sharing access to a single remote repository. Linked to the main respository, team members create distinct branches, which segregate and track changes from the main repository branch, to focus on particular feature implementations or bug fixes. When the branch is complete, team members can either submit a pull request for the team to review the changes or simply merge the changes if they are confident that the changes are appropriate. The two strategies are broadly similar but require different levels of filtering and trust. In a project where the team is in constant communication, it is likely appropriate to use a shared repository.

Working on code in branches has distinct advantages in small teams as well. Sharing access to the same repository, team members can initialise as many branches as neccessary and host segregated development streams in a mutually accessible location. This allows team members to easily switch between branches as required and assist each other with challenges. Once a branch is finished, it can be merged to the main branch with a single commit message which clearly indentifies when it was integrated and its purpose. Typically, branches are squashed before they are committed to the main branch so that their commit timeline is not saved to the main branch and does not muddy the project's timeline (Ernst, 2024b).

There are various considerations when using a shared repository and branch based development model however. When working on a branch, team members must make sure not to edit code that other branches depend on without consulting the team. Simple reconfiguration of a shared file can easily cause a branch to deviate from parallel branches which raise multiple time-consuming merge conflicts when each branch is ready to be merged (Ernst, 2024a). If a shared dependency must be updated, it should be edited in its own distinct branch and merged with the main branch as soon as possible so that any unfinished branches can sync these changes and continue working. For the same reason, it is crucial that in-progress branches sync changes from the main branch daily or more frequently depending on the project's update frequency. Finally, when commencing a branch, such as a bug fix patch, it is great practice to generate tests before work begins. Creating tests which initially fail but pass when the branch is complete gradually ensures the project's robustness and builds the project's collection of tests. It also assists in focusing the branch ensuring that its intented impact can be clearly tracked in the tests and these features can be preserved in future branches easily (Ernst, 2024b).

### References

Ernst, M. (2024a) _[How to create and review a GitHub pull request](https://homes.cs.washington.edu/~mernst/advice/github-pull-request.html)_, Computer Science & Engineering University of Washington Community Website, accessed 27 July 2024.

Ernst, M. (2024b) _[Version control concepts and best practices](https://homes.cs.washington.edu/~mernst/advice/version-control.html)_, Computer Science & Engineering University of Washington Community Website, accessed 22 July 2024.

Github (2024) _[About collaborative development models](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models)_, Github Docs Website, accessed 7 August 2024.

## Q2. What are the most important aspects of quality software? /6

Designing software requires a thorough understanding of the contexts within which the product needs to function. The design process typically begins with considering one or more use cases for the software, the challenges that users face in these scenarios and planning a solution suitable for these conditions. However, developing quality software requires developers to consider circumstances beyond these baseline applications and account for how the software will work over in varied use cases over an extended period of time. Boehm's (1976) software quality model and the ISO's (International Organization for Standardization) 25010 publication (ISO 25000, 2022) provide frameworks for describing and designing quality software.

Both Boehm and the ISO describe the importance of quality software being portable. Portablility refers to a software's ability to function on varied machines with varied hardware specifications. When designing, developers must account for the environments that they are developing in and how they differ from the their end users'. Software provides no use to potential users if their computers or internet connections cannot handle an application. To account for these differences, developers should test their software on a variety of devices and, broadly, must consider their target users and the tools they use and have access to.

Boehm acknowledges that portability often works in opposition to efficiency as a program can be optimised for a particular system only to function worse on other systems yet, this tradeoff must be balanced carefully to create quality software (Boehm, 1976). Efficiency in quality software describes utilising the available resources for that software to run. This can refer to processing power but also refers to other resources which aid the software's function. A common example of an efficiency tradeoff is designing web applications for desktops versus mobiles. Efficiency considerations in this context refer not only to the devices' processing power but also their efficiency in utilising screen space to communicate information. Quality software considers the tools available in the different contexts that the software will be used in and maximises them.

Scalability is an integral characteristic of quality software that is complimented by flexibility (ISO 25000, 2022). Developers need to consider how their tools can and will be implemented into workflows and account for varying scales of data that the software needs to handle. Quality software must scale to users' needs and handle large deployments and minimal deployments gracefully.

Both the ISO and Boehm identify interaction capability and the ease of use of software as a key quality trait (ISO 25000, 2022 & Boehm, 1976). The ISO's description extends on ease of use and and describes that a quality software must be reasonable to learn as well. Usability is a fundamental concern of software design as a tool fundamentally does not work if individuals cannot use it. Learnability further accentuates the need for developers to understand user contexts and the different backgrounds and understandings of individuals who will use their software. Understanding a user base allows developers to tune the interface or functionality of software so it can be used and learnt appropriately.

One point of difference between the two models is that the ISO 25010 describes security as a neccessity of quality software (ISO 25000, 2022) whereas Boehm's does not. This can likely be attributed to an increased emphasis on data privacy in the internet age. When designing software, developers must consider the risks that the tool generates for users including system vulnerabilities and the storage of their data. It is essential that users are guaranteed confidentiality when using a software as privacy is as much of a resource to consider for users as time and financial costs. Security also encompasses data integrity and confirmation that saved data is consistent and reliable. Software must implement reliable data storage and access to be considered effective.

Finally, both models value maintainability and the ease that software can be updated. At a coding level, maintainability means producing code that is clearly modularised and formatted so that bugs can be fixed cleanly and without large overhauls. At the user level, maintainability requires users to be able to install updates easily or update their own processes using the app logically.

Creating quality software requires clear planning and considerate implementation so that tools function as intended in varied, future-proofed contexts. Developers must strive to create portable, efficient, flexible, useable, maintainable and secure software and, to do so, must consider the different contexts that the software will be used in.

### References

ISO 25000 (2022) _[ISO/IEC 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)_, ISO 25000 website, accessed 27 July 2024.

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

## Q3. Outline a standard high level structure for a MERN stack application and explain the components /6

The MERN stack is a popular collection of technologies which can be used to create a dynamic web application. MERN stands for MongoDB, Express, React JS and Node.js, four tools which all use JavaScript syntax and complimentarily fill the roles required to generate webpages, handle interactions with them and store and serve their data.

React JS is the front-end component of the MERN stack and a web framework used to create fast-loading, responsive webpages. React uses JSX, a JavaScript syntax extension which hybridises JS with HTML so that users can easily describe HTML webpages. The framework uses component-based design where the different elements of a HTML page are modularised to be reused, like building blocks, and pieced together to create webpage layouts. React is particularly useful for creating responsive webpages which can track state. Using the ```UseState``` hook, developers are able to use getter and setter functions that track state changes based on user interaction such as clicking on a button. Combined with the ```UseEffect``` hook, changes in state can trigger updates in the webpage layout and display differing data. React is able to rapidly update the display due to its underlying virtual DOM technologies. The virtual DOM is a recreation of the browser DOM (Document Object Model) which describes the elements of a loaded webpage as a JS object. React creates a virtual DOM as the page is initially rendered and creates a new copy whenever the webpage is to be changed based on an updated state. The two iterations are compared to identify where there are differences and React compartmentally updates only the neccessary elements, preventing an entire page reload. These systems allows React to display display dynamic pages efficiently.

Express is a Node package used to create APIs and handle routing configuration, facilitating the connection and interaction between a web application's front-end and back-end. Using Express, a developer is able to define routers which describe how a webpage or API will responds to different HTTP request types at defined URIs. Express allows for the use of middleware to handle requests and manipulate any data they are sent with or lack. A typical middleware used in Express is the ```express.json()``` function which converts a request's body into JSON, so that it can be manipulated in the applications back-end. Express is particularly effective for developers because its syntax and router objects allow for DRY, reuseable routing elements which helps speed up development (GeeksforGeeks, 2023).

Node.js is a runtime environment which allows the Express scripting of a web application to run. Express is built using JavaScript, a language which can typically only be executed by web browsers. Node provides an alternative environment to run JS scripts, including Express APIs, so that the webpage and server-side logic can be executed concurrently and written in the same language. In addition, Node.js is bolstered by a large developmental community that generates packages to extend server-side capabilities.

Finally, MongoDB is the database layer of the MERN stack. MongoDB is a NoSQL database that can be interacted with using JavaScript code. MongoDB databases can be run locally or using MongoDB Inc.'s cloud services. MongoDB is particularly valued due to its flexible data structures which allow developers to define, store and query instances without the strict formatting required by SQL databases (GeeksforGeeks, 2023). In the MERN stack, MongoDB is used to store the data that populates a page and to record users' posted data.

Considering the MERN stack in totality, the React layer provides the tools to create webpages for users to interact with, the Express layer handles the user's interactions by requesting and handling the appropriate resources, Node.js allows Express to execute and offers additional capabilities and MongoDB stores data for the user to interact with. Besides effective performance, the key element that makes the MERN stack popular is its consistent use of JavaScript eliminating script conversions and allowing developers to easily learn the software syntax (MongoDB, n.d. & Kadam et. al., 2023).

### References

GeeksforGeeks (2023) _[MERN Stack](https://www.geeksforgeeks.org/mern-stack/)_, GeeksforGeeks website, accessed 27 July 2024.

GeeksforGeeks (2024) _[ReactJS Virtual DOM](https://www.geeksforgeeks.org/reactjs-virtual-dom/)_, GeeksforGeeks website, accessed 28 July 2024.

Kadam, Y., Goplani, A, Mattoo, S., Gupta, S. K., Amrutkar, D., Dhanke, J. (2023). 'Introduction to MERN Stack & Comparison with Previous Technologies', _European Chemical Bulletin_ 12(4), pp. 14382-14386. DOI: 10.48047/ecb/2023.12.si4.1300.

MongoDB (n.d.) _[Mern Stack Explained](https://www.mongodb.com/resources/languages/mern-stack-tutorial)_, MongoDB website, accessed 27 July 2024.

## Q4. A team is about to engage in a project, developing a website for a small business. What knowledge and skills would they need in order to develop the project? /6

- technical, soft skills too
- Effectively describes a range of skills and knowledge required by IT workers to complete a quality web development project

To design and create a website for a business, a development team needs a specific understanding of the business' requirements. Considering Boehm's (1976) model for quality software, a website should be designed considering the contexts that it will be engaged with. Firstly, the development team must understand what functionality the website needs to have to aid the business. By extension, the team needs to understand the typical website user so that the website can be designed to suit their hardware and interface requirements. For example, a general practice business will likely need to feature contact information, service offerings and information about the clinic's doctors. In addition, the business may require additional functionality such as an online booking system implemented with dynamic webpages and form submissions, or, the company may want to keep these systems on site for simplicity. By extension, depending on the clinic's customers or location, the typical user may have limited website literacy and may require a simpler user interface, or the business may want a sophisticated and sleek interface to attract a different customer type. These requirements should be considered to ensure the website fulfills Boehm's recommendations for usability and portability across devices. The team also needs to understand the company's maintenance plans following the websites creation to ensure that it is appropriately future-proofed. If the business does not plan on updating the site frequently, the team needs to ensure the layout and functionality is robust as web technologies advance, a consideration that would shape the entire design process. It is key that a team understands the contexts that their website will be used in to successfully design and implement it.

There are distinct technical skills a development team requires to create a website using a particular technology stack. In many contexts, the MERN stack provides all of the tools required to make an approptiate small business' website. To use the MERN stack, the design team must know how to use JavaScript as well as the specific syntax of MongoDB, Express, React JS and how to configure and use Node.js. Besides these defined skills, there are complementary understandings the team must apply to use these tools. When designing the back-end and routing for the website, the team members must implement RESTful practices so that the website functions in a stable and maintainable way. This includes defining routes that are logical and delivering data in a consistent way. Notably, creating a RESTful API requires a reliable database and consistant storage structure. Because MongoDB is a NoSQL database, the development team has full control over how instances are recorded which allows for quick initialisation but can also permit messy formatting. For these reasons, the development team must have a technical knowledge of the MERN stack but also a conceptual knowledge of how to design the website's database and backend to be consistent and maintainable.

In addition to project understanding and technical knowledge, the team members require project management and planning skills. In many contemporary projects, Agile methodologies are used to set goals, manage deadlines and respond to project challenges as they arise. Adopting Agile techniques including using Kanban boards to visually communicate progress and prioritise tasks, scheduling daily stand-ups and feedback sessions and dedicating resources based on team agreement are all beneficial practices that will bolster a teams productivity (Moe, et. all, 2014). Whilst a development team does not need to know Agile project management specifically, the team requires a structured division of work to ensure all tasks can be completed on schedule. In a technical context, project management requires a team to develop and enforce source control habits. Using Git or an alternative software, team members must know how to back-up and share their work and how to archive their progress with succinct commit messages and pull requests.

When creating a website, a development team requires technical and conceptual skills to handle the design, programming and project management elements of the task.

### References

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

Brede Moe, N., Dingsøyr, T., Dyba, T. (2014) 'Agile Project Management', in Ruhe, G., Wohlin, C. (eds.) _Software Project Management in a Changing World_. Berlin: Springer-Verlag, pp. 277-300.

## Q5. With reference to one of your own projects, discuss what knowledge or skills were required to complete your project, and to overcome challenges /6

- assignments, side projects
- challenges you overcame extrapolated
- Effectively describes a range of skills and knowledge used to complete a project

Designing and creating a web server API using Flask and Postgres was a project that required distinct technical and conceptual skills. The project featured these tools as well as SQLAlchemy and marshmallow and was designed as parent-teacher communication tool that allowed each side to make comments about students, parents to enter contact information for their child's attendances and endpoints for teachers to access this contact information.

A core challenge creating the application was designing the database efficiently to allow for RESTful endpoints. When I began this process, I found it challenging to identify what data needed to be stored and how to best structure the tables. Specifically, the task of normalising the data was daunting. To handle this macro challenge, I decided to break down the task down into its technical and conceptual elements. First, I found it helpful to research similar API tools that childcare businesses used to facilitate their data and communication. After collecting references, I identified the features that my application needed by reading reviews and imagining use cases. This allowed me to identify improvements I could incorporate into my API such as improving the security of the app by reducing the amount of input data required. To refine the tables, I completed additional research into ERD diagrams and compared my work to industry examples. This allowed me to develop my understanding of ERD design and normalise the database, step-by-step, in a way that prevented technical challenges in the implementation stages. In addition, I continued to review the table design as I designed the API's endpoints which helped identify flaws which I was able to fix such as using a merge table to link contact, children and attendance data in a distinct table to prevent duplicate data.

In addition, to the database design skills that the project required, the task required me to improve my ability using models and schemas. Connecting the Flask routes to the database was simple to implement yet, as I continued programming, I found that my models allowed users to input flawed data which would raise errors. marshmallow's validation tools proved a powerful and convenient way to prevent these errors but, when I began the project, I only had a rudimentary understanding of how they could be applied. In particular, there were input routes where I wanted users to have to choose from one of three values. In this instance, I was able to refer to the reference documentation and find the OneOf() validator which was perfect for the situation. In addition, I had trouble handling datatype errors which would arise when POST requests were submitted with formatting errors but were not particularly descriptive when printed to the console. Again, I referred to SQLAlchemy and marshmallow's documentation and online forums to identify the issue and brainstorm solutions. Two notable examples were when submitting a phone number beginning with a zero, Python would disregard the zero which, in turn, would raise a marshmallow validator error. This was challenging to identify but, after logging the data at each stage, I was able find the error and convert the number input to a string and add the zero knowing that marshmallow could interpret numbers or strings. The other example was submitting a boolean value for an "is_admin" attribute. The request body would inconsistently be interpretted and it took lengthy troubleshooting to recognise the error would arise when the boolean was submitted without being wrapped in appostrophes. Each of these issues required patient research and a more through understanding of Flask, marshmallow and SQLAlchemy behaviours. Preventing these issues at the API level makes the project more robust and easy to incorporate into a front-end application.

Designing and creating a server API required technical knowledge of how to use a Flask, PostgreSQL, SQLAlchemy and marshmallow tech stack as well as the ability to troubleshoot errors in a pragmatic way. In addition, a key challenge of creating a successful API is designing the database in a considered way. With each challenge, I was able to overcome the problem with research and patience.

### References

## Q6. With reference to one of your own projects, evaluate how effective your knowledge and skills were for this project, and suggest changes or improvements for future projects of a similar nature /6

- here's what I would do differently
- Evaluates effectiveness of knowledge and skills accurately, providing examples, and providing an insightful improvement on each skill

One significant project I recently completed was creating a CLI application using Python. The application works by presenting the user with a string describing a mysterious trading card. After receiving this hint, the user can guess the card or receive one or two more hints before guessing it. The user's guess is evaluated, with a simple validator that checks for typos to give the user a second chance, and they receive points or the chance to play again if they are right or wrong. After each correct answer the user's score is compared to the leaderboard and, if it is higher, they can save their score with a name. Within the game there is an easy and hard mode. When creating this app, I had one week to design and implement it and I used a rudimentary Agile methodology to complete the task in time. Reflecting upon the project, there are clear improvements I would make to my methodology and skills for future tasks.

When designing the app, I used a Kanban board on Trello to document what tasks needed doing, which tasks I was prioritising and deadlines for these tasks. I recognised that breaking down the tasks into steps was essential and did so thoroughly but, still, when submitting the assignment, I did not have enough time to complete every feature that I wanted. As I approached the major deadline, I realised that the code implementation, particularly my scoring system was failing and I would be time-pressed to fix it and finish my documentation. To ensure I had time to finish the task, I decided to drop a cosmetic feature and simplify the scoreboard to function more linearly. These decisions allowed me to complete the task on time emphasised errors in my project management. Reflecting upon the project, I realised that I was missing gaps in the Agile methodology after the initial planning stages. A key element of Agile workflows is a frequent stand-up meeting to discuss what's working and whether tasks should be reprioritised (Fernandez & Fernandez, 2008). Because I was working solo, I did not engage in this practice properly which meant I was not adjusting task deadlines to match my success or challenges in different parts of the project. There were multiple instances where I labored through a task, such as implementing the scoreboard, with little success because I had scheduled it to be completed by a certain day, rather than reconsidering whether I could approach it after an easier task. Similarly, I left my documentation to the final day rather than working on it alongside the developing. This was a particular mistake because documenting the task's progress and describing its features would have helped focus the features of the project and highlight which elements were less important to complete early. I have since found much more success in other projects by actively evaluating the prior days work each morning. This has made me feel more comfortable switching timelines on the fly and maximising my efficiency.

In regards to technical skills, this project highlighted my need to improve at writing and maintaining tests. Within the project, a JSON object is parsed to select a random object. The returned object would be largely the same between instances, but some had additional or lacking properties on cards released between years. When ingesting the data to the project, I did not account for these types of issues but they quickly arose by throwing key errors. To handle them, I attempted to write tests that tested the selecting and manipulating functions but I found this task time-consuming and challenging, particularly when I tried to automate the tests. Again, I attempted to work through these challenges without reflecting upon whether this was good practice. This decision slowed down my workflow and held up my progress across days before I finally decided to scrap some of the tests. These testing challenges emphasised two learning points for me. Firstly, I learnt that I need to improve my test writing and maintenance skills. During the project, I tried to write automated tests beyond my scope of knowledge because I did not have a solid understanding of the testing software. In future projects, I will incorporate more research time into learning the testing packages that are available for the tools I am using. Secondly, I would now recognise the bottleneck earlier and pivot my approach. I have since pivoted to write simpler, more stable, manual tests as a safety net to ensure my projects are functioning as expected. From a project management perspective, it was a poor decision to try and become proficient at a new technology whilst under time pressure and I would identify this fault earlier. I also now identify the importance of stable tests, even if they are simple and not optimised.

The CLI app project I completed highlighted errors in my project management under time pressure. The task emphasised the need to use true Agile techniques and a planning flexibility to solve challenges and meet deadlines effectively.

### References

Fernandez, D. J. and Fernandez, J. D. (2008) ‘Agile Project Management —Agilism versus Traditional Approaches’, Journal of Computer Information Systems, 49(2), pp. 10–17. DOI: 10.1080/08874417.2009.11646044.

## Q7. Explain control flow, using an example from the JavaScript programming language /6

- if statements
- Provides a thorough explanation of control flow in programming

When JavaScript code is executed, it is typically interpreted line-by-line in sequential order so that the first line will execute before the second. This sequencing can be altered by using control flow statements which execute code, not neccessarily in sequence, based on described conditions (MDN Web Docs, 2024a). In JavaScript, the ```if```, ```if else```, ```switch```, ```ternary operator``` and ```for loops``` are all techniques that can alter the order that a script is executed including skipping lines (MDN Web Docs, 2024b).

The ```if``` statement evaluates whether a condition is true and, if so, executed a code bloke before continuing to execute the script sequentially. ```if else``` is an alternative method that can be used to evaluate multiple possible conditions and provide a default response if none of the conditions are true. ```if``` and ```if else``` statements require the use of operands that return true or false based on whether the values compared are truthy or falsy. In JavaScript, a function that returns ```false```, ```undefined```, ```null```, ```0```, ```NaN``` or ```""```, or a variable assigned one of these values, is considered falsy and will cause a particular if condition to not execute (MDN Web Docs, 2023a). Conditions can also be checked for loose quality or strict equality. Strict equality compares two values to check if they are both the same datatype and values whilst loose equality will complete a type conversion to see if the values are the same when the data is the same type.

Below is an example of control flow and equality types:

``` JavaScript
function eval () {
var evaluation = ""
var answer = "true"
if (evaluation) {
    return
}
else if (answer === true) {
    evaluation = "Truly true"
    return
}
else if (answer) {
    evaluation = "Sort of true"
    return
}
else {
    evaluation = "Not, in any way, true"
    return
}
console.log(evaluation)
}

eval()

```

```eval``` first initialises the variables ```evaluation``` and ```answer``` and then begins evaluations on the variables. The first if statement checks if ```evaluation``` is a truthy value which, because it is a blank string, is not true so it will not execute. The second if statement checks if answer is a boolean value equaling ```true```, however, it will not execute because answer is a string rather than a boolean so this evaluation is false. The third if statement converts answer to a boolean by checking if it is one of false, undefined, null, 0, NaN or "". Because it is not, nad answer holds a value, it evaluates to true. ```evaluation``` is then set to "Sort of true", the following else statement is skipped and the rest of the function executes so that the console prints "Sort of true". The else statement would execute if none of the other if statements were true but, in this example is not neccessary and does not execute.

Other control conditional flow statements are the ```switch``` statement which describes the different possible conditions a variable could fulfill and executes the matching code block or a default code block. The ```ternary operator``` is an operator that checks for a condition and executes a "true" block or a "false" block depending on what the condition evaluates to.

Loops are an alternative to conditional statement control flow and can be used to execute code that deviates from line-by-line execution. JavaScript has various ```for``` loops as well as ```while``` loops. ```for``` loops repeat a block of code until it evaluates to false such as iterating through an array until there are no more values that have not been iterated. ```while``` statements loop a block of code until a condition evaluates to false. Alternatively, ```do...while``` loops execute a block of code before evaluating a condition, stopping when the condition evaluates falsely (MDN Web Docs, 2023b).

For example:

``` JavaScript
let counter = 0;
do {
    counter += 2;
    console.log(counter)
} while (counter != 10)
```

In this example, ```counter``` is initialised as 0. The ```do``` block adds 2 to ```counter``` and prints the updated value then evaluates whether counter does not equal 10. The ```do``` block will thus loop 5 times until counter equals 10 then continue the script.

### References

MDN Web Docs (2024a) _[Control flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2024b) _[Control flow and error handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2023a) _[Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)_, MDN Docs Glossary website, accessed 29 July 2024.

MDN Web Docs (2023b) _[Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#do...while_statement)_, MDN Docs Glossary website, accessed 29 July 2024.

## Q8. Explain type coercion, using examples from the JavaScript programming language /6

- quirks that are unique to JS
- Provides a thorough explanation of control flow in programming

Type coercion in JavaScript is when a value is implicitly converted from one type to another automatically (MDN Web Docs, 2024a). This is different from conversions that are explicitly declared such as the String() or Number() methods.

There are a variety of circumstances in which JavaScript will automatically change a data type to complete process. The loose equality operator ```==``` will convert strings and booleans to numbers to compare their values against numbers (Samoshkin, 2018).

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

However, other number-based operators including ```<```, ```>=```, ```-```, ```*```, ```%``` and the bitwise operators, which consider binary values, coerce a string to a number.

For example:

```JavaScript
"10" - 5
// Returns 5
"15" / 3
// Returns 5
"5" ^ "3"
// converts "5" to 101, converts "3" to 11
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

In the above example, ```"and"``` evaluates to true when it is explicitly converted because it is not one of the values ```false```, ```undefined```, ```null```, ```0```, ```NaN``` or ```""```. The ```&&``` operator checks if the compared values are truthy by converting them implicitly to boolean. If both values are truthy, the last truthy value is returned. If one of the values is falsy, that value is returned, hence why ```false``` and ```NaN``` are returned in the last two comparisons (MDN Web Docs, 2024b).

When non-primitive values such as objects are compared or evaluated, they are coerced to a primitive data type (Samoshkin, 2018). If added to compared using a logical operator or added using ```+```, the contents of an array will be converted to a string. Similarly, an object will be converted to a string as well. If a mathmetical operator is used, arrays and objects will be converted into numbers results in a NaN value.

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

JavaScript type coercion is a useful feature which can reduce code by eliminating explicit conversion of variables. However, the default coercion behaviour of some data types can lead to unexpected results if not accounted for.

### References

Alexey Samoshkin (2018) _[JavaScript type coercion explained](https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/)_, freeCodeCamp website, accessed 30 July 2024.

MDN Web Docs (2024a) _[Type coercion](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion)_, MDN Docs Glossary website, accessed 30 July 2024.

MDN Web Docs (2024b) _[Logical AND (&&)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)_, MDN Docs Glossary website, accessed 30 July 2024.

## Q9. Explain data types, using examples from the JavaScript programming language /6

- types, unique to JS, show what the concept is and how to use it
- Provides a thorough explanation of data types in programming

In JavaScript, there are seven primitive data types: ```number```, ```string```, ```boolean```, ```null```, ```undefined```, ```symbol``` and ```bigInt```. Variables can be values that are one of these data types or an object such as a function. JavaScript is a dynamic language with dynamic datatypes which allows any variable to be assigned any type and a variable can be changed at any time to a different datatype (MDN Web Docs, 2024a). The primitive data types have a variety of methods and behaviours inherently linked to them that assist in their usage within JavaScript syntax. A variable's datatype can be checked using the built-in ```typeof()``` function.

For example:

```JavaScript
let example = "cat"
typeof(example)
// Returns 'string' 
example = 1
typeof(example)
// Returns 'number'
```

Primitive data types are immutable meaning that a primitive value cannot be altered. For example, the ```number``` ```4``` cannot be altered within JavaScript to equal ```5```. However the other type of data, objects, are mutable and can store primitive data to be changed later. Objects can be considered as a collection of primitive value properties. In addition, primitive data types have methods associated with them that can assist in modifying objects or variables that contain them.

```JavaScript
let tree = "oak"
tree[0] = "bark"
console.log(tree)
// 'oak' 
// The string value is immutable
tree = "bark"
console.log(tree)
// Console shows 'bark'
// Tree variable can be changed
let forest = {trees: "oak"}
// Assigns forest an object value with a key-pair "trees: "oak""
console.log(forest.trees)
// "oak"
forest.trees = "pine"
console.log(forest.trees)
// Console shows "pine"
// Objects are mutable
forest.trees.concat(" and redgums") 
// Uses the string datatype's inbuilt concat() method
console.log(forest.trees)
// "oak and redgums"
```

There are particular quirks to some of the data types and their associated values. Notably, ```null``` and ```undefined``` behave similarly when used in operations but are intended for different uses (MDN Web Docs, 2024a). ```null``` is used to represent the absence of an object whereas ```undefined``` is the lack of a value. Similarly, ```NaN``` is a value that represents something that is not a number but the value itself is classified with a ```number``` datatype. These qualities should be noted when using the loose equality operator.

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
```

```bigint``` is a primitive data type used for handling numbers larger or smaller than the minimum number values of JavaScript. Typically, if a value is added to the maximum ```number``` value, JavaScript will round unpredictably. ```bigint``` does not have this problem, however, and will add accurately. ```bigint``` values can be generated dynamically by adding ```n``` after a number when a variable is being assigned (MDN Web Docs, 2024b). ```symbol``` is a data type used to create constants that are definitively unique. Symbols can be passed as a key value to an object ensuring the symbol value will not clash with a property assigned later and, when generating the symbol, a symbol can hold additional data. Symbols are also not enumerable meaning that they will not be considered when an object is iterated. This quality can be used to keep particular data more private, although the data is can still be accessed in other ways (Playcode.io, n.d.). The ```bigint``` and ```symbol`` datatypes allow for unique functionality.

For example:

``` JavaScript
let maxNumber = Number.MAX_SAFE_INTEGER
// 9007199254740991
maxNumber + 2
// 9007199254740992
// Value is incorrectly added
let bigIntMax = BigInt(Number.MAX_SAFE_INTEGER)
// 9007199254740991n
bigIntMax + 2n
// 9007199254740993n
// Must add using bigint notation
// Successfully tracks update
const house = Symbol("bricks")
let constructionPlans = {[house]: "pink"}
// Symbol can be passed as an object key
constructionPlans.house = "blue"
// Does not overwrite symbol house
console.log(constructionPlans)
// { house: 'blue', [Symbol(bricks)]: 'pink' }
console.log(Object.keys(constructionPlans))
// ['house']
// This is the string value, symbol attribute is not shown
console.log(constructionPlans[house])
// pink
console.log(house)
// Symbol(bricks)
// Symbol can be accessed out of the context of the object it is in

```

The various primitive data types of JavaScript are used to handle different types of values with unique properties. For this reason, they all have specific methods associated with them to extend their functionality. Each primitive type has associated behaviour within the JavaScript language and their properties and methods can be leveraged in objects to create advanced funcitonality.

### References

GeeksforGeeks (2024) _[JavaScript type coercion explained](https://www.geeksforgeeks.org/javascript-data-types/)_, GeeksforGeeks website, accessed 30 July 2024.

MDN Web Docs (2024a) _[JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)_, MDN Web Docs website, accessed 30 July 2024.

MDN Web Docs (2024b) _[BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt)_, MDN Web Docs website, accessed 30 July 2024.

Playcode.io (n.d.) _[JavaScript Symbols](https://playcode.io/javascript/symbols)_, Playcode Website website, accessed 31 July 2024.

## Q10. Explain how arrays can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- explain a concept, how to use it
- Demonstrates an extensive ability to manipulate arrays
- .filter, .map, .sort

Arrays are mutable objects used to store a collection of items in a single variable. Arrays are resizeable and can contain a mix of datatypes including objects. Arrays have an inherent length property which is related to the number of values with in the array. Values within an array are zero-indexed with a numbered key which can be used to target them. Notably, arrays can be explicitly altered to have their length extended and a value can be assigned to a non-sequential index. When this occurs, the indexes between the two values that are assigned values hold an ```undefined``` value.

For example:

```JavaScript
let colours = ['blue', 'pink', 'red']
console.log(colours)
// [ 'blue', 'pink', 'red' ]
colours.length
// 3
colours[2]
// 'red'
colours[6] = 'green'
console.log(colours)
// [ 'blue', 'pink', 'red', <3 empty items>, 'green' ]
colours.length
// 7
```

Index targeting is a rudimentary way to alter an index and there are a variety of prototype methods that can be used to alter them. There are two types of methods to manipulate arrays: mutating methods and copying methods. Mutating methods alter the array that the method is applied to whilst copying methods create and return a shallow copy of the array with specified alterations. Mutating methods often have a non-mutating alternative counterpart such as ```pop()```, a mutating method, and ```slice(0, -1)```, a non-mutating alternative, two functions that remove values from arrays (MDN Web Docs, 2024). There are many methods that can manipulate and mutate an array and its values such as ```push()``` which adds a value to the end of an array, ```reverse()``` which reverses the indexes of an array and ```shift()``` which removes the first value of an array and returns it. Their non-altering alternatives are ```concat([x, arrayName])``` which returns a merged copy array of the given arguments with the x value as the first value, ```toReversed()``` which returns a reverse-ordered copy of an array and ```slice(1)``` which which returns a copy of the array with the values after the provided index.

For example:

```JavaScript
let colours = ["blue", "red", "green"]
// [ 'blue', 'red', 'green' ]
colours.slice(0, -1)
// [ 'blue', 'red' ]
colours
// [ 'blue', 'red', 'green' ]
// Colours is unaltered
colours.pop()
// 'green'
colours
// [ 'blue', 'red' ]
// pop() mutated Colours
```

Arrays also have a collection of iterative methods which consider all values in an array and parses each value through a given callback function with different effects based on the specific method. Iterative methods are non-mutating and return copies of the relevant results. ```forEach()``` accepts a callback function and simply applies that function to all values in the array individually but does not return anything. ```filter()``` takes a callback function and returns a new array with only values that return a truthy value when passed to the provided function. ```map()``` applies a callback function to all values in an array and returns the results in a new array. ```sort()``` is an array method used to sort indexes of an array based on the criteria of a passed compare function. Notably, whilst ```sort()``` is similar to an iterative function, it mutates the array and sometimes invokes the callback function multiple times on a single index to sort the values meaning it is not a true iterative function.

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
// colours was unaltered
colours.sort((a, b) => a.length - b.length)
// [ 'red', 'blue', 'green' ]
// Call back function sorts by shortest length first
console.log(colours)
// Console shows:
// [ 'red', 'blue', 'green' ]
// colours array is mutated
```

Arrays can be manipulated in various ways making them flexible tools for data storage. Array's iterative methods are particularly powerful for altering arrays according to sophisticated criteria. Essentially, arrays can be altered in mutative and non-mutative ways and there are always different techniques to achieve each type of alteration.

### References

MDN Web Docs (2024) _[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)_, MDN Web Docs website, accessed 31 July 2024.

## Q11. Explain how objects can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- Demonstrates an extensive ability to manipulate objects

(MDN Web Docs, 2024a)

Objects are used in JavaScript to store properties and assign values to them for reference or manipulation. Properties and their associated values are key and value pairs and the key value's can be initialised with a name (a word without appostrophes), a string, a symbol or a number (MDN Web Docs, 2024). A property value can be a primitive data type or another object such as a function, an array or another nested object. A property that is a function is referred to as a method and this is how data types have associated functions that can be easily called. Each object property can be accessed using dot notation or bracket notation, except for properties with spaces which must be accessed using bracket notation. By referring to an object's property key, it can often be altered. If a property does not exist yet is assigned a value, a new property will be initialised with that value.

For example:

``` JavaScript
let identifier = "name"
let dog = {
    identifier: "Charles",
    "personality type": "friendly"
}
console.log(dog)
// Console shows:
// { identifier: 'Charles', 'personality type': 'friendly' }
dog.identifier
// 'Charles'
dog['personality type']
// 'friendly
dog.enemy = "cats"
console.log(dog)
// { identifier: 'Charles', 'personality type': 'friendly', enemy: 'cats' }
```

Objects can be created by listing properties within the object initializer syntax ```{}```, using ```Object.create()``` syntax or by using ```new ObjectName``` where ObjectName is a defined object constructor function. Defining an object constructor function allows a particular object structure to be reused as many times as required.

For example:

``` JavaScript
function Person(name, birthYear) {
    this.name = name,
    this.birthYear = birthYear,
    this.planet = "Earth"
    this.birthdaySong = function() {console.log("Happy birthday to me!")}
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

When an object constructor function contains a method like in the above example, the method is stored in each instance created using the constructor function. Alternatively, objects of the same type can share attributes including methods. Additional methods can be added this way by using the ```ObjectName.prototype``` syntax where ObjectName is a constructor name. The ```.constructor.name``` property of an object returns the name of the function used to construct it. To define a abstracted functions to interact with an object's properties or to make property keys obscured, objects can be initialised with ith getter and setter methods. These methods are attributes assigned using the ```get``` and ```set``` keywords followed by a function that returns or alters a different property. Getters and setters can be declared after an object and instances exist by using the ```.defineProperties()``` function which will add the functions to all instances similar to ```.prototype``` syntax.

For example:

``` JavaScript
function Person(name) {
    this.name = name
}
let boy1 = new Person("Jeff")
let boy2 = new Person("Stu")
boy2.constructor.name
// Returns 'Person'
Person.prototype.grade = 2
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
boy2.setName = "Charles"
console.log(boy2.getName)
// Console shows:
// 'Charles'
console.log(boy2.name)
// Console shows:
// 'Charles'
```

Object properties can be iterated through for manipulation as well. The inbuilt ```Object.keys()``` returns all property key values that are enumerables which excludes values such as getter and setter functions as well as prototype properties. ```Object.getOwnPropertyNames()``` returns all key names including non-enumerable keys excluding protype properties again. Otherwise, a ```for in``` loop can be used to iterate through an object and returns all emumerable properties including prototype properties. Each property can than be used or manipulated in the code block.

For example:

``` JavaScript
// Using boy1 and boy2 as defined in the previous example block
Object.keys(boy2)
// Returns [ 'name' ]
Object.getOwnPropertyNames(boy2)
// Returns [ 'name', 'getName', 'setName' ]
for (property in boy2) {console.log(property)}
// Console shows:
// name
// grade
for (property in boy2) {
    boy2[property] = "Freshman"
}
for (property in boy2) {console.log(boy2[property])}
// Console shows:
// Freshman
// Freshman
```

There are multiple, powerful ways to manipulate objects in JavaScript targeting individual instances or all instances constructed using the same function. The different object methods have distinct use cases and can be chained creatively to alter stored data easily.

### References

MDN Web Docs (2024) _[Working with objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)_, MDN Web Docs website, accessed 31 July 2024.

## Q12. Explain how JSON can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- Demonstrates an extensive ability to manipulate JSON

JSON (JavaScript Object Notation) is a text-based format designed for transporting data as a string that can be, later, interpreted as an object. Formatting data as a string means it can be handled by more applications, including different applications using different native language, making JSON files convenient for sharing (MDN Web Docs, 2024b).

JSON can only handle particular JavaScript data types and has formatting rules that differ from typical JavaScript objects. JSON supports arrays, strings, booleans, the ```null``` value and nested objects that contain these values. However, strings must be contained in double-quotes, numbers cannot begin with 0 and the ```NaN``` and ```Infinity``` number values cannot be used. This also means that ```BigInt```, ```undefined``` and ```Symbol``` values cannot be stored in their natural formats, neither can functions.

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
```

Whilst JSON does not accept particular datatypes, developers can work around this by storing data in different formats for later conversion. For example, a phone number cannot be stored as a number value in JavaScript objects or JSON alike because it begins with a 0 and contains too main digits. Instead, a phone number could be stored as a string. In a unique case, ```BigInt``` values cannot be converted to JSON strings using ```JSON.stringify()``` and will raise an error but this can be worked around by writing a custom prototype function to handle their automatic conversion (MDN Web Docs, 2024a and MDN Web Docs, 2024c).

The ```JSON.stringify()``` method provides another method to manipulate JSON objects via its second parameter: ```replacer```. The ```replacer``` parameter can be an array containing designated key values, listed as strings, to contain in the JSON string or a function that returns any key or value to include.

For example:

```JavaScript
let bigObj = {value: 111222333444n}
bigObj
// { value: 111222333444n }
JSON.stringify(bigObj)
// Throws:
// Uncaught TypeError: Do not know how to serialize a BigInt
BigInt.prototype.toJSON = function () { return this.toString() }
// Specifies how to handle BigInt objects when they are parsed by JSON.stringify()
// This method converts it to a string
JSON.stringify(bigObj)
// Returns: 
// '{"value":"111222333444"}'

let numbers = {a: 2, b: 3}
JSON.stringify(example, (key, value) => {if (value != '2') {return value}})
// Returns:
// '{"b":3}'
JSON.stringify(example, ['b'])
// Returns:
// '{"b":3}'
```

Another useful way to utilise and manipulate JSON within JavaScript is to save and access it using the browser's ```sessionStorage``` or ```localStorage```. ```sessionStorage``` is an amount of memory in a browser that can hold data until the session ends whilst ```localStorage``` is an amount of memory that perseveres until a user deletes it. Both of these objects accept string data and can be accessed and saved-to in JavaScript scripts, making them perfect for caching JSON when creating web applications (W3 Schools, 2024).

For example:

```JavaScript
let usefulData = {content: "Don't forget to brush your teeth each night"}
let usefulJSON = JSON.stringify(usefulData)
localStorage.setItem("storedExample", usefulJSON)
// Saves the usefulJSON string as "storedExample" in local storage

let retrievedString = localStorage.getItem("storedExample");
let retrievedJSON = JSON.parse(restievedString);
// The JSON string is retrieved from local storage and converted to a JSON object for later manipulation, mirroring the original usefulData object
```

JSON is a popular and convenient format to send and receive data to be handled by different coding languages. Within JavaScript, the ```JSON``` global object and its methods provide convenient conversion tools that allow users to handle JSON formatting easily. These methods have notable customisable options that should be considered to handle differently-typed data. In addition, JSON formatting is particularly useful for caching data in browsers when creating web applications.

### References

MDN Web Docs (2024a) _[JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)_, MDN Web Docs website, accessed 1 August 2024.

MDN Web Docs (2024b) _[Working with JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)_, MDN Web Docs website, accessed 31 July 2024.

MDN Web Docs (2024c) _[JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)_, MDN Web Docs website, accessed 31 July 2024.

W3 Schools (2024) _[JSON.stringify()](https://www.w3schools.com/js/js_json_stringify.asp)_, W3 Schools website, accessed 31 July 2024.
