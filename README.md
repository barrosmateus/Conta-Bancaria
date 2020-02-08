# Conta-Bancaria
aula básica de programação - desafio 8


const user = {
  name: "Mariana",
  transactions: [],
  balance: 0
};



function createTransaction(transaction){ 
   user.transactions.push(transaction)
 
   if (transaction.type == 'credit'){
     user.balance =  user.balance + transaction.value
     user.balance =  user.balance + transaction.value
     user.balance =  user.balance + transaction.value
  }else{
    user.balance = user.balance - transaction.value
  }
}

function getHigestValueByType(typeOfTransaction){
  let higestValue = 0
  let higestTransaction
  for (let i of user.transactions){
    if (i.type == typeOfTransaction && i.value > higestValue){
    higestValue = i.value
    higestTransaction = i
    }    
  }
  return higestTransaction
}

function getHigestTransactionValue(){
let amont = 0

  for(let quantity of user.transactions ){
      amont = amont + quantity.value
    }

    return amont / user.transactions.length
}

function transactionCountByType(){
  let typeOfTransaction = {
    typeCredit: 0,
    typeDebit: 0
  } 
   
  for (let object of user.transactions){
    if(object.type ==  'credit'){
     typeOfTransaction.typeCredit = typeOfTransaction.typeCredit + 1
    }else{
      typeOfTransaction.typeDebit = typeOfTransaction.typeDebit + 1
    }
  
  } 
  return typeOfTransaction
}

createTransaction({
  type:'credit',
  value: 600
}),
createTransaction({
  type:'credit',
  value: 25
}),
createTransaction({
  type:'debit',
  value: 150
}),
createTransaction({
  type:'debit',
  value: 300
}),
createTransaction({
  type:'debit',
  value: 500
}),


console.log(user)
console.log('o maior valor de trasaçao, em tipo e valor', getHigestValueByType('credit'))
console.log('o maior valor de trasaçao, em tipo e valor', getHigestValueByType('debit'))
console.log(('o valor médio de transações é de:'), getHigestTransactionValue())
console.log(transactionCountByType())
