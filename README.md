# lets-try
italian_food = ["Pasta Bolognese", "Pepperoni pizza", "Margherita piza", "Lasagna"]
indian_food = ["Curry", "Chutney", "Samosa", "Naan"]

# Define a function named find_meal that accepts two parameters: name and menu. Return name if found (represented as a list). If not, return None
def find_meal(name, menu):
  return name if name in menu else None 
# select meal function
def select_meal(name, food_type):
  if food_type == "Italian":
    return find_meal(name, italian_food)
  elif food_type == "Indian":
    return find_meal(name, indian_food)
  else:
    return None
# display available meals function
def display_available_meals(food_type):
  if food_type == "Italian":
    print("Available Italian Meals: ")
    for meal in italian_food:
      print(meal)
  elif food_type == "Indian":
    print("Available Indian Foods: ")
    for meal in indian_food:
      print(meal)
  else:
    "Invalid food type"
# order summary function
def create_summary(food_type, name, amount):
  order = select_meal(name, food_type)
  if order:
    return f"You ordered {amount} {name}" 
  else:
    return "Meal not found"
# Intro
print("Welcome to the Food Order System!")
# Food type input
type_input = input("What type of food would you like to choose from? Today's options are Italian or Indian: ")
display_available_meals(type_input)
# Order input

name_input = input("Enter meal choice: ")
amount_input = input("Enter order quantity: ")
# Present order summary
result = create_summary(type_input, name_input, amount_input)
print(result)
