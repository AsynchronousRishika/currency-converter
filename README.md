# React + Vite



TODAYS LEARNING
/***************************************
CUSTOM HOOKS(made by us)
file path----
src-> customhook-> usecurrencyinfo.js


1. custom hook can use in-built hooks

2.  custom hook always return an array with at least one

3. custom hook  is a function that returns either an array or object

4. custom hook  are reusable and they make our code more modular, easy to understand and maintain

5. we can import the custom hook into any component and use it like normal variables

6. Custom Hooks must start with "use" followed by a capitalized word (camel  case).

7. api's humesa string format likhe hote hai.. so we have to parse it into JSON using JSON.parse() or json().

8. We need to call setData inside of useEffect because data is not available outside of useEffect .

9. If you want to run something only once then put it inside useEffect without dependency array.
  
   if you want to run it every time when some value changes then put it inside useEffect with dependency array.
10. 
we can directly use fetch() but we want whenwver currency  changes , new request should be made to fetch(), that can be done by using useeffect()

Example:-

function useCurrencyInfo( currency){
   useEffect( () =>{
    fetch(`https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/${currency}.json`)
    },[currency])
}


/*******************************************



Mounting refers to the process of creating a new component and adding it to the DOM.



/**********************************************
USEEFFECT

A side effect in programming refers to any change that a function or expression makes outside of its own scope.

For example, a function that modifies a global variable, writes to a file, or sends a network request all have side effects. 

In the context of React, side effects are often used to perform actions such as fetching data from an API, setting up event listeners, or manipulating the DOM. These actions are necessary for building complex user interfaces, but they can also introduce complexity and make the code harder to maintain.

To manage side effects in React, it's recommended to use the 'useEffect' hook. This hook allows you to perform side effects in a controlled and predictable way, by separating them from the component's render logic. 

By using 'useEffect', you can ensure that side effects are only executed when necessary, and that they don't interfere with the component's rendering behavior.



 
/*************************************
fetch() ----> takes the url  as argument, returns promise which resolves to response object.
           --> if there are any errors in the request ,then it rejects with the error object.

response.json()----> returns another promise and parsed the JSON to Javascript object.


the method being named json(), the result is not JSON but is instead the result of taking JSON as input and parsing it to produce a JavaScript object.


then((res)=>{res.json()})  - this will return another promise.
then() ---> takes the callback function as argument.

-------------------------------------------------------
 inputBox.jsx file

  {currencyOption.map((currency)=>(<option key={currency} value="usd">
                    usd
                   </option>))}

   [1. map()](https://www.w3schools.com/react/react_es6_array_methods.asp)  
   
   [ 2. map() and keys](https://legacy.reactjs.org/docs/lists-and-keys.html)   
--------------------------------------------------------
USEID HOOK





--------------------------------------------------------
<form
                        onSubmit={(e) => {
                            e.preventDefault();
                           
                        }
                    >
[preventdeafult()](https://www.w3schools.com/jsref/event_preventdefault.asp)
[onsubmit function](https://www.w3schools.com/tags/ev_onsubmit.asp)

--------------------------------------------------------


* i got stuck here  * 
Error: Objects are not valid as a React child (found: object with keys {label, amount, currencyOptions, onCurrencyChange, selectCurrency, onAmountChange}). If you meant to render a collection of children, use an array instead.

 error ocurred in line
 function InputBox(
    label,
    amount,
    onAmountChange,
    onCurrencyChange,
    currencyOption = [],
    selectCurrency = "usd",
    amountDisable = false,
    currencyDisable = false,
    className = "" )


   * here i forgot to use curly bracket 
    if want to render collections of childrens in react component then i have to pass it as a array *

    * solution *

    function InputBox(
    {label,
    amount,
    onAmountChange,
    onCurrencyChange,
    currencyOption = [],
    selectCurrency = "usd",
    amountDisable = false,
    currencyDisable = false,
    className = "" })


    * i got stuck where currency option was not showing in the selector , so the problem is  where i got stucked , i wrote currencyOptions props which  i was passing in child component present in App.jsx, is different to the currencyOption props present in react component (in InputBox.js)   .jbki child componet mai jis naam s bhejte h props ussi naam s react component ya parent component  mai props likhte hai *  

   * after correcting the name  currencyOptions to currencyOption ..options selctor mai dikhne lge phir#   c u r r e n c y - c o n v e r t e r 
 
 #   c u r r e n c y - c o n v e r t e r  
 