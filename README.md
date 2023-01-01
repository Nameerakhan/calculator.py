# calculator.py
from art import logo
from replit import clear
def add(n1,n2):
   return n1+n2 
#substraction
def substract(n1,n2):
      return n1-n2
#multiplication
def multiply(n1,n2):
    return n1*n2
#division
def division(n1,n2):
    return n1/n2


operator = {
  "+":add,
  "-":substract,
  "*":multiply,
  "/":division
}

def calculator():
  print(logo)
  n1 = float(input("what's the first number?"))
  for symbol in operator:
    print(symbol)
  operational_symbol =input("pick an operation: ")
  n2 =float(input("what's the next number?: "))
  #addition
  calculation_function = operator[operational_symbol]
  answer1 = calculation_function(n1,n2)  
  print(f" {n1} {operational_symbol} {n2} ={answer1}")
  should_continue = input(f"type'y' to continue calculating with {answer1}, or type'n' to start a new calculation:")
  clear()
  
  final_calculation = False
  while not final_calculation:
  
    if should_continue=="y":
      operational_symbol =input("pick another operation: ")
      n3=int(input("what's the next number?: "))
      calculation_function = operator[operational_symbol]
      answer2 = calculation_function(answer1,n3)
      temp = answer1
      answer1 = answer2
      answer2 = temp
      print(f" {temp} {operational_symbol} {n3} ={answer1}")
      should_continue = input(f"type'y' to continue calculating with {answer1}, or type'n' to start a new calculation:")
      
      clear()
    else:
      final_calculation =True
      print(f" {n1} {operational_symbol} {n2} ={answer1}")
      calculator()
calculator()
  

