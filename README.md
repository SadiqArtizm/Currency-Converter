import inquirer from "inquirer";


let Convertion = {
    "PKR":{
        "USD": 0.0044,
        "POUND" : 0.0037,
        "PKR": 1

    },
    
        "POUND":
        {
            "USD": 1.21,
            "PKR": 282.00,
            "POUND": 1

        },
        "USD":{
            "PKR": 282.80,
            "POUND": 0.83,
            "USD": 1
        }


    }

const answer:{
    from: "POUND"| "USD" |"PKR",
    to : "POUND"| "USD" |"PKR",
    amount : number
} = await inquirer.prompt([
    {
        type: "list",
        name:"from",
        choices:["PKR","USD","POUND"],
        message: "Select Your Currency: "
    },
    {
        type: "list",
        name:"to",
        choices:["PKR","USD","POUND"],
        message: "Select Your Convertion Currency: "
    },
    {
        type: "number",
        name:"amount",
        message: "Please Enter Your Convertion Amount: "
    }
]);
const {from, to, amount} = answer;
if(from && to && amount){
let result = Convertion[from][to] * amount;
console.log(`Your Convertion From ${from} to ${to} is ${result}`)
}else{
    console.log("invalid inputs")
}
