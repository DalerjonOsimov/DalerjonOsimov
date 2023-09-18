# Найдем четные четырехзначные числа, у которых вторая справа цифра равна 1
numbers = []
for i in range(1000, 2049, 2):
    if str(i)[-2] == '1':
        numbers.append(i)

# Выведем цифры числа, исключая единицы
for num in numbers:
    num_str = str(num)
    num_without_ones = [digit for digit in num_str if digit != '1']
    print('Число:', num_str, ', Цифры без единиц:', ''.join(num_without_ones))

# Вычислим среднее число
min_num = min(numbers)
max_num = max(numbers)
average_num = (min_num + max_num) / 2

# Выведем среднее число прописью
def number_to_words(num):
    ones = ["", "один", "два", "три", "четыре", "пять", "шесть", "семь", "восемь", "девять"]
    tens = ["", "десять", "двадцать", "тридцать", "сорок", "пятьдесят", "шестьдесят", "семьдесят", "восемьдесят", "девяносто"]
    teens = ["", "одиннадцать", "двенадцать", "тринадцать", "четырнадцать", "пятнадцать", "шестнадцать", "семнадцать", "восемнадцать", "девятнадцать"]

    if num < 10:
        return ones[num]
    elif 10 <= num < 20:
        return teens[num - 10]
    else:
        return tens[num // 10] + (" " + ones[num % 10] if num % 10 != 0 else "")

average_num_words = number_to_words(int(average_num))
print('Среднее число прописью:', average_num_words)
