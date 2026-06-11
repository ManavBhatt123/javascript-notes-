scope hai ke aap apne created variables and functions kaha tak use kar sakte hai 

functional scope -functions ke andar he use ho sakti hai 
global scope - pure coded kahi bhi use ho sakti hai 
block scope - {} mai he use ho sakti hai 


execution content 

js sabse pehle jaisa hi aapka function dekhta hai sabse pehle 
js baanta hai execution context , ye ek process hai jo ko do different phases mein chahta hai , memeory phase doorse ka naam hai execution phase 


js - lexical scoping 
ki aap kaha par physically available ho ye poori tareeke se depend karta hai ki aap kya access kar paaoge 

dynamic scoping 
dynamic scoping mai scoping, variable ka scope runtime pe decide hota hai , based on function call kisne kiya 

function ko call karne wala decide karega variable 


closures 
closures hota hai functions jo kisi parent function ke andar ho aur andar wla function return ho raha ho and returningfunc use kare , parent function ka koi variable 

faayde nuksaan par 
1) private variable
2) global pollution 


ye sach hai fnc ke khatam hone pe aapka fnc and uske varibles 
khtm hojaate hai , par jab bhi closures banta hai to aapka fnc aur uske variables ka ek backlink bnaya jaata hai aur uska naam hota hai [[environment]]


this keyword is the special keyword hai 

oops in js 
1) constructor - It is just normal function , but it is used to create the new objects.

2) new creates new object , sets this in it , links to constructors prototype and returns the obejct automatically. 

3) Prototype is an object from which other objects inherit properties and methods.


extend is used to create a child class from a parent class. 

super is used to call the parent class.

super has two main uses:
(1) call the parent parameter 
(2) call a parent method 
 
