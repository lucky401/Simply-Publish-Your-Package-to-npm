---
theme: default
title: 'Simply Publish Your Package to npm'
download: true
monaco: false
highlighter: Prism
routerMode: 'hash'
colorSchema: 'dark'
info: |
  ## Simply Publish Your Package to npm
  By Lucky Dewa Satria.
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
  .font-press-start {
    font-family: 'Press Start 2P', sans-serif !important;
  }
  .text-gradient {
    background-color: #2B90B6;
    background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
    background-size: 100%;
    -webkit-background-clip: text;
    -moz-background-clip: text;
    -webkit-text-fill-color: transparent; 
    -moz-text-fill-color: transparent;
  }
  .text-gradient-red {
    background-color: #2B90B6;
    background-image: linear-gradient(45deg, #f59e0b 10%, #ef4444 20%);
    background-size: 100%;
    -webkit-background-clip: text;
    -moz-background-clip: text;
    -webkit-text-fill-color: transparent; 
    -moz-text-fill-color: transparent;
  }
</style>

<img
  src="/npm-bg.png"
  class="h-screen absolute top-0 right-0 left-0 -z-1"
  title="NPM"
  alt="NPM background"
/>

<div class="flex z-2">
  <div>
    <h1 class="text-base font-semibold">Simply Publish Your Package to npm</h1>
    <span class="text-lg">Bring the best of open source to you, your team, and your company</span>
    <div class="pt-12">
      <span
        @click="$slidev.nav.next"
        class="px-2 p-1 rounded cursor-pointer"
        hover="bg-white bg-opacity-10">
        Press Space for next page <carbon:arrow-right class="inline"/>
      </span>
    </div>
  </div>
  <img
    src="/npm-logo.png"
    class="h-24 mt-10"
    title="NPM"
    alt="NPM Logo"
  />
</div>

---

<span class="text-gradient text-2xl font-bold">NPM Package</span>

As of the moment I'm writing this talks, npm has facilitated the publication of over 1.6 million packages with a weekly download rate of over 31 billion! These numbers are fantastic for any software tool.

`npm i borderi --save`

<img
  src="/wombat-install.png"
  class="h-60"
  border="rounded-lg"
  title="NPM Install"
  alt="NPM Install"
/>

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

Read more about [npm](https://docs.npmjs.com/)

---

<div class="absolute top-1/2 left-1/2 transform-gpu -translate-x-1/2 -translate-y-1/2 w-11/12">
  <div class="flex items-center">
    <div>
      <h1>Let's start our imagination.</h1>
      <h3 class="text-white">
        Let’s assume we have this question for UI projects worked by <span class="text-yellow-500">3 different teams</span> for <span class="text-yellow-500">3 different projects</span> <span class="text-purple-500">together to achieve one vision</span>. Most UI projects run on the browser. The bundle size is a constraint. We cannot have too large a bundle size since it directly affects the performance of our app. So, let’s look at the different scenarios when we want to publish our code as NPM packages
      </h3>
    </div>
    <img
      src="/npm-wombat.jpeg"
      class="h-60 ml-8"
      border="rounded-lg"
      title="wombat mascot"
      alt="wombat mascot"
    />
  </div>
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<span class="text-2xl font-bold"><span class="text-yellow-500">Why</span> and <span class="text-yellow-500">when</span> you sould <span class="text-yellow-500">create one</span></span>

Should we publish them as public NPM packages or private NPM packages which can be used only within our enterprise?

<div class="grid grid-rows-5 gap-y-5 text-lg mt-12">
  <span><flat-color-icons:multiple-inputs class="inline"/> We have multiple projects using similar code (Reusable code)</span>
  <span><openmoji-brick class="inline"/> Minimum customization over every project</span>
  <span><fxemoji-bank class="inline"/> More maintainable codebase (Testability)</span>
  <span><noto-man-detective class="inline"/> Provide consistency across project </span>
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<span class="text-2xl font-bold"><span class="text-yellow-500">Why</span> and <span class="text-yellow-500">when</span> you <span class="text-red-500">shouldn't</span> create on</span>

when should we avoid publishing a NPM package?

<div class="grid grid-rows-5 gap-y-5 text-lg mt-12">
  <span><simple-icons:crowdsource class="inline text-yellow-500"/> We don't want to have some extra code for all the scenarios</span>
  <span><vscode-icons:file-type-patch class="inline"/> We need to support customization over every project</span>
  <span><emojione-v1:person-lifting-weights class="inline"/> We don't have support to maintain all codebase</span>
  <span><flat-color-icons:engineering class="inline"/> We work on small teams and the requirement likely to change </span>
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<div class="absolute top-1/2 left-1/2 transform-gpu -translate-x-1/2 -translate-y-1/2">
    <h1 class="font-press-start mb-8">Okay,okay!</h1>  
    <img
      src="/show-me-the-code.jpeg"
      class="h-64"
      border="rounded-lg"
      title="wombat mascot"
      alt="wombat mascot"
    />
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<div class="absolute top-1/2 left-1/2 transform-gpu -translate-x-1/2 -translate-y-1/2">
    <img
      src="/npm-publish.png"
      class="h-40 block mb-8"
      border="rounded-lg"
      title="NPM publish"
      alt="NPM publish"
    />
    <h1>Let's build a simple package and publish it to NPM</h1>
    <span @click="$slidev.nav.next" class="font-press-start text-gradient-red text-xl mt-8 block cursor-pointer">Start Building</span>
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

# Project overview

We want to create a simple package, this package expose functions to make a border in HTML

`npm i borderi --save`

<div class="flex justify-between">
  <div class="w-1/2">

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document</title>
    <style>
      .box {
        width: 300px;
        height: 300px;
      }
    </style>
  </head>
  <body>
    <div class="borderi box"></div>
    <script src="./index.js"></script>
  </body>
</html>
```

  </div>
  <div class="w-1/2 ml-6">

```js
// index.js
import { borderi } from 'borderi';
borderi({
  border_type: 'thick',
  border_color: 'blue',
});
```

<img
    src="/project.png"
    class="h-40"
    border="rounded-lg"
    title="Project overview"
    alt="Project overview"
  />

</div>
</div>

---

# First, we need [npm](https://www.npmjs.com/signup) account

<div class="flex">
  <img
    src="/register.png"
    class="w-60 mr-8 mt-4"
    border="rounded-lg"
    title="NPM register"
    alt="NPM register"
  />
  <div>

`npm login`

<img
  src="/login.png"
  class="h-40 mt-5"
  border="rounded-lg"
  title="NPM login"
  alt="NPM login"
/>

<span class="text-sm text-gray-500">If you activate 2FA auth, enter temporary code from your authenticator</span>

  </div>
</div>

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Second, npm init

We need move to our project or workspace folder and init npm
<br/><br/>
`cd borderi-package` then `npm init`

<div class="flex">
  <img
    src="/package-json.png"
    class="h-40 mt-1 mr-8"
    title="NPM init"
    alt="NPM init"
  />
  <div>

```json
{
  "name": "borderi",
  "version": "1.0.0",
  "description": "Example package",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": ["border", "html", "border"],
  "author": "Lucky Dewa Satria",
  "license": "MIT"
}
```

  </div>
</div>

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Third, create our package

```js{all|1|2-16|17|all}
const borderi = (options) => {
  let els = document.querySelectorAll('.borderi');
  if (options.border_type === 'thick') {
    options.border_type = '3px';
  } else {
    options.border_type = '1px';
  }
  if (!options.border_color) {
    options.border_color = 'black';
  }

  els.forEach((el) => {
    el.style.border = `${options.border_type} solid ${options.border_color}`;
  });
};

module.exports.borderi = borderi;
```

<span v-click="1" class="absolute right-40 top-24 text-green-300 text-xl">
  We want receive some options
</span>

<arrow v-click="1" x1="510" y1="110" x2="300" y2="110" color="#564" width="3" arrowSize="1" />

<span v-click="3" class="absolute right-67 top-95 text-green-300 text-xl">
  Expose our package
</span>

<arrow v-click="3" x1="510" y1="395" x2="310" y2="400" color="#564" width="3" arrowSize="1" />

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Fourth, publish

`npm publish`

<img
  src="/publish.png"
  class="h-80"
  title="NPM publish"
  alt="NPM publish"
/>

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Check on npm registry

You can check on [npm](https://www.npmjs.com/)

<img
  src="/registry.png"
  class="h-80"
  title="NPM registry"
  alt="NPM registry"
/>

[https://www.npmjs.com/package/borderi](https://www.npmjs.com/package/borderi)

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

<div class="absolute top-1/2 left-1/2 transform-gpu -translate-x-1/2 -translate-y-1/2">
  <span class="text-center block text-4xl leading-loose" style="font-family: 'Press Start 2P', sans-serif">
    There is <br/> more <flat-color-icons:idea  class="inline" />
  </span>
</div>
<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Tips, You can easily manage package using np

A better npm publish

<div class="flex">

  <div class="mr-4">
  <img
  src="/np.png"
  class="h-50"
  title="npm on github"
  alt="npm on github"
/>

[https://github.com/sindresorhus/np](https://github.com/sindresorhus/np)

</div>
  <div>

### Install

`$ npm install --global np`

### Usage

`$ np` and you good to go

<img
    src="/screenshot.gif"
    class="h-30"
    title="better npm publish"
    alt="better npm publish"
  />

  </div>
</div>

<div class="p-1  bg-gradient-to-r from-yellow-500 via-red-500 to-purple-500 absolute top-0 right-0 left-0"></div>

---

# Thanks, Any feedback would be appreciated

<div class="flex w-sm my-10 items-center">
  <img src="/lucky.jpg" class="h-20 rounded-full shadow-2xl">
  <div class="ml-5">
    <span class="block mb-2" style="font-family: 'Press Start 2P', sans-serif">Lucky DS</span>
    <span class="block mb-2">Fullstack Javascript Engineer</span>
    <a href="tel:085156501865" class="text-xs">085156501865</a>
  </div>
</div>

### Tech Stack for this presentation

<div border="rounded" class="bg-white mt-2">
  <div class="flex justify-around p-5">
    <img src="/vue-logo.png" alt="vue" class="h-20 mx-2" title="vue"/>
    <img src="/slide_dev.png" alt="slidev" class="h-20 mx-2 " title="slidev"/>
    <img src="/cloudfare.png" alt="cloudfare" class="h-20 mx-2" title="cloudfare"/>
    <img src="/github.png" alt="github" class="h-20 mx-2" title="github"/>
    <img src="/vite.svg" alt="vite" class="h-20 mx-2" title="vite"/>
  </div>
</div>
