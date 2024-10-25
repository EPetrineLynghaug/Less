# Lecture notes, Less A Test Project 

This project demonstrates the use of dynamic CSS preprocessors, specifically LESS and SASS, within a simple web development environment. The aim is to compare the capabilities, syntax, and performance of these preprocessors and understand when to use each one.

## Table of Contents
 1.	Introduction
 2.	Languages and Tools Used
 3.	Installation
 4.	Comparison: LESS vs. SASS
 5. Syntax Differences
 6. Mixins
 7. Nesting and Parent Selectors
 8. Functions
 9. Variable Scope
 10. Interpolation
 11. Performance and Debugging
 12. Conclusion: When to Choose LESS or SASS
 13. Running the Project

## Introduction

LESS and SASS are CSS preprocessors that add functionality such as variables, mixins, functions, and nested rules to regular CSS. They allow developers to write more maintainable and DRY (Don’t Repeat Yourself) code.

Both preprocessors require compiling the .less or .scss files into standard .css that browsers understand. This project will guide you through setting up a basic environment using both LESS and SASS, and demonstrate their features through practical examples.

Languages and Tools Used
•	CSS Preprocessors: LESS, SASS
•	Node.js and NPM: For managing dependencies and running scripts
•	JavaScript: Used for configuring build scripts
•	HTML/CSS: To test and display compiled styles

## Installation

### Setting Up LESS

1.	Install LESS as a dev dependency:
 ```bash
    npm install less --save-dev
 ```

 2.	Create a build script in package.json:
 ```json
    "scripts": {
        "build-css": "lessc src/less/styles.less dist/styles.css"
    }
  ```   

3.	Run the build script:
 ```bash
    npm run build-css
  ``` 

### Setting Up SASS
1.	Install SASS as a dev dependency:
 ```bash
      npm install sass --save-dev
 ```

2.	Create a build script in package.json:  
 ```json  
     "scripts": {
        "build-sass": "sass src/sass/styles.scss dist/styles.css"
        }  
 ```    

3.	Run the build script:
 ```bash
     npm run build-sass
```       


### Comparison: LESS vs. SASS

Syntax Differences
• LESS: Uses @ for variables.
 ```LESS
    @primary-color: #333;
 ```

 •	SASS: Uses $ for variables.
 ```scss
    $primary-color: #333;
  ```

### Mixins

Mixins allow you to define reusable chunks of code. 
 •	LESS:
 ```Less
    .rounded-corners(@radius: 5px) {
    border-radius: @radius;}
    .button {.rounded-corners(10px);
    }
 ```
 •	SASS:
 ```scss

    @mixin rounded-corners($radius: 5px) {
     border-radius: $radius;
    }
    . button {
    @include rounded-corners(10px);
    }
 ```

### Nesting and Parent Selectors

LESS: Supports basic nesting.
```Less
    .nav {
  ul {
    margin: 0;
     }
    }
```
•	SASS: Supports advanced nesting using &.
```scss
    .nav {
  ul & {
    margin: 0;
  }
}
```

### Functions

•	LESS: Has a limited set of built-in functions.
```LESS
    @base: 5%;
    .class {
    width: @base * 2;
    }
```
•	SASS: Has more built-in functions for color manipulation and other utilities.
```sass
    $base: 5%;
    .class {
    width: $base * 2;
    }   
```

### Variable Scope

•	LESS: Allows variables to be scoped within blocks.
•	SASS: Variables are always global by default but can be made local using !default.

### Interpolation

•	LESS:
```LESS
    @size: large;
    .icon-@{size} {
    width: 100px;
    }
```
•	SASS:
```scss
    $size: large;
    .icon-#{$size} {
    width: 100px;
    }
```
### Performance and Debugging

#### Performance

•	LESS: Compiles using JavaScript. This can make it slower compared to Dart SASS.
•	SASS: When using Dart SASS, it’s faster than older Ruby or Node SASS implementations.

#### Debugging

•	LESS: Error messages can be difficult to understand, making debugging harder.
•	SASS: Provides clearer error messages and debugging options.

### Conclusion: When to Choose LESS or SASS

•	LESS: Great for small projects or when you need a lightweight CSS preprocessor. It is easier to learn if you’re already familiar with CSS.
•	SASS: Ideal for larger projects that require more advanced features, such as complex functions, modular imports, and extensive variable manipulation.

In conclusion, while LESS is simpler and may be preferable for small-scale projects, SASS provides a richer set of features that make it more suitable for larger applications where maintainability and advanced styling capabilities are essential.

## Running the Project
```bash
	1.	Clone the repository:
    git clone https://github.com/EPetrineLynghaug/personalportfolio.git
    2.	Install dependencies:
    npm install
     	3.	Build CSS with LESS:   
        npm run build-css
        	4.	Build CSS with SASS:
            npm run build-sass
```
