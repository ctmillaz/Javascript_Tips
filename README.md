# Javascript Logic

### Example of using javascript in html.
`function getLocation(location){
  if (location){
    return <p>Location: {location}</p>;  ## This line is a javascript function with html in it.  It also uses a location property of another variable with javascript inside curly braces.
  }
}`


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

`function getPetName(){
    const petName = 'Hal';
    return petName;
}`

`const petName = getPetName();  ## If define the function with a variable, you can then use petName in the console log, because it's in scope.
console.log(petName);`
### Ans: Hal


## **NOTE* var based variables are function scoped.  let/const are blocked scoped which includes functions.

### Example 3:
`if(fullName){
    var firstName = fullName.split(' ')[0]    ###Using var
    console.log(firstName);
}

console.log(firstName)`
### Ans: Cort
### Ans: Cort

### Example4:

`if(fullName){
    const firstName = fullName.split(' ')[0]   ##Using const or let
    console.log(firstName);
}

console.log(firstName)`
### Ans: Cort
### Ans: Invalid/Error      
### you can't use the variable outside the block if it is defined in the block


### Example5: The work-around for using let/const in the same way variable does.
`var fullName = 'Cort Yonder';
let firstName;                    ##Pull out the variable and don't define it.

if(fullName){
    const firstName = fullName.split(' ')[0]
    console.log(firstName);
}

console.log(firstName)`
### Ans:Cort
### Ans:Cort


------------------------------------------------------------------------------------------------------------------------------


# Arrows


### Defining a function
`const square = function (x) {
    return x * x;
}`

### Another syntax for the initial function
`function square (x) {
    return x * x;
}`


### Using arrows in that function.  This way is different and works, but isn't any more advantageous than the first way.
`const squareArrow = (x) => {
    return x * x;
}

console.log(squareArrow(9));`

### Differen way to use arrows, which is more advantageous because you don't need returns. The return is implicit.

`const squareArrow =(x) => x * x;

console.log(squareArrow(4));`


### Verbose example and example with return arrow function, but these use strings.

`const getFirstName = (fullName) => {
    return fullName.split(' ')[0];
}
console.log(getFirstName('Cort Yonder'));

const getFirstName2 = (fullName2) => fullName2.split(' ')[0];

console.log(getFirstName2('Cort Yonder'));`
