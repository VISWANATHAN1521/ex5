from tkinter import *
from tkinter import messagebox
window=Tk()
window.geometry("1920x1080")

def calculate_bmi():
    try:
        weight = float(weight_entry.get())
        height = float(height_entry.get())
        bmi = weight / (height ** 2)
        bmi_result = f"Your BMI is: {bmi:.2f}\n"
        if bmi < 18.5:
            bmi_result += "Underweight"
        elif 18.5 <= bmi < 25:
            bmi_result += "Normal weight"
        elif 25 <= bmi < 30:
            bmi_result += "Overweight"
        else:
            bmi_result += "Obese"
        messagebox.showinfo("BMI Result", bmi_result)
    except ValueError:
        messagebox.showerror("Error", "Invalid input. Please enter numeric values for weight and height.")

window = tk.Tk()
window.title("BMI Calculator")

weight_label = tk.Label(window, text="Weight (kg):")
weight_label.pack()
weight_entry = tk.Entry(window)
weight_entry.pack()

height_label = tk.Label(window, text="Height (m):")
height_label.pack()
height_entry = tk.Entry(window)
height_entry.pack()

calculate_button = tk.Button(window, text="Calculate BMI", command=calculate_bmi)
calculate_button.pack()

window.mainloop()
