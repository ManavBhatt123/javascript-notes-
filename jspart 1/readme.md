(1) Variables and Declaration 

declaration and initialization

var a ;( declare kara sirf )
var a = 12;(declare ke sath humne usse initial bhi kar diya)

initialization ka mtb hota hai pehle bar usko inital karna 

var - 1) var window mai add hota hai 
      2) var functions scoped hota hai 
      3) var ko hum redeclare kar sakte hai 

hume inn sab problem se bachna hota hai isliye hum let ka use karte hai 
    
const hum tab use karte hai , jab hume value ko fix karna hota hai , var or let mai hum value ko change kar sakte hai .
const mai hum reassign nhi kar sakte par hum us value ke kuch part ko change kar sakte hai 


(2) scope ( global , block , functional)

global  scope ka mtb hum usse kahi bhi use kar sakte hai


block scope
{

}
var block scope nhi hota hai mtb hum var ko block scope ke andar rakhe toh hum usse scope ke bahar bhi use kar sakte hai 

par let block scope hota hai , jo bhi uske andar declare hoga hum usse block scope ke bahar use nhi kar sakte .


functional scope 

var ko functional scope hota hai , hum usse function ke andar kahi bhi use kar sakte hai , agar hum usse kisi block ke andar bhi likh de fhir bhi voh pure function mai use ho sakta hai 
 
let functional scope nhi hota hai , agar hum usse function ke andar kisi block ke andar declare kare toh sirf voh use block tak valid hai voh pure function mai use nhi hoga 



reassignment - we can reassign the value of same variable again 
        var a = 12;
        a = 42;

        let p = 23;
        p = 23;

redeclaration - we can redeclare the variable but we can do this with var but not with let 



temporal dead zone -> utna area jitne mai js ko pata to hai ki variable exist karta hai par voh apko value nhi de sakta


hoisting impact per type -> jab js mai ek variable banata hai toh voh do hisso mai didvide ho jata hai ek uska declare jo upar chala jata hai or ek uska initialize part jo neeche reh jata hai 



datatypes

primtive datatype -> aisi saari values jinko copy karne par tumhe ek real copy mil jaaye

Example of primitive -> string, number, boolean,null ,defined,symbol,bigint

null ka mtb hai aapne jaan boojh kar koi value nhi di.

undefined ka mtb ki aapne ek variable banaya aur usey value nhi di to jo value by default wo hai undefined . 

symbol ka main kaam hai unique value banana
mtb agar do symbol kabhi same nhi hote , chahe unka naam same bhi ho




reference datatype -> inko copy karne par copy ke real value nhi milti par uska refernce milta hai .

example of reference -> arrays , objects, functions

dynamic typing -> js mein static typing nhi hota yaha par dynamic typing hota hai iska mtb hai ke aap data ko change kar sakte ho .

quirks -> unexpected behavior jo lanaguage mai present hai uske language ke design ke time se 

type coercion -> concept jismein aapka ek type atomatically convert ho jata hai . 

truthy and falsy value -> 
0  false  ""  null   undefined  NaN document.all   -> yeh falsy value hai 
baki sari value truthy value hai 




operators
1) arithmetic operators -> +,-,*,/,%,**
2) comparison -> comparsion -> = == === != !== >= <= > < ( = sign mean to assign value to variable ), (== sign check the value is equal or not but not strict checking , for example 12=='12'//true , but it should be false one is number and other one is string ),( === it do the strict checking 12 === '12'//false) , ( != check the value is not equal to other value , but not do strict checking ),(!== it do the strict checking )
3) assignment -> = += -= *= /= %= 
4) logical -> && || !
5) unary -> + - ! typeof ++ -
5) ternary -> ?:




control flow 
1) if else else-if
2) switch case
3) early return pattern 


loop 
for , while , do-while

break and continue 

break mai kya hota hai loop chalta aur jaha likha hai break at this number 
voh waha se aage nhi jata chahe uska end point baad mai ho 

continue mai kya uss number pe jaha continue likh usko leave karke baki sab print hota hai 



functions 

function declaration -> jab hum function ko declare karte hai by using the keyword function 

function expression -> jab hum function ko ek variable ek andar store karte hai .

arrow function -> cleaner and shorter way to write a function using => syntax.


default -> when we give default to parameter which function use if no arguments is pass 

first class function -> hum function ko value ke tarah treat karte hai 

pure function -> aisa function jo bahar ke value ko change na kare voh hai pure function .
impure  function -> aisa function jo bahar ke value ko change kare voh hai impure function .

closure -> ek function jo return karega ek function or return hone wala function use karega parent func ka koi variable 

lexical scoping -> function ke variable ka scope , code likhne ke jagha se decide hota hai , run time se nhi 

iife -> function ko define karte hi turant call kar dena 

hoisting in function declaration -> we can do hoisting in function declaration 

hoisting in function expression -> we cannot do hoisting in function expression 