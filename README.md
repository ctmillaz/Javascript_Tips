# Javascript Logic

### Example of using javascript in html.
`function getLocation(location){
  if (location){
    return <p>Location: {location}</p>;  ## This line is a javascript function with html in it.  It also uses a location property of another variable with javascript inside curly braces.
  }
}
`


## tertiary logic

`<boolean> ? '<Is your variable this, pass and use> :  < If it wasn't the other variable, use this one>`
### Example:
`true ? 'Chad': 'Anonymous`
### Ans: Chad


`<boolean> ? '<If this isn't your variable, pass and use> :  < If this is the variable, then use>`
### Example2:
`false ? 'Chad': 'Anonymous`
### Ans: Anonymous

`<variable> ? '<Is your variable this, pass and use> :  < If it wasn't the other variable, use this one>`
### Example3:
`Chad ? Chad : 'Anonymous'`
### Ans: Chad

`<p>{appObject.options.length > 0 ? 'Here are your options': 'No options'}</p>`         
### curly braces inside p tags
### Example4:



## Logical "&&" Operator

`true && <string>`
### Both need to be true for the string to show up.
### Example:
`true && 'Some age'`
### Ans: Some age

### Example2:
`false && 'Some age'`
### Ans: false

### Example 3:
`{user.age >= 18 && <p>Age: {user.age}</p>}` 
### Everything is surrounded by curly braces to use javascript.  And has html tags inside.
### Example 1:
`17 >= 18 && <p>Age: 17</p>`
### Ans: blank, because the 17 is less than 18, so the p tags can't be shown...both sides are not true.

### Example 4:
`18 >= 18 && <p>Age: 18</p>`
### Ans: Age: 18

### Example 5:
`{(user.age && user.age >= 18) && <p>Age: {user.age}</p>}`
### This checks if there is age, and then if the user is 18 or older, then if both are true...the p tags are placed.



-------------------------------------------------------------------------------------------------------------------------------
# ES6

## **NOTE** You should only use const and let.  Never var.



## var can be changed by renaming variables or using the same reference with a new variable.

### Example1:
`var nameVar = 'Andrew';
nameVar = 'Mike';
console.log('nameVar',nameVar);`
### Ans: nameVar Mike

`var nameVar = 'Andrew';
var nameVar = 'Mike';
console.log('nameVar',nameVar);`
### Ans: nameVar Mike


## let is the same as var in that you can rename a reference, but you can't redefine with same reference

`let nameLet = 'Jen';
nameLet = 'Julie';
console.log('nameLet', nameLet);`
### Ans: Julie

`let nameLet = 'Jen';
let nameLet = 'Julie';
console.log('nameLet', nameLet);`
### Ans: Error/Invalid

## const is similar to a final in java.  You can't change a refence to a new variable and you cand redefine.

`const nameConst = 'Frank';
nameConst = 'Gunther';
console.log('nameLet', nameConst);`
### Ans: Invalid

`const nameConst = 'Frank';
const nameConst = 'Gunther';
console.log('nameLet', nameConst);`
### Ans: Invalid




## Scope:   var, let, and const are the same for scope.

### Example:
`function getPetName(){
    var petName = 'Hal';  ## var/let/const
    return petName;
}

getPetName();
console.log(petName);  ## can't find petName, because it is embedded in the function.`
### Ans: Invalid



### Example2:
`
function getPetName(){
    const petName = 'Hal';
    return petName;
}
`

`const petName = getPetName();  ## If define the function with a variable, you can then use petName in the console log, because it's in scope.
console.log(petName);
`
### Ans: Hal


## **NOTE* var based variables are function scoped.  let/const are blocked scoped which includes functions.

### Example 3:
`
if(fullName){
    var firstName = fullName.split(' ')[0]    ###Using var
    console.log(firstName);
}

console.log(firstName)
`
### Ans: Cort
### Ans: Cort

### Example4:
`
if(fullName){
    const firstName = fullName.split(' ')[0]   ##Using const or let
    console.log(firstName);
}

console.log(firstName)
`
### Ans: Cort
### Ans: Invalid/Error      
### you can't use the variable outside the block if it is defined in the block


### Example5: The work-around for using let/const in the same way variable does.
`
var fullName = 'Cort Yonder';
let firstName;                    ##Pull out the variable and don't define it.

if(fullName){
    const firstName = fullName.split(' ')[0]
    console.log(firstName);
}

console.log(firstName)
`
### Ans:Cort
### Ans:Cort


------------------------------------------------------------------------------------------------------------------------------


# Arrows


## Defining a function
`
const square = function (x) {
    return x * x;
}
`

### Another syntax for the initial function
`
function square (x) {
    return x * x;
}
`


### Using arrows in that function.  This way is different and works, but isn't any more advantageous than the first way.
`
const squareArrow = (x) => {
    return x * x;
}

console.log(squareArrow(9));
`

### Differen way to use arrows, which is more advantageous because you don't need returns. The return is implicit.
`
const squareArrow =(x) => x * x;

console.log(squareArrow(4));
`


### Verbose example and example with return arrow function, but these use strings.
`
const getFirstName = (fullName) => {
    return fullName.split(' ')[0];
}
console.log(getFirstName('Cort Yonder'));

const getFirstName2 = (fullName2) => fullName2.split(' ')[0];

console.log(getFirstName2('Cort Yonder'));
`


--------------------------------------------------------------------------------------------------------------------------------

# Arrows Part 2

## **NOTE** With these new ES5 and ES6 syntax there is no need to use the keyword function if you know the correct syntax. It's like var, where just not needed anymore.

### Example:
`
const add = function (a,b) {
    console.log(arguments);
    return a + b;
};
 
console.log(add(55, 1));
`  
### if you add in an additional number it will still come up in the arguements even though the parameters are only a and b.
### 55 and 1 show up in the developer tools with console.log(arguements
###Ans: 56


## Using arrows for the same function
### Example2:

`
const add = (a,b) => {
    console.log(arguments);
    return a + b;
};
 
console.log(add(55, 1, 1001));
`
### Ans: Invalid/Error     
### This is becaue we are using arrows now, and arguments does not work in arrows any longer



## Using this keyword

### Example:
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived: function () {
        console.log(this.name);   
### this.<property> allows you to use any property that was made available in the object.
        console.log(this.cities);

        this.cities.forEach(function(city) {

        });
    }
};

user.printPlacesLived();
`


### Example 2: 
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived: function () {
 `
 ### Declared property, so the keyword this works.
 `
        console.log(this.name);
        console.log(this.cities);

        this.cities.forEach(function(city) {
`
 ### Anonymous function because it's not a declared property
 `
            console.log(this.name + ' has lived in ' + city)
        });
    }
};

user.printPlacesLived();
`
### Ans: Invalid/Error   
### This is because the foEach function is trying to use this.name and this is not able to be used in an anonymous function.


### Example3: The work around for not being able to use this.
 `
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived: function () {	                          
        const that = this;
`
### Define reference that is equal to this.
`
        this.cities.forEach(function(city) {                      
            console.log(this.name + ' has lived in ' + city)
        });
    }
};
`
### Ans: Cort has lived in Taiwan, etc, etc.


### Example4: Arrow function version.  Benefits are the arrow function doesn't bind its own this value so you can use this in your return.
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived: function () {
        this.cities.forEach((city) => {
`        
### remove function and add arrow
`
            console.log(this.name + ' has lived in ' + city)
        });
    }
};
`
### Ans: Cort has lived in Taiwan, etc, etc.

### Example5: When not to use Arrow functions.
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived: () => {
`
### remove function and add arrow here and you get Invalid, because arrow functions don't bind thier own this value.  It's no longer equal to it's value and goes up to the parent scope, which looks for this in the global scope or inital variables you created at the root level of the file.
`
        this.cities.forEach((city) => {                        
            console.log(this.name + ' has lived in ' + city)
        });
    }
};
`
### Ans: Invalid

### Example 6: How to fix that previous statement to work.  We need to remove the initial arrow statement
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
`
### We removed the colon and arrow and this is valid.
`
        this.cities.forEach((city) => {
            console.log(this.name + ' has lived in ' + city)
        });
    }
};
`
### Ans: Cort has lived in Taiwan, etc, etc.


----------------------------------------------------------------------------------------------------------------------------------



# Using map instead of forEach

### **NOTE** Map does not affect the initial array at all.
### function gets called one time for each item in the array like forEach. We have access to that item in the first arguement.  
### ForEach just lets you print items out to the screen. Map allows you to tranform each item and give you a new array back. 
### forEach version
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
        const cityMessages = this.cities.map((city) => { 
            return city;
        });

        this.cities.forEach((city) => {
            console.log(this.name + ' has lived in ' + city)
        });
    }
};

user.printPlacesLived();
`


### Explaining what map can do(Simple Example):
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
        const cityMessages = this.cities.map((city) => {
            return city + '!';
`          


### Allows you to add on to the existing return.
`
        });

       return cityMessages;
    }
};

console.log(user.printPlacesLived());
`


### Explaining what map can do(Experienced Example):
### Allows you to add on to the existing return.
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
        const cityMessages = this.cities.map((city) => {
            return this.name + ' has lived in ' + city + '!';
        });

       return cityMessages;
    }
};

console.log(user.printPlacesLived());
`



### Explaining what map can do(More Experienced Example):
### Remove const and city Messages
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
        return this.cities.map((city) => {
`        
### Remove const and city Messages
`
            return this.name + ' has lived in ' + city + '!';
        });
    }
};

console.log(user.printPlacesLived());
`


### Explaining what map can do(Final Cleaned up Example):
### Cleaned up version
`
const user = {
    name: 'Cort',
    cities: ['Taiwan', 'Tahiti', 'Port of You'],
    printPlacesLived() {
        return this.cities.map((city) => this.name + ' has lived in ' + city + '!');
    }
};

console.log(user.printPlacesLived());
`

### Example of map with numbers:
`
const multiplier = {
    numbers: [ 4, 7, 8],
    multiplyBy: 2,
    multiply () {
        return this.numbers.map((number) => number * this.multiplyBy);
    }
};

console.log(multiplier.multiply());
`


-----------------------------------------------------------------------------------------------------------------

## Classes1

### An example of a class
`
class Person {
    constructor(name = 'Anonymous') {
        this.name = name;
    }
    getGreeting(){
        //return 'Hi. I am ' + this.name + '!';
        return `Hi. I am ${this.name}!`
    }
}
`

### Notice the $ in the return statement.  This is ES6 template strings.  You need to use backtick instead of apostrophe.
### You can then add in a template from the constructor by using ${this.<variable>} or you can just use a static string like normal.


-----------------------------------------------------------------------------------------------------------------------------

# Class2

### An empty string is called a falsy value, and would fail an if condition
` '' `

### Flip it using a logical NOT
`!''`
#### Solution: true


### The logical NOT works similar to an on and off switch.  If you do a logical NOT twice you receive false again.
`!!''`
#### Solution: false


### A string with a value is called a truthy value.  If you do two logical NOT's they will void each other, but give you a boolean.
`!!'myname'`
#### Solution: true


### Undefined works the same as having no string
`!!undefined`
#### Solution: false 

--------------------------------------------------------------------------------------------------------------------------------
# React Components 

### They are just ES6 classes that extend something React gives us.

### In React your class has to be an upper case first character.

### A React Component must define a render function
