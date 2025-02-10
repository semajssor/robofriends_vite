# Tutorial for React + Vite 

### To run the project:

- Clone this repo
- Run `$ npm install`
- Run `$ npm run dev`

I used my other ***[robot_friends](https://github.com/semajssor/robot_friends)*** React project and deployed it as Vite. 

To create a new Vite project with React[^1], you have to:

   1. Create a new folder 
   2. Open it with code editor 
   3. In the terminal, cd to this project
   4. Enter the command `npm create vite@latest` (or yarn: `yarn create vite`)
   5. The terminal will prompt you:
      ```
      Need to install the follwing packages:
      create-vite@6.1.0   (that will show the latest version of Vite)
      Ok to proceed? (y)  (here you have to press `y` on your keybord)
      ```
   6. It will now ask you to name your project:
      ```
      ? Project name: >> 
      ```
   7. Now the terminal with prompt you to select a framework:
      ```
      Vanilla (It means Vanilla JavaScript)
      vue
      React (I used this option)
      Preact
      Lit
      Svelte
      Solid
      Qwik
      Others
      ```
   8. Then, they will ask you to select a variant:
      ```
      TypeScript
      TypeScript + SWC
      JavaScript        (I used this option)
      JavaScript + SWC
      Remix
      ```
   9. It's done, now simply run:
      ```
      $ cd `_(name of your project)_`
      $ npm install
      $ npm run dev
      ```

Once you're ready, create your new repository in GitHub and run the following commands to initialize a git repository in your Vite app and push your existing code to a remote repository on GitHub.

```
$ git init
$ git add .
$ git commit -m "initial-commit"
$ git branch -M main
$ git remote add origin http://github.com/{username}/{repo-name}.git
$ git push -u origin main
```

To deploy your Vite app to GitHub Pages, follow the following steps[^2]:

   1. In your `vite.config.js` file, update the **base** config with your repo name:
      ```
      import { defineConfig } from 'vite'
      import react from '@vitejs/plugin-react'

      // https://vitejs.dev/config/
      export default defineConfig({
      plugins: [react()],
      base: "/{repo-mane}/"
      })
      ```
   2. In your terminal, make sure your are in your project and run the following command:
      ```
      $ npm install gh-pages --save-dev
      ```

   3. Update your `package.json` file with the following **predeploy** and **deploy** scripts:
      ```
      "scripts": {
      "predeploy" : "npm run build",
      "deploy" : "gh-pages -d dist",
      (rest of your code)
      }
      ```
      Add the complete website URL by setting **homepage** in package.json
      ```
      "homepage": "https://{username}.github.io/{repo-name}/"
      ```
      Your updated `package.json` file should like something like:
      ```
      {
         "name": "robofriends_vite",
         "homepage": "https://semajssor.github.io/robofriends_vite/",
         "private": true,
         "version": "0.0.0",
         "type": "module",
         "scripts": {
            "predeploy": "npm run build",
            "deploy": "gh-pages -d dist",
            "dev": "vite",
            "build": "vite build",
            (rest of your script)
         }      
         (rest of your code)
      }
      ```
   4. Now, run the command `$ npm run deploy`. Once it's **published**, you can test it and run `$ npm run dev`.

   Now, you are ready to do the usual git commands to push it to GitHub. Wait a few minutes to make sure that you have a latest version and then you are ready to configure your GitHub Pages:

   1. In GitHub, click on **Settings**
   2. Then, click on **Pages**
   3. In the section **Build and deployment** make sure that the option ***gh-pages*** is selected
   4. Then wait a bit and you should be able to see your website.
   5. Lastly, go back on the main page of your repository, and in the **About** section, click on the gear logo, and then thick the box where it's written 
   - [x] Use your GitHub Pages website


[^1]: [Getting started with Vite](https://vite.dev/guide/) 
[^2]: [Deploying Vite App to GitHub Pages](https://medium.com/@aishwaryaparab1/deploying-vite-deploying-vite-app-to-github-pages-166fff40ffd3)