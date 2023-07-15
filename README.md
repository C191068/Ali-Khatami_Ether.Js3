# Ali_Khatami_Ether.JS3

### Tiny JavaScript Refresher

```javascript

console.log("Khatami");

```

it will print the following
![e59](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/f53a93da-7537-4121-9817-ba575a158e9c)
Figure1: After writing the above code in our .js file when we typed ```deploy akrkdeploy.js``` at terminal<br>
 it will print the above <br>

 Here we have use the word ```node``` means we want to run the above javascript code using node.js <br>
 ```node``` is used for running backend Javascript code <br>

 ```uint256 variable =5``` in Solidity is same as that of ```let variable = 5``` of Javascript <br>

```javascript

console.log("Khatami");

let variable = 5;

console.log(variable);

```


The above code will print the following:

 ![e60](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/0b220d97-529c-4c55-9c84-d73a01badd60)
 Figure2: When we click ```node``` then clik ```ak``` then click the ```Tab``` button and click ```Enter``` button


 ```javascript

function main() {
  console.log("Khatami");

  let variable = 5;

  console.log(variable);
}

```

the above code will give the following no output


 ![e61](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/81842b5c-ca26-4def-93d8-f0a08ec918d6)

 Figure3: It is because we have wrapped the whole code in a function and want something to call the function <br>

 ```javascript

function main() {
  console.log("Khatami");

  let variable = 5;

  console.log(variable);
}

main();

```

the above code will give the following output <br>



 ![e62](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/18977172-bdfd-43ea-b28f-59ab90088b7d)

Solidity is an example of ```synchronous``` programming language but there will be some exceptions when <br>
working with Oracles <br>



Synchronous programming language means where one line gets executed one after another <br>

 ```javascript

function main() {
  console.log("Khatami");

  let variable = 5;

  console.log(variable);
}

main();

```


In the above code after calling of the ```main()``` function other lines of code gets executed one after another <br>


Javascript is an asynchronous programming language because while waiting for one line code to get executed<br>
we can have another code to get executed <br>

example of synchronous programming throug a sentence:

Mr Ali have arrnge dinner party by inviting frinds in his house. His mother is cooking fried chickens.<br>
Until the fried chicken is cooked he waits. Then he pour drinking water from bottle to glass. 
Then serve the food and start<br>
the dinner party <br>


example of asynchronous programming throug a sentence:

Mr Ali have arrnge dinner party by inviting frinds in his house. His mother is cooking fried chickens.<br>
He does not wait until the fried chicken is cooked thus he pour drinking water from bottle to glass.<br>
After the fried chicken is cooked <br>
Then serve the food and start<br>
the dinner party <br>



![f1](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/ac7ce9fc-b5be-4cec-a24a-14d80f1af8df)
Figure1: We have created a new file ```akrkparty.js``` to deploy the above code <br>


the code is given below:

```javascript

//Arrange Dinner party
//Cook Fried Chicken
//Pour Water
//Start party

function arrangedinnerparty() {
  cookfriedchicken();
  pourwater();
}

```


```javascript


//Arrange Dinner party
//Cook Fried Chicken
//Pour Water
//Start party

function arrangedinnerparty() {
  cookfriedchicken();
  pourwater();
}

function cookfriedchicken() {
  return Promise();
}

```




If any of the function inside ```function arrangedinnerparty()``` suppose ```cookfriedchicken()``` return Promise like above <br>

we have to tell our code to wait until the the fried chicken is fully cooked <br>

```javascript

//Arrange Dinner party
//Cook Fried Chicken
//Pour Water
//Start party

function arrangedinnerparty() {
  let status = cookfriedchicken();
  pourwater();
}

function cookfriedchicken() {
  return Promise();
}

```

We have set status to ```cookfriedchicken()``` function , if the chicken is being cooked the status is pending<br>

if the cooking of the fried chicken is finished , the status is fulfilled <br>

if the gas stove explode for any reason the status is rejected <br>

here below we gain change our code :

```javascript 

//Arrange Dinner party
//Cook Fried Chicken
//Pour Water
//Start party

function arrangedinnerparty() {
  cookfriedchicken();
  pourwater();
  startparty();
  
}

function cookfriedchicken() {
  return Promise();
}


```

In the above code ```startparty()``` function will only be called if the ```cookfriedchicken()``` and ```pourwater()``` <br>

have been executed <br>

here below we amde another change <br>

```javascript

//Arrange Dinner party
//Cook Fried Chicken
//Pour Water
//Start party

async function arrangedinnerparty() {
  await cookfriedchicken();
  await pourwater();
  startparty();
}

function cookfriedchicken() {
  return Promise();
}


```

here we made ```function arrangedinnerparty()``` function to asynchronous function and then use ```await``` keyword <br>

```await``` keyword tells any ```Promise``` based function to wait until the ```Promise``` is fulfilled or rejected <br>






 



 

 
 


