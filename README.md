# Front End Code Exam

1. What is the value of b?

```javascript
let a = 1;
let b = a;

b = 1;
a = 2;

console.log(b);
```

2. What is the value of b.name?

```javascript
let a = { name: "John Doe" };
let b = a;

b.name = "John Wick";
a.name = "Johnny English";

console.log(b.name)
```

3. What is the value of state?

```javascript
function useState (initialValue) {
    let _val = initialValue;
    
    function setState(newVal) {
        _val = newVal
    }
  
  return [_val, setState]
}

const [state, setState] = useState(1)

setState(5);
setState(10);

console.log(state)
```

4. If the button clicked 3 times, what will be the final value of state?

```javascript   
import { useCallback, useState } from "react";

const Component = () => {
  const [state, setState] = useState(1);

  const handleClick = useCallback(() => {
    setState(state + 1);
  }, []);

  return (
    <>
      <div>{state}</div>
      <button onClick={handleClick}>Click Me!</button>
    </>
  );
};
```

5. What is the final value of count?

```javascript   
import { useCallback, useEffect, useState } from "react";

const Component = () => {
  const [count, setCount] = useState(1);

  const incrementCount = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []);

  useEffect(() => {
    const timer = setTimeout(() => {
      if (count < 5) {
        incrementCount();
      }
    }, 1000);

    return () => clearTimeout(timer);
  }, [incrementCount]);

  return <div>{`Timer started: ${count}`}</div>;
};
```

6. What is the value of car.getModel()?

```javascript
const car = {
    model: "Toyota",
    getModel: () => {
        return this.model || "Unknown"; 
    }    
};
 
console.log(car.getModel());
```

7. What is the value of person.getName()?

```javascript
const person = {
    firstName: "John",
    getName: function () {
        return this.firstName ? this.firstName + " Wick" : "John Doe" ; 
    }    
};
 
console.log(person.getName());
```

8. What is the output of console.log?

```javascript
const greet = (str1) => (str2) => `${str2 || ""} ${str1 || ""}`;
const greetMessage = greet("Good Morning");

console.log(greetMessage("Hello"));

```

9. What text will be displayed last in the console?

```javascript
function f1() {
	console.log("execute f1")
}

function f2() {
	console.log("execute f2")
}

function f3() {
	console.log("execute f3")
}

function f4() {
	console.log("execute f4")
}

f1()
setTimeout(() => f3(), 0)
setTimeout(() => f2(), 0)
f4()

```

10. What is the output of console.log?

```javascript
function displayer(result = 1) {
  return result
}

function calculator(num1, num2) {
  let sum = num1 + num2;
  return sum;
}

const result = calculator(5, 5);
console.log(displayer(result));

```

