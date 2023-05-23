import math

# Отримання оцінок від користувача
tasks = []
while True:
    a = float(input("Введіть оптимістичну оцінку для завдання (a): "))
    m = float(input("Введіть найбільш ймовірну оцінку для завдання (m): "))
    b = float(input("Введіть песимістичну оцінку для завдання (b): "))
    tasks.append((a, m, b))
    choice = input("Бажаєте додати ще одне завдання? (y/n): ")
    if choice.lower() == 'n':
        break

# Розрахунок оцінки та стандартного відхилення для кожного завдання
E_tasks = []
SD_tasks = []
for task in tasks:
    a, m, b = task
    E_task = (a + 4*m + b) / 6
    SD_task = (b - a) / 6
    E_tasks.append(E_task)
    SD_tasks.append(SD_task)

# Розрахунок оцінки та стандартного відхилення для всього проекту
E_project = sum(E_tasks)
SE_project = math.sqrt(sum([sd**2 for sd in SD_tasks]))
CI_project_lower = E_project - 2*SE_project
CI_project_upper = E_project + 2*SE_project

# Виведення результатів
print(f"95% довірчий інтервал проекту: {CI_project_lower:.2f} ... {CI_project_upper:.2f} балів")
