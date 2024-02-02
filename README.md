# reve-assignment

## Installation

Follow these steps to set up and run the project locally:

### Prerequisites

Make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) (Node Package Manager)
- [Vue.js] (npm install -g @vue/cli)
- [npm Json Server Package] (npm i json-server -g)

### An Overview of the assignment have been provided along with the files for convenience
Google Drive Link - https://drive.google.com/file/d/1yoki_H9BfwbQc0A-RjwSC8vV5djECVCK/view?usp=sharing

### Compiles and hot-reloads for development

We will need two terminals.
At first terminal, we will run the following to create our fake api 
to fetch dummy data from local storage
```
json-server --watch db.json
```

Then again in a new terminal run the following to start the project
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
