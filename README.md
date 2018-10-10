# Javascript_Tips

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

`<p>{appObject.options.length > 0 ? 'Here are your options': 'No options'}</p>`         ### curly braces inside p tags
### Example4:



## Logical And Operator

`true && <string>`
### Both need to be true for the string to show up.
### Example:
`true && 'Some age'`
### Ans: Some age

### Example2:
`false && 'Some age'`
### Ans: false

### Example 3:
`{user.age >= 18 && <p>Age: {user.age}</p>}` ###Everything is surrounded by curly braces to use javascript.  And has html tags inside.
### Example 1:
`17 >= 18 && <p>Age: 17</p>`
### Ans: blank, because the 17 is less than 18, so the p tags can't be shown...both sides are not true.

### Example 4:
`18 >= 18 && <p>Age: 18</p>`
### Ans: Age: 18

### Example 5:
`{(user.age && user.age >= 18) && <p>Age: {user.age}</p>}`
### This checks if there is age, and then if the user is 18 or older, then if both are true...the p tags are placed.





