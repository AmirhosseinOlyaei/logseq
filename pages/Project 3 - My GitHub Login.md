- ## My GitHub Login
- **Goal**
- Help GitHub designed their login form with Validation. A replica of [https://github.com/login](https://github.com/login) (you need to be logged out from GH to access the page)
  
  ![](https://i.imgur.com/W7JDJip.png)
- We want to validate the following:
- Username or email address is not empty.
- Username or email address is more that 6 characters.
- Password fields is not empty.
- Password fiend is more than 6 characters.
- **Prerequisite reading**
- None
- **References**
- [Get an HTML ElementbyId](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
- ["Watching an event on an element"](https://www.w3schools.com/jsref/met_element_addeventlistener.asp)
- [Relevant JS events](https://data-flair.training/blogs/javascript-event-types/)
-
- issues:
	- Create a new repository
		- Create **my-github-login** repository
		- ```bash
		  cd msimbo-projects
		  git clone git@github.com:AmirhosseinOlyaei/my-github-login.git
		  ```
	- MSIMBO's handbook for `Tailwindcss`
		- https://app.gitbook.com/o/7ARYFXdeWuKbQzeWPB76/s/ORacclflVRID90lsQOUg/resources/frameworks-and-libraries/setup-tailwindcss
	- Install **npm & node**
		- `https://nodejs.org/en/download/`
	- Install **yarn**
		- `npm install --global yarn`
		- or
		- `sudo npm i -g yarn`
	- Install **TailwindCSS package**
		- `yarn add -D tailwindcss`
		- `npx tailwindcss init`
	- Modify **tailwind.config.js**
		- Replace: `content: ["./src/**/*.{html,js}", "./*.{html,js}"],`
	- Create a **tailwind.css** file and add contents
		- `touch tailwind.css`
		- ```tailwind.css
		  /* tailwind.css */
		  @tailwind base;
		  @tailwind components;
		  @tailwind utilities;
		  ```
	- Dynamically generate a **styles.css** file `tailwind.css` this file
		- `npx tailwindcss -i ./tailwind.css -o ./styles.css --watch`
	- Create an **index.html** file and reference our generated `styles.css`
		- `touch index.html`
		- ```index.html
		  	<!doctype html>
		  	<html>
		  	<head>
		  	  <!-- ... -->
		  	  <meta charset="UTF-8" />
		  	  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
		  	  **<link href="styles.css" rel="stylesheet">**
		  	</head>
		  	<body>
		  	   <h1 class="text-9xl"> welcome</h1>
		  	</body>
		  	</html>
		  ```
		- touch `.gitignore` and include `node_modules` in the file
			- prevent `node_module` folder from being push to the GitHub
		-
		- Bootstrapping the project
			- [x] Todo list: closing issues with commit message. [[Git]]
			- fixes #1 - Create a new repository my-simple-todo
			- fixes # - Clone the repository in local msimbo-projects folder
			- fixes # - Create .gitignore file
			- fixes # - Install TailwindCSS package
			- fixes # - Modify tailwind.config.js
			- fixes # - Create a tailwind.css file and add contents
			- fixes # - Dynamically generate a styles.css file from tailwind.css file
			- fixes # - Create an index.html file and reference our generated styles.css
			- fixes # - Create a README.md file
		-
		- [x] Bootstrapping TailwindCSS
			- ```zsh
			  create a repository `my-github-login`
			  cd msimbo-projects
			  git clone git@github.com:AmirhosseinOlyaei/my-github-login.git
			  cat >> .gitignore
			  node_modules
			  ^C
			  brew install node // https://nodejs.org/en/download/
			  sudo npm i -g yarn
			  yarn add -D tailwindcss
			  npx tailwindcss init
			  //Replace: `content: ["./src/**/*.{html,js}", "./*.{html,js}"],` in tailwind.config.js
			  cat >> tailwind.css
			  /* tailwind.css */
			  @tailwind base;
			  @tailwind components;
			  @tailwind utilities;
			  ^C
			  npx tailwindcss -i ./tailwind.css -o ./styles.css --watch
			  //Add `<link href="styles.css" rel="stylesheet">` in index.html
			  
			  ```
		-
		- **Front-end work for Project 3: My GitHub Login** #project
			- **Description**
				- Completing tasks utilizing HTML, CSS and JavaScript to make sure GitHub Login works smoothly and as designed.
			- **Tasks** [Project3: A GitHub Login]
				- [x] **Bootstrapping** TailwindCSS and GitHub
				- [x] **Design** GitHub login user interface in HTML and Tailwindcss
				- [x] **Implement** form validation in JS
					- [x] Username or email address is not empty
					- [x] Username or email address is more that 6 characters
					- [x] Password fields is not empty
					- [x] Password field is more than 6 characters
				- **Integrate** with back-end
					- Deploy to Vercel
		-
		- **[[HTML]] [[Planning]] **
			- [x] Create a section to hold all included elements in the center of the page
			- [x] Division 1 includes: GitHub logo
			- [x] Division 2 includes: GitHub Sign in title
			- [x] Division 3 includes: a hidden error box
			- [x] Division 4 includes: a form
				- [x] Label for username
				- [x] Input box
				- [x] Label for password
				- [x] Input box
				- [x] Submit bottom
			- [x] Division 5 includes: registration link
			- [x] Utilized elements to display the content
				- tags:
					- <html>
					- <meta>
					- <link>
					- <title>
					- <body>
					- <div>
					- <img>
					- <p>
					- <form>
					- <label>
					- <input>
					- <script>
				- attributes:
					- lang
					- charset
					- name
					- content
					- initial-scale
					- href
					- rel
					- class
					- id
					- src
					- alt
					- type
					- value
					- type
		-
		- **[[CSS]] [[Planning]] **
			- Basics - Cascading Style Sheets to format the layout of the app
			- Selectors - class, id, ...
			- Box Model - Content, Padding, Border and Margin
			- Properties - color, border, margin, font-style, ...
			- Responsive & Flexbox - mobile first
			- [x] Framework: TailwindCSS
				- m-n -> margin
				- p-n -> padding
				- border
				- rounded-md
				- bg -> background
				- w -> width
				- flex
				- flex-col
				- justify-center
				- items-center
				- space-x-n
				- text-sm
				- text-color-n
		-
		- **[[JavaScript]] [[Planning]]**
			- [[Code along]]
				- [[f23c1-google-converter]]
			- **Tasks**
				- [x] get elements by id from html and put in a variable
				- [x] add an event listener by submit and run a function
					- [x] prevent default page refresh function
					- [x] conditional statements to check:
					- [x] Username or email address is not empty
					- [x] Username or email address is more that 6 characters
					- [x] Password fields is not empty
					- [x] Password field is more than 6 characters
					- [x] show error message if not true
					- [x] hide error message if true
			- Define types and variables
				- .String()
				  id:: 63deffc2-a17d-4c6d-b892-877d22c1c62d
				- const xElements
				- const xValues
			- Implement functions
				- .getElementById()
				- .innerHTML
				- .addEventListener()
				- .preventDefault()
				- .includes()
			- Conditions
				- if
				- else if
				- else