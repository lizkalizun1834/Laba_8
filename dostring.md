# Уставновка всех необходимых библиотек:

import tkinter as tk # импорт модуля
from tkinter import filedialog





# Создадим окно приложения
window = tk.Tk()
window.title("Программа с GUI")

# Устанавливаем начальный размер окна (ширина x высота)
window.geometry("400x300") 

# Методы для обработки введенных чисел
def add_numbers_gui():
    try:
# Получим введенные числа
# перевод в тип данных с плавающей точкой
        num1 = float(entry1.get()) 
# перевод в тип данных с плавающей точкой
        num2 = float(entry2.get()) 
# присвоение переменной суммы двух переменных
        result = num1 + num2 
        result_label.config(text=f"Результат: {result}")
    except ValueError:
        result_label.config(text="Ошибка: введите числа!")

# Метод для выбора файла
def select_file():
    file_path = filedialog.askopenfilename()
    file_label.config(text=f"Выбранный файл: {file_path}")

# Поля для ввода чисел
label1 = tk.Label(window, text="Введите первое число:")
label1.pack()
entry1 = tk.Entry(window)
entry1.pack()

label2 = tk.Label(window, text="Введите второе число:")
label2.pack()
entry2 = tk.Entry(window)
entry2.pack()

# Кнопка для выполнения сложения
add_button = tk.Button(window, text="Сложить", command=add_numbers_gui)
add_button.pack()

# Метка для отображения результата
result_label = tk.Label(window, text="Результат:")
result_label.pack()

# Кнопка для выбора файла
file_button = tk.Button(window, text="Выбрать файл", command=select_file)
file_button.pack()

# Метка для отображения выбранного файла
file_label = tk.Label(window, text="Файл не выбран")
file_label.pack()


# Позволяем изменять размер окна
window.resizable(True, True) # Можно изменять как по ширине, так и по высоте

# Запуск приложения
window.mainloop()
