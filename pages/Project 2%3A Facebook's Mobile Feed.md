- https://programs.ulem.org/mod/assign/view.php?id=325
- [[MSIMBO - Intro to Computing]]
- **Goal**
	- Using #TailwindCSS, design your own version of the Facebook mobile newsfeed (you will need 3 pages).
	  
	  Some important notes:
	- 1. You're designing just the sections in the screenshot below
	- 2. TailwindCSS is [a mobile-first platform](https://tailwindcss.com/docs/responsive-design#working-mobile-first)
	  ![](https://i.imgur.com/iVi8u3z.jpeg)
- **Prerequisites Materials**
	- Download and [install Responsively](https://responsively.app/) #responsively.app
	  id:: c4d2a444-99be-4803-8ebd-a5834d051d49
	  
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
		- issue : Install tailwind CSS
			- ```bash
			  sudo yarn add -D tailwindcss
			  ```
		- issue: `npx tailwindcss init`
			- >Configure your template paths.
			- >Add the paths to all of your template files in your `tailwind.config.js` file.
			- ```js
			  content: ["./src/**/*.{html,js}"], ["./*.html"],
			  ```
		- issue :
			- ```bash
			  mkdir src && cd src && touch tailwind.css
			  ```
			- ```css
			  @tailwind base;
			  @tailwind components;
			  @tailwind utilities;
			  ```
		- issue : Start the Tailwind CLI build process
			- Run the CLI tool to scan your template files for classes and build your CSS.
			- ```bash
			  npx tailwindcss -i ./src/tailwind.css -o ./css/styles.css --watch
			  ```
		- issue : Run: `yarn` to build the packages this project depends on.
			- a new #bash tab for each line of code in #vscode
			- ```bash
			  cd facebook-tailwind
			  yarn serve:dev
			  yarn watch:css
			  ```
			- Run `yarn serve:dev` to preview the project.
			- Run `yarn watch:css` to start making changes to the tailwind styles. This starts the tailwind build script.
			- Rename tabs
		- issue : in `package.json` check
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
		- issue : in `index.html` head add
			- ```html
			  <link href="/css/styles.css" rel="stylesheet">
			  ```
		- issue : create the file `touch .gitignore`
			- >type `node_modules` in .gitignore file
		- issue : [[Push to GitHub]]
			- {{embed ((63c83f7e-3974-4694-811b-8f77819b0408))}}
		- issue : {{embed ((c4d2a444-99be-4803-8ebd-a5834d051d49))}}
		- issue : signed in to #Jsitor