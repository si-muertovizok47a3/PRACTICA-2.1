point = "1234567890"
GPA = 0
point_count = 0
lower_grade = 100
higher_grade = -100
name_student_lower_grade = ""
name_student_higher_grade = ""
try:
    fText = open("result.txt", 'a+', encoding="utf8")
    with open("students.txt", 'r', encoding="utf8") as f:
        for line in f:
            for char in line:
                if char in point:
                    GPA += int(char)
                    point_count += 1
            GPA /= point_count
            if GPA <= lower_grade:
                name_student_lower_grade = line.split(':')[0]
                lower_grade = GPA
            if GPA >= higher_grade:
                name_student_higher_grade = line.split(':')[0]
                higher_grade = GPA
            if GPA >= 4:
                fText.write(f"Средний бал студента(-ки) {line.split(':')[0]} : {GPA}\n")
            GPA = 0
            point_count = 0
    print(f"{name_student_higher_grade} имеет наивысший средний бал {higher_grade}")
    print(f"{name_student_lower_grade} имеет низший средний бал {lower_grade}")
    fText.close()
except FileNotFoundError:
    print("Ошибка: Файл 'students.txt' не найден.")
except ZeroDivisionError:
    print("Ошибка: В строке студента не найдены оценки (деление на ноль).")
