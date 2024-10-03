import tkinter as tk
import random

# Initialize the main window
root = tk.Tk()
root.title("Guess the Gold Cup")

# Load images of rabbit and gold cup
rabbit_img = tk.PhotoImage(file="rabbit.png")
cup_img = tk.PhotoImage(file="cup.png")

# Create a label to display the result
result_label = tk.Label(root, text="", font=("Helvetica", 16))
result_label.pack(pady=10)

# Function to handle rabbit click
def on_rabbit_click(rabbit_number):
    global result_label
    if rabbit_number == gold_cup_position:
        result_label.config(text="Congratulations! You found the gold cup!")
    else:
        result_label.config(text="Sorry, no cup behind this rabbit. Try again!")

# Create buttons for the rabbits
rabbit_buttons = []
for i in range(4):
    button = tk.Button(root, image=rabbit_img, command=lambda i=i: on_rabbit_click(i))
    button.pack(side=tk.LEFT, padx=10)
    rabbit_buttons.append(button)

# Randomly place the gold cup behind one of the rabbits
gold_cup_position = random.randint(0, 3)

# Run the main loop
root.mainloop()
