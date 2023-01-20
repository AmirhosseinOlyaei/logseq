- https://programs.ulem.org/mod/assign/view.php?id=325
- [[MSIMBO - Intro to Computing]]
- **Goal**
	- Using TailwindCSS, design your own version of the Facebook mobile newsfeed (you will need 3 pages).
	  
	  Some important notes:
	- 1. You're designing just the sections in the screenshot below
	- 2. TailwindCSS is [a mobile-first platform](https://tailwindcss.com/docs/responsive-design#working-mobile-first)
	  ![](https://i.imgur.com/iVi8u3z.jpeg)
- **Prerequisites Materials**
	- Download and [install Responsively](https://responsively.app/)
	  
	  (You will use this as your web browser to preview your work through this project)
	- Register for Jsitor or Codepen
	- [Utility-First Fundamentals](https://tailwindcss.com/docs/utility-first)
	- [Reusing Styles](https://tailwindcss.com/docs/reusing-styles)
	- [Adding Custom Styles](https://tailwindcss.com/docs/adding-custom-styles)
	- [Installation](https://tailwindcss.com/docs/installation)
	- [Editor Setup](https://tailwindcss.com/docs/editor-setup)
	- [Width](https://tailwindcss.com/docs/width)
	- [Padding](https://tailwindcss.com/docs/padding)
	- [Responsive Design](https://tailwindcss.com/docs/responsive-design)
	- [Object Fit](https://tailwindcss.com/docs/object-fit)
	- [X-Index](https://tailwindcss.com/docs/z-index)
-
- **How to Submit Your Work**
	- 1. Name your project/repo `facebook-tailwind`
	- 1. Commit your code and project to GitHub
	- 2. Deploy your project to vercel (this should happen with commits you do to GitHub)
	- 3. Submit the following to the appropriate section on Moodle
		- Your public GitHub link (test that you can visit this link in an incognito window)
		- Your public Vercel link (test that you can visit this link in an incognito window)
-
- **Step 1**: Craft your plan in GitHub issues, send me that link in slack.
	- logseq://graph/logseq?block-id=63c8c738-c03d-4c75-b387-0c4195a4a72c
		- issue : Download Node.js LTS.
			- https://nodejs.org/en/
		- issue : Installing yarn
			- `sudo npm i -g yarn` or `npm install -global yarn`
		- issue : Making facebook-tailwind project directories
			- ```bash
			  cd ULEM
			  cd msimbo-projects
			  mkdir facebook-tailwind
			  cd facebook-tailwind
			  ```
			- issue :
	- {{embed ((63c8c738-c03d-4c75-b387-0c4195a4a72c))}}
	-
	- Open your terminal and `cd` into your **msimbo-projects** folder
	- Clone this repo, `git clone git@github.com:msimbo/f23c1-google-converter.git` #Git
	- `cd` into the [new] folder, **f23c1-google-converter**
	- Run: `yarn` to build the packages this project depends on. #yarn
	- Run `yarn serve:dev` to preview the project
	- Run `yarn watch:css` to start making changes to the tailwind styles. This starts the tailwind build script.
	- in `.gitignore`
		- ```git
		  node_modules
		  ```
	- in `tailwind.config.js`
		- ```js
		  content: ["./*.html"],
		  ```
	- in `package.json`
		- ```js
		  {
		    "devDependencies": {
		      "live-server": "git+https://github.com/tapio/live-server.git#ad22544",
		      "tailwindcss": "^3.2.4"
		    },
		    "scripts": {
		      "watch:css": "npx tailwindcss -i ./src/tailwind.css -o ./css/style.css --watch",
		      "serve:dev": "live-server ."
		    }
		  }
		  ```
	- in `index.html`
		- ```html
		      <link rel="stylesheet" href="css/style.css">
		  ```
	- in `src/tailwind.css`
		- ```css
		  @tailwind base;
		  @tailwind components;
		  @tailwind utilities;
		  ```
	-