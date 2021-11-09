﻿# Front End Code Exam

1. What is the value of b?

```javascript
let a = 1;
let b = a;

b = 1;
a = 2;

console.log(b);
```

What is the value of b.name?

```javascript
let a = { name: "John Doe" };
let b = a;

b.name = "John Wick";
a.name = "Johnny English";

console.log(b.name)
```

What is the value of state?

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

If the button clicked 3 times, what will be the final value of state?

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

What is the final value of count?

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

What is the value of car.getModel()?

```javascript
const car = {
    model: "Toyota",
    getModel: () => {
        return this.model || "Unknown"; 
    }    
};
 
console.log(car.getModel());
```

What is the value of person.getName()?

```javascript
const person = {
    firstName: "John",
    getName: function () {
        return this.firstName ? this.firstName + " Wick" : "John Doe" ; 
    }    
};
 
console.log(person.getName());
```

