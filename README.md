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

here below we made another change <br>

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

```await``` keyword can only be used inside asynchronous function <br>


In most of the cases we will be working with asynchronous function because  when we deploy a contract <br>
we have to wait until the contract is deployed <br>

if we don't use asynchronous function it means we are not waiting until the contract is deployed <br>

we ahve also made following changes in the code below:

```javascript

async function main() {
  console.log("Khatami");

  let variable = 5;
  console.log(variable);
}

main()
  .then(() => process.exit(0))
  .catch((error) => {
    console.error(error);
    process.exit(1);
  });

```


We have add the following in the code above:


```javascript

main()
  .then(() => process.exit(0))
  .catch((error) => {
    console.error(error);
    process.exit(1);
  });

```

it some syntax wailting for it basically finish and returns an error if it gets <br>



![f2](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/fa2f251a-2da7-4d39-a356-3177f6f1011c)
figure2: in order to compile our solidity code into our javascript project we need to install solc-js <br>
for that we have to visit this link https://github.com/ethereum/solc-js

![f3](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/df848880-e2ca-4d2a-b3c2-8779585772f5)

Figure3: while we install Node.js , npm(node package manager) is automatically installed <br>

It is a library and registry for javascript software packages <br>
The registry contains over 800,000 code packages.Open-source developers use npm to share software.<br>
Many organizations also use npm to manage private development.<br>

![f4](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/3d27d346-7789-4805-b34d-50dd42965475)
Figure4: Another thing also gets installed and thatis corepack <br>

![f5](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/c44632f7-a853-4833-81a0-0c8e280f1f24)

Figure5: Another way to include solidity is by going to thsu link https://classic.yarnpkg.com/en/docs/getting-started <br>

![f6](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/e2411b4e-be28-46f2-8375-def38c15d894)

Figure6: Use quotes (double or single) to go to the folder or path contains white spaces or special symbols.<br>


![f7](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/ab969e79-f76f-4c27-9f79-ce2314ef9176)

Figure7: We have to open powershell as administrator and run the command ```corepack enable``` <br>
after that if we typed ```yarn --version``` the above error will be displayed <br>

![f8](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/61929292-56ac-4b0b-84b0-3923693c5ebb)

Figure8: to solve the problem we have to use the above command and thus we see the version number of yarn <br>

![f9](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/2c7b3f14-a410-41d2-b1a2-365d9db9e75d)

Figure9: To add solidity compiler we add the above commands shown with position number <br>

![f10](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/a53a3a2d-9998-4e2b-857a-ba631ccb05ed)

Figure10: it automatically added package.json folder , it talks lot about our project and the dependncies it works with<br>

![f11](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/4eedc8b9-b827-4de2-8496-75cd37eb1fe9)

 Figure11: yarn.lock tells us the exact version of the package of our project <br>
 
![f12](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/0828067f-3099-44f8-9668-defe74f333f4)

Figure12: here node modules folder is going to be all the installed code we have downloaded <br>

![f13](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/72165b4e-65f0-4007-81de-9b658b0b2958)

Figure13: here is a ```solc``` folder where it contains all the code associated with solc package that we have installed <br>

![f14](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/88afbe36-3deb-43bd-b814-4be2b8f92329)

Figure14: to add version 0.8.7 we ahve to give the above command <br>

![f15](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/796a1515-8580-444d-bd20-7933acf0fad2)

Figure15: In our pacakge.json file we can see 0.8.7 is fixed <br>


 We can compile our smart contract in code and have it automatically run when we deploy them <br>

 We can compile them separately <br>

 Here we gonna compile our contract separately using solc js command <br>

 yarn command can be used to install dependencies and can be used to run commands <br>

 ![f16](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/6c8c6bf8-6445-4028-988b-f5398363b6d2)

Figure16: if we want to see all the command that solc.js allow we run the above command <br>

![f17](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/a0495465-7388-47bd-a41d-acd710ecd131)

Figure17: If we want to check the version then we write the above command <br>

![f18](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/bd998da5-61b9-438d-870a-15408d4d574a)

 Figure18: to compile our solidity smart contract we have to give the following command <br>

 ```yarn solcjs --bin --abi --allow-paths node_modules/ --base-path . -o . akrkSimplestorage.sol``` <br>

Here in the above :

```yarn solcjs```: This is the command to run the solcjs executable using Yarn. solcjs is the Solidity compiler provided by the Solidity team.<br>

```--bin```: This option tells the Solidity compiler to generate binary bytecode for the smart contract. The binary bytecode represents the<br>
executable code that can be deployed to the Ethereum network.<br>

```--abi```: This option instructs the Solidity compiler to generate the Application Binary Interface (ABI) for the smart contract. <br>
The ABI is a JSON representation of the contract's functions and their input/output parameters, which is used for interacting with the <br>
contract.

```--allow-paths node_modules/:``` This option specifies the path(s) where the Solidity compiler should look for imported Solidity files.<br>

In this case, it indicates that it should search for imports in the node_modules/ directory.<br>

```--base-path period``` means that base path gonna be in thsi folder ```E:\akrkethjs\akrkethers-simple-storage``` <br>

```-o period``` means we gonna compile binary and abi to this folder  ```E:\akrkethjs\akrkethers-simple-storage``` <br>

![f19](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/0a6d30a7-3521-43ea-b637-ba6840c56789)

 Figure19: here we get abi(application binary interface) of our contract <br>

 ![f20](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/5b8b8024-d390-412a-927b-433b0327b725)

Figure20: then we get the binary or the low level format of our code <br>

![f21](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/a81139c0-ccb4-42d3-a08c-a086ae775c48)

Figure21: If we click the upper arrow button of the keyboard by selecting the console <br>

![f22](https://github.com/C191068/Ali-Khatami_Ether.Js3/assets/89090776/46bf7e5c-4794-4d5c-a4d4-666e6e99b0ef)

 Figure22: We can get the recent command of the console <br>

 


