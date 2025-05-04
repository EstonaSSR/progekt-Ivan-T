Иван Тырин, [5/4/2025 11:56 AM]
import sys
import time
import pygame

for i in range(1):
    pygame.init()

    width, height = 400, 200
    screen = pygame.display.set_mode((width, height))
    pygame.display.set_caption('Имитация загрузки')

    black = (0, 0, 0)
    white = (255, 255, 255)
    green = (0, 255, 0)

    font = pygame.font.Font(None, 36)


    def draw_loading_bar(progress):
        pygame.draw.rect(screen, white, [50, 100, 300, 30])
        pygame.draw.rect(screen, green, [50, 100, 300 * progress, 30])


    # Основной цикл
    def main():
        clock = pygame.time.Clock()
        loading_time = 5
        start_time = time.time()

        while True:
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    pygame.quit()
                    sys.exit()

            elapsed_time = time.time() - start_time
            progress = min(elapsed_time / loading_time, 1)

            screen.fill(black)
            loading_text = font.render('Запуск системы...', True, white)
            screen.blit(loading_text, (150, 50))
            draw_loading_bar(progress)

            pygame.display.flip()
            if progress >= 1:
                break

            clock.tick(60)
        running = True
        while running:
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    running = False

            screen.fill(black)
            completed_text = font.render('Система запущена', True, white)
            screen.blit(completed_text, (100, 100))
            pygame.display.flip()

        pygame.quit()

    print('Добро пожаловать, User!')

    if name == "main":
        main()
    while True:
        user_application = input('Выберите приложение(умные заметки, узнать id лица, пройди тест,Hi it!,шутер ,чат gpt, обработка фото, калькулятор, 3д, 4д):')
        if user_application == 'умные заметки':
            from PyQt5.QtCore import *
            from PyQt5.QtWidgets import *
            import json
            notes = {}
            # with open('notes.json', 'w') as file:
            #     json.dump(notes, file)
            app = QApplication([])
            notes_win = QWidget()
            notes_win.setWindowTitle('умные заметки')
            notes_win.resize(900, 600)
            list_notes = QListWidget()
            list_notes_label = QLabel('Список заметок')
            list_tags = QListWidget()
            list_tag_label = QLabel('Список тегов')
            button_note_create = QPushButton('Создать заметку')
            button_note_delete = QPushButton('Удалить заметку')
            button_note_save = QPushButton('Сохранить заметку')
            button_tag_add = QPushButton('Добавить тег')
            button_tag_del = QPushButton('Открепить тег')
            button_tag_search = QPushButton('Искать заметки по тегу')
            field_tag = QLineEdit('')
            field_tag.setPlaceholderText('Подсказка: сюда вводить теги')
            field_text = QTextEdit()
            layout_notes = QHBoxLayout()
            col1 = QVBoxLayout()
            col1.addWidget(field_text)
            col2 = QVBoxLayout()
            col2.addWidget(list_notes_label)
            col2.addWidget(list_notes)
            row1 = QHBoxLayout()
            row1.addWidget(button_note_create)
            row1.addWidget(button_note_delete)
            row2 = QHBoxLayout()
            row2.addWidget(button_note_save)
            col2.addLayout(row1)
            col2.addLayout(row2)
            # и точно так же нижнюю чать второго столбца :)))))
            col2.addWidget(list_tag_label)
            col2.addWidget(list_tags)
            col2.addWidget(field_tag)
            row3 = QHBoxLayout()
            row3.addWidget(button_tag_add)
            row3.addWidget(button_tag_del)

Иван Тырин, [5/4/2025 11:56 AM]
row4 = QHBoxLayout()
            row4.addWidget(button_tag_search)
            col2.addLayout(row3)
            col2.addLayout(row4)
            def Snow_note():
                key = list_notes.selectedItems()[0].text()
                field_text.setText(notes[key]['текст'])
                list_tags.clear()
                list_tags.addItems(notes[key]['теги'])
            list_notes.itemClicked.connect(Snow_note)
            with open('../../Downloads/notes.json', 'r') as file:
                notes = json.load(file)
            list_notes.addItems(notes)
            layout_notes.addLayout(col1, stretch=2)
            layout_notes.addLayout(col2, stretch=1)
            notes_win.setLayout(layout_notes)
            def add_note():
                note_name, ok = QInputDialog.getText(notes_win, 'Новая', 'Название')
                if ok and note_name != '':
                    notes[note_name] = {'текст': '', 'теги': []}
                    list_notes.addItem(note_name)
            def save_note():
                if list_notes.selectedItems():
                    key = list_notes.selectedItems()[0].text()
                    notes[key]['текст'] = field_text.toPlainText()
                    with open('../../Downloads/notes.json', 'w') as file:
                        json.dump(notes, file, sort_keys=True, ensure_ascii=False)
            button_note_create.clicked.connect(add_note)
            button_note_save.clicked.connect(save_note)
            def del_note():
                if list_notes.selectedItems():
                    key = list_notes.selectedItems()[0].text()
                    del notes[key]
                    list_notes.clear()
                    list_tags.clear()
                    field_text.clear()
                    list_notes.addItems(notes)
                    with open('../../Downloads/notes.json', 'w') as file:
                            json.dump(notes, file, sort_keys=True, ensure_ascii=False)
            button_note_delete.clicked.connect(del_note)
            def add_tag():
                if list_notes.selectedItems():
                    key = list_notes.selectedItems()[0].text()
                    tag = field_tag.text()
                    if not tag in notes[key]['теги']:
                        notes[key]['теги'].append(tag)
                        list_tags.addItem(tag)
                        field_tag.clear()
                    with open('../../Downloads/notes.json', 'w') as file:
                        json.dump(notes, file, sort_keys=True, ensure_ascii=False)
            button_tag_add.clicked.connect(add_tag)
            def del_tag():
                if list_tags.selectedItems():
                    key = list_notes.selectedItems()[0].text()
                    tag = list_tags.selectedItems()[0].text()
                    notes[key]['теги'].remove(tag)
                    list_tags.clear()
                    list_tags.addItems(notes[key]['теги'])
                    with open('../../Downloads/notes.json', 'w') as file:
                        json.dump(notes, file, sort_keys=True, ensure_ascii=False)
            button_tag_del.clicked.connect(del_tag)
            notes_win.show()
            app.exec()
        elif user_application == 'пройди тест':
            from random import *
            from PyQt5.QtCore import Qt
            from PyQt5.QtWidgets import *
            class Question():
                def init(self, question, right_answer, wrong1, wrong2, wrong3):
                    self.question = question
                    self.right_answer = right_answer
                    self.wrong1 = wrong1
                    self.wrong2 = wrong2
                    self.wrong3 = wrong3
            question_list = []
            question_list.append(
                Question('А и Б сидели на трубе А упала Б пропала. Что осталалось на трубе?', 'И', 'N', 'А', 'Б'))

Иван Тырин, [5/4/2025 11:56 AM]
question_list.append(
                Question('Хороший вопрос всегда требует ответа. Не так ли?', 'Это философия, а этого предмета нету в школе',
                         'Да', 'Нет', 'Осуждаю'))
            question_list.append(Question('2+2=4. Верно?', 'Да', 'да', 'ДА', 'Ад'))
            question_list.append(Question('2+2=5. Верно?', 'Нет', 'НЕТ', 'нЕт', 'НЕт'))
            question_list.append(
                Question('Как называется лёд который при контакте с водой ведёт себя как центр кристаллизации?', 'Лёд 9',
                         'Лёд обычный', 'Лёд необычный', 'Ни какой из этих ответов не правельный'))
            question_list.append(
                Question('Какое направление добавляется при попадании в 4д пространство?', 'Ана и ката', 'Впрёд и назад',
                         'Вправо и влево', 'Вверх и вниз'))
            question_list.append(
                Question('Как называется куб в 4д пространстве', 'Тессеракт', 'Тор клифорда', 'Кубиндр', 'Сфериндр'))
            question_list.append(Question('Параллельные линии пересекаютсятся?', 'Да*', 'Да', 'нет', 'Нет'))
            question_list.append(
                Question('Изменяется ли проекция при параллельном перемещении плоскости проекций', 'Нет', 'Да', 'Незнаю',
                         'Не какой из этих ответов не правельный'))
            question_list.append(Question('Кто съел морковку?', 'Стёпа', 'Никакой', 'Достали эти вопросы', '...'))
            app = QApplication([])
            window = QWidget()
            window.setWindowTitle('Memory Card')
            btn_OK = QPushButton('Ответить')
            lb_Question = QLabel('В каком году быда основана Москва?')
            RadioGroupBox = QGroupBox("Варианты ответов")
            rbtn_1 = QRadioButton('1147')
            rbtn_2 = QRadioButton('1242')
            rbtn_3 = QRadioButton('1861')
            rbtn_4 = QRadioButton('1943')
            AnsGroupBox = QGroupBox("Результат теста")
            lb_Result = QLabel('Прав ты или нет')
            lb_Correct = QLabel('ответ будет тут')
            RadioGroup = QButtonGroup()
            RadioGroup.addButton(rbtn_1)
            RadioGroup.addButton(rbtn_2)
            RadioGroup.addButton(rbtn_3)
            RadioGroup.addButton(rbtn_4)
            Layout_res = QVBoxLayout()
            Layout_res.addWidget(lb_Result, alignment=(Qt.AlignLeft | Qt.AlignTop))
            Layout_res.addWidget(lb_Correct, alignment=Qt.AlignHCenter, stretch=2)
            AnsGroupBox.setLayout(Layout_res)
            Layout_ans1 = QHBoxLayout()
            Layout_ans2 = QVBoxLayout()
            Layout_ans3 = QVBoxLayout()
            Layout_ans2.addWidget(rbtn_1)
            Layout_ans2.addWidget(rbtn_2)
            Layout_ans3.addWidget(rbtn_3)
            Layout_ans3.addWidget(rbtn_4)
            Layout_ans1.addLayout(Layout_ans2)
            Layout_ans1.addLayout(Layout_ans3)
            RadioGroupBox.setLayout(Layout_ans1)
            Layout_line1 = QHBoxLayout()
            Layout_line2 = QHBoxLayout()
            Layout_line3 = QHBoxLayout()
            Layout_line1.addWidget(lb_Question, alignment=(Qt.AlignHCenter | Qt.AlignVCenter))
            Layout_line2.addWidget(RadioGroupBox)
            Layout_line2.addWidget(AnsGroupBox)
            Layout_line3.addWidget(btn_OK, stretch=2)
            Layout_card = QVBoxLayout()
            Layout_card.addLayout(Layout_line1, stretch=2)
            Layout_card.addLayout(Layout_line2, stretch=8)
            Layout_card.addLayout(Layout_line3, stretch=1)
            AnsGroupBox.hide()
            answers = [rbtn_1, rbtn_2, rbtn_3, rbtn_4]
            shuffle(answers)
            def show_result():
                RadioGroupBox.hide()
                AnsGroupBox.show()
                btn_OK.setText('Следующий вопрос')

Иван Тырин, [5/4/2025 11:56 AM]
def ask(q: Question):
                ''' функция записывает значения вопроса и ответов в соответствующие виджеты,
                при этом варианты ответов распределяются случайным образом'''
                shuffle(answers)
                answers[0].setText(q.right_answer)
                answers[1].setText(q.wrong1)
                answers[2].setText(q.wrong2)
                answers[3].setText(q.wrong3)
                lb_Question.setText(q.question)
                lb_Correct.setText(q.right_answer)
                show_question()
            def check_answer():
                if answers[0].isChecked():
                    lb_Result.setText('Правильно!')
                    show_result()
                if answers[1].isChecked() or answers[2].isChecked() or answers[3].isChecked():
                    lb_Result.setText('Неверно!')
            show_result()
            def show_question():
                RadioGroupBox.show()
                AnsGroupBox.hide()
                btn_OK.setText('Ответить')
                RadioGroup.setExclusive(False)
                rbtn_1.setChecked(False)
                rbtn_2.setChecked(False)
                rbtn_3.setChecked(False)
                rbtn_4.setChecked(False)
                RadioGroup.setExclusive(True)
            def next_quesstion():
                cur_question = randint(0, len(question_list) - 1)
                q = question_list[cur_question]
                ask(q)
            def click_OK():
                if btn_OK.text() == 'Ответить':
                    check_answer()
                else:
                    next_quesstion()


            def show_results():
                pass


            def test():
                if 'Ответить' == btn_OK.text():
                    show_results()
                else:
                    show_question()
            next_quesstion()
            btn_OK.clicked.connect(click_OK)
            window.setLayout(Layout_card)
            window.show()
            app.exec()
        elif user_application == 'Hi it!':
            from turtle import *
            from random import *
            tsize = 20
            s_width = 200
            s_height = 180
            class Sprite(Turtle):
                def init(self, x, y, step=10, shape='circle', color='black'):
                    Turtle.init(self)
                    self.penup()
                    self.speed(0)
                    self.goto(x, y)
                    self.color(color)
                    self.shape(shape)
                    self.step = step
                    self.points = 0
                def move_up(self):
                    self.goto(self.xcor(), self.ycor() + self.step)
                def move_down(self):
                    self.goto(self.xcor(), self.ycor() - self.step)
                def move_left(self):
                    self.goto(self.xcor() - self.step, self.ycor())
                def move_right(self):
                    self.goto(self.xcor() + self.step, self.ycor())
                def is_collide(self, sprite):
                    dist = self.distance(sprite.xcor(), sprite.ycor())
                    return dist < 30
                def set_move(self, x_start, y_start, x_end, y_end):
                    self.x_start = x_start
                    self.y_start = y_start
                    self.x_end = x_end
                    self.y_end = y_end
                    self.goto(x_start, y_start)
                    self.setheading(self.towards(x_end, y_end))
                def make_step(self):
                    self.forward(self.step)
                    if self.distance(self.x_end, self.y_end) < self.step:
                        self.set_move(self.x_end, self.y_end, self.x_start, self.y_start)
            player = Sprite(0, -100, 10, 'circle', 'orange')

Иван Тырин, [5/4/2025 11:56 AM]
enemy1 = Sprite(-s_width, 0, 15, 'square', 'red')
            enemy1.set_move(-s_width, 0, s_width, 0)
            enemy2 = Sprite(s_width, 70, 15, 'square', 'red')
            enemy2.set_move(s_width, 70, -s_width, 70)
            goal = Sprite(0, 120, 20, 'triangle', 'green')
            total_score = 0
            scr = player.getscreen()
            scr.listen()
            scr.onkey(player.move_up, 'Up')
            scr.onkey(player.move_left, 'Left')
            scr.onkey(player.move_right, 'Right')
            scr.onkey(player.move_down, 'Down')
            while total_score < 3:
                enemy1.make_step()
                enemy2.make_step()
                if player.is_collide(goal):
                    total_score += 1
                    player.goto(0, -100)
                if player.is_collide(enemy1) or player.is_collide(enemy2):
                    goal.hideturtle()
                    break
            if total_score == 3:
                enemy1.hideturtle()
                enemy2.hideturtle()
        elif user_application == 'обработка фото':
            import os
            from PyQt5.QtWidgets import *
            from PyQt5.QtCore import Qt

            app = QApplication([])
            win = QWidget()
            win.resize(700, 500)
            win.setWindowTitle('Easy Editor')
            lb_image = QLabel("Картинка")
            btn_dir = QPushButton("Папка")
            lw_files = QListWidget()

            btn_left = QPushButton("Лево")
            btn_right = QPushButton("Право")
            btn_flip = QPushButton("Зеркало")
            btn_sharp = QPushButton("Резкость")
            btn_bw = QPushButton("ЧБ")

            row = QHBoxLayout()
            col1 = QVBoxLayout()
            col2 = QVBoxLayout()
            col1.addWidget(btn_dir)
            col1.addWidget(lw_files)
            col2.addWidget(lb_image, 95)
            row_tools = QHBoxLayout()
            row_tools.addWidget(btn_left)
            row_tools.addWidget(btn_right)
            row_tools.addWidget(btn_flip)
            row_tools.addWidget(btn_sharp)
            row_tools.addWidget(btn_bw)
            col2.addLayout(row_tools)

            row.addLayout(col1, 20)
            row.addLayout(col2, 80)
            win.setLayout(row)

            win.show()

            workdir = ''


            def filter(files, extensions):
                result = []
                for filename in files:
                    for ext in extensions:
                        if filename.endswith(ext):
                            result.append(filename)
                return result


            def chooseWorkdir():
                global workdir
                workdir = QFileDialog.getExistingDirectory()


            def showFilenamesList():
                extensions = ['.jpg', '.jpeg', '.png', '.gif', '.bmp']
                chooseWorkdir()
                filenames = filter(os.listdir(workdir), extensions)
                lw_files.clear()
                for filename in filenames:
                    lw_files.addItem(filename)


            from PyQt5.QtGui import *
            from PIL import Image


            class ImageProcessor():
                def init(self):
                    self.image = None
                    self.name = None
                    self.save_dir = 'Modified/'

                def loadImage(self, filename):
                    self.name = filename
                    image_path = os.path.join(workdir, filename)
                    self.image = Image.open(image_path)

                def showImage(self, path):
                    lb_image.hide()
                    pixmapimage = QPixmap(path)
                    w, h = lb_image.width(), lb_image.height()
                    pixmapimage = pixmapimage.scaled(w, h, Qt.KeepAspectRatio)
                    lb_image.setPixmap(pixmapimage)
                    lb_image.show()

Иван Тырин, [5/4/2025 11:56 AM]
def saveImage(self):
                    path = os.path.join(workdir, self.save_dir)
                    if not (os.path.exists(path) or os.path.isdir(path)):
                        os.mkdir(path)
                    image_path = os.path.join(path, self.name)
                    self.image.save(image_path)

                def do_bw(self):
                    self.image = self.image.convert('L')
                    self.saveImage()
                    image_path = os.path.join(workdir, self.save_dir, self.name)
                    self.showImage(image_path)

                def do_left(self):
                    self.Image = self.image.transpose(Image.ROTATE_90)
                    self.saveImage()
                    image_path = os.path.join(workdir, self.save_dir, self.name)
                    self.showImage(image_path)

                def do_right(self):
                    self.Image = self.image.transpose(Image.ROTATE_270)
                    self.saveImage()
                    image_path = os.path.join(workdir, self.save_dir, self.name)
                    self.showImage(image_path)


            def showChosenImage():
                if lw_files.currentRow() >= 0:
                    filename = lw_files.currentItem().text()
                    workimage.loadImage(filename)
                    image_path = os.path.join(workdir, workimage.name)
                    workimage.showImage(image_path)


            workimage = ImageProcessor()
            lw_files.currentRowChanged.connect(showChosenImage)
            btn_dir.clicked.connect(showFilenamesList)
            btn_bw.clicked.connect(workimage.do_bw)
            btn_left.clicked.connect(workimage.do_left)
            btn_right.clicked.connect(workimage.do_right)
            app.exec()

        elif user_application == 'чат gpt':
            import g4f.gui
            import random

            print('Пререйдите по первой ссылке')
            random_number = random.randint(0, 9999)
            g4f.gui.run_gui(port=random_number)
        elif user_application == 'калькулятор':
            from cmath import *
            import flet as ft

            def main(page: ft.Page):
                page.title = "Калькулятор"

                num1 = ft.TextField(label="Число 1", width=150)
                num2 = ft.TextField(label="Число 2", width=150)

                result_text = ft.Text("Результат: ")

                def calculate(e):
                    n1 = float(num1.value)
                    n2 = float(num2.value)
                    operation = e.control.text
                    if operation == "+":
                        result = n1 + n2
                    elif operation == "-":
                        result = n1 - n2
                    elif operation == "/":
                        result = n1 / n2
                    elif operation == "*":
                        result = n1 * n2
                    elif operation == "√":
                        result = sqrt(n1)
                    elif operation == "sin":
                        result = sin(n1)
                    elif operation == "cos":
                        result = cos(n1)
                    elif operation == "tan":
                        result = tan(n1)


                    result_text.value = f"Результат: {result}"  # Обновляем результат

                    page.update()


                buttons = [
                    ft.ElevatedButton(op, on_click=calculate) for op in ["+", "-", "/", "*", "√", "sin", "cos", "tan"]
                ]

                page.add(
                    num1, num2,
                    ft.Row(buttons, alignment=ft.MainAxisAlignment.CENTER),
                    result_text
                )


            ft.app(target=main)
        elif user_application == '3д':
            import numpy as np
            import matplotlib.pyplot as plt
            from mpl_toolkits.mplot3d import *

Иван Тырин, [5/4/2025 11:56 AM]
figure = input('Введите фигуру(шар, куб, тессеракт):')
            if figure == 'шар':
                fig = plt.figure()
                ax = fig.add_subplot(111, projection='3d')

                u = np.linspace(0, 2 * np.pi, 100)
                v = np.linspace(0, np.pi, 100)

                x = 10 * np.outer(np.cos(u), np.sin(v))
                y = 10 * np.outer(np.sin(u), np.sin(v))
                z = 10 * np.outer(np.ones(np.size(u)), np.cos(v))

                ax.plot_surface(x, y, z, color='b', alpha=0.6)

                ax.set_xlabel('X-axis')
                ax.set_ylabel('Y-axis')
                ax.set_zlabel('Z-axis')
                ax.set_title('3D Sphere')

                plt.show()
            if figure == 'куб':
                r = [0, 1]
                X, Y = np.meshgrid(r, r)
                Z1 = np.zeros_like(X)
                Z2 = np.ones_like(X)

                fig = plt.figure()
                ax = fig.add_subplot(111, projection='3d')

                ax.plot_surface(X, Y, Z1, alpha=0.5, color='cyan')
                ax.plot_surface(X, Y, Z2, alpha=0.5, color='cyan')
                ax.plot_surface(X, Z1, Y, alpha=0.5, color='cyan')
                ax.plot_surface(X, Z2, Y, alpha=0.5, color='cyan')
                ax.plot_surface(Z1, X, Y, alpha=0.5, color='cyan')
                ax.plot_surface(Z2, X, Y, alpha=0.5, color='cyan')

                ax.set_xlabel('X')
                ax.set_ylabel('Y')
                ax.set_zlabel('Z')

                ax.set_xlim(0, 1)
                ax.set_ylim(0, 1)
                ax.set_zlim(0, 1)

                plt.title('Куб')
                plt.show()
            if figure == 'тессеракт':
                def plot_tesseract(ax):
                    vertices = np.array([[x, y, z, w] for x in [0, 1] for y in [0, 1] for z in [0, 1] for w in [0, 1]])

                    projection = vertices[:, :3] + 0.5 * vertices[:, 3][:, np.newaxis]

                    edges = []
                    for i in range(len(vertices)):
                        for j in range(i + 1, len(vertices)):
                            if np.sum(np.abs(vertices[i] - vertices[j])) == 1:  # Соединяем только "соседние" вершины
                                edges.append((i, j))

                    for edge in edges:
                        points = projection[list(edge), :]
                        ax.plot3D(*zip(*points), color='b')


                def main():
                    fig = plt.figure()
                    ax = fig.add_subplot(111, projection='3d')

                    ax.set_title("Projection of a Tesseract in 3D")
                    ax.set_xlabel('X axis')
                    ax.set_ylabel('Y axis')
                    ax.set_zlabel('Z axis')

                    plot_tesseract(ax)

                    plt.show()


                if name == "main":
                    main()
        elif user_application == 'выход':
            import pygame
            import time

            pygame.init()

            BLACK = (0, 0, 0)
            WHITE = (255, 255, 255)

            screen = pygame.display.set_mode((800, 600))
            pygame.display.set_caption("Завершение работы...")

            font = pygame.font.SysFont(None, 48)


            def shutdown_simulation():
                messages = [
                    "Завершение работы системы...",
                    "Закрытие открытых приложений...",
                    "Сохранение настроек...",
                    "Завершение работы системы. Пожалуйста, подождите..."
                ]

                for message in messages:
                    screen.fill(BLACK)

                    text = font.render(message, True, WHITE)
                    text_rect = text.get_rect(center=(400, 300))
                    screen.blit(text, text_rect)

                    pygame.display.flip()

                    time.sleep(1)

Иван Тырин, [5/4/2025 11:56 AM]
for alpha in range(0, 255, 5):
                    screen.fill(BLACK)
                    overlay = pygame.Surface((800, 600))
                    overlay.fill(BLACK)
                    overlay.set_alpha(alpha)
                    screen.blit(overlay, (0, 0))

                    pygame.display.flip()
                    time.sleep(0.1)

                pygame.quit()


            if name == "main":
                shutdown_simulation()
            break
        elif user_application == 'шутер':
            from pygame import *
            from random import randint
            from time import \
                time as timer
            font.init()
            font1 = font.Font(None, 80)
            win = font1.render('YOU WIN!', True, (255, 255, 255))
            lose = font1.render('YOU LOSE!', True, (180, 0, 0))

            font2 = font.Font(None, 36)


            # mixer.init()
            # mixer.music.load('space.ogg')
            # mixer.music.play()
            # fire_sound = mixer.Sound('fire.ogg')

            img_back = "galaxy.jpg"
            img_bullet = "bullet.png"
            img_hero = "rocket.png"
            img_enemy = "ufo.png"
            img_ast = "asteroid.png"

            score = 0
            goal = 20
            lost = 0
            max_lost = 10
            life = 3


            class GameSprite(sprite.Sprite):
                def init(self, player_image, player_x, player_y, size_x, size_y, player_speed):
                    sprite.Sprite.init(self)

                    self.image = transform.scale(image.load(player_image), (size_x, size_y))
                    self.speed = player_speed

                    self.rect = self.image.get_rect()
                    self.rect.x = player_x
                    self.rect.y = player_y

                def reset(self):
                    window.blit(self.image, (self.rect.x, self.rect.y))


            class Player(GameSprite):
                def update(self):
                    keys = key.get_pressed()
                    if keys[K_LEFT] and self.rect.x > 5:
                        self.rect.x -= self.speed
                    if keys[K_RIGHT] and self.rect.x < win_width - 80:
                        self.rect.x += self.speed

                def fire(self):
                    bullet = Bullet(img_bullet, self.rect.centerx, self.rect.top, 15, 20, -15)
                    bullets.add(bullet)


            class Enemy(GameSprite):
                def update(self):
                    self.rect.y += self.speed
                    global lost
                    if self.rect.y > win_height:
                        self.rect.x = randint(80, win_width - 80)
                        self.rect.y = 0
                        lost = lost + 1


            class Bullet(GameSprite):
                def update(self):
                    self.rect.y += self.speed
                    if self.rect.y < 0:
                        self.kill()


            win_width = 700
            win_height = 500
            display.set_caption("Shooter")
            window = display.set_mode((win_width, win_height))
            background = transform.scale(image.load(img_back), (win_width, win_height))
            ship = Player(img_hero, 5, win_height - 100, 80, 100, 10)

            monsters = sprite.Group()
            for i in range(1, 6):
                monster = Enemy(img_enemy, randint(80, win_width - 80), -40, 80, 50, randint(1, 5))
                monsters.add(monster)

            asteroids = sprite.Group()
            for i in range(1, 3):
                asteroid = Enemy(img_ast, randint(30, win_width - 30), -40, 80, 50, randint(1, 7))
                asteroids.add(asteroid)

            bullets = sprite.Group()

            finish = False
            run = True

            rel_time = False

Иван Тырин, [5/4/2025 11:56 AM]
num_fire = 0
            while run:
                for e in event.get():
                    if e.type == QUIT:
                        run = False
                    elif e.type == KEYDOWN:
                        if e.key == K_SPACE:
                            if num_fire < 5 and rel_time == False:
                                num_fire = num_fire + 1
                                # fire_sound.play()
                                ship.fire()
                            if num_fire >= 5 and rel_time == False:
                                last_time = timer()
                                rel_time = True

                if not finish:
                    window.blit(background, (0, 0))
                    ship.update()
                    monsters.update()
                    asteroids.update()
                    bullets.update()
                    ship.reset()
                    monsters.draw(window)
                    asteroids.draw(window)
                    bullets.draw(window)

                    if rel_time == True:
                        now_time = timer()
                        if now_time - last_time < 3:
                            reload = font2.render('Wait, reload...', 1, (150, 0, 0))
                            window.blit(reload, (260, 460))
                        else:
                            num_fire = 0
                            rel_time = False

                    collides = sprite.groupcollide(monsters, bullets, True, True)
                    for c in collides:
                        score = score + 1
                        monster = Enemy(img_enemy, randint(80, win_width - 80), -40, 80, 50, randint(1, 5))
                        monsters.add(monster)

                    if sprite.spritecollide(ship, monsters, False) or sprite.spritecollide(ship, asteroids, False):
                        sprite.spritecollide(ship, monsters, True)
                        sprite.spritecollide(ship, asteroids, True)
                        life = life - 1

                    if life == 0 or lost >= max_lost:
                        finish = True  # проиграли
                        window.blit(lose, (200, 200))

                    if score >= goal:
                        finish = True
                        window.blit(win, (200, 200))

                    text = font2.render("Счет: " + str(score), 1, (255, 255, 255))
                    window.blit(text, (10, 20))
                    text_lose = font2.render("Пропущено: " + str(lost), 1, (255, 255, 255))
                    window.blit(text_lose, (10, 50))

                    # задаем разный цвет в зависимости от кол-ва жизней
                    if life == 3: life_color = (0, 150, 0)
                    if life == 2: life_color = (150, 150, 0)
                    if life == 1: life_color = (150, 0, 0)
                    text_life = font1.render(str(life), 1, life_color)
                    window.blit(text_life, (650, 10))
                    display.update()


                else:
                    finish = False
                    score = 0
                    lost = 0
                    num_fire = 0
                    life = 3
                    for b in bullets: b.kill()
                    for m in monsters: m.kill()
                    for a in asteroids: a.kill()
                    time.delay(3000)
                    for i in range(1, 6):
                        monster = Enemy(img_enemy, randint(80, win_width - 80), -40, 80, 50, randint(1, 5))
                        monsters.add(monster)
                    for i in range(1, 3):
                        asteroid = Enemy(img_ast, randint(30, win_width - 30), -40, 80, 50, randint(1, 7))
                        asteroids.add(asteroid)
                time.delay(100)

Иван Тырин, [5/4/2025 11:56 AM]
elif user_application == '4д':
            figure = input('Введите фигуру(4д цилиндр, тессеракт):')
            if figure == 'тессеракт':
                import numpy as np
                import matplotlib.pyplot as plt
                from mpl_toolkits.mplot3d import Axes3D
                from matplotlib.widgets import Slider
                from itertools import combinations


                def generate_tesseract_vertices():
                    vertices = []
                    for i in [0, 1]:
                        for j in [0, 1]:
                            for k in [0, 1]:
                                for l in [0, 1]:
                                    vertices.append([i, j, k, l])
                    return np.array(vertices)


                def rotation_matrix_4d_xy(theta):
                    return np.array([
                        [np.cos(theta), -np.sin(theta), 0, 0],
                        [np.sin(theta), np.cos(theta), 0, 0],
                        [0, 0, 1, 0],
                        [0, 0, 0, 1]
                    ])


                def rotation_matrix_4d_xz(theta):
                    return np.array([
                        [np.cos(theta), 0, -np.sin(theta), 0],
                        [0, 1, 0, 0],
                        [np.sin(theta), 0, np.cos(theta), 0],
                        [0, 0, 0, 1]
                    ])


                def rotation_matrix_4d_xw(theta):
                    return np.array([
                        [np.cos(theta), 0, 0, -np.sin(theta)],
                        [0, 1, 0, 0],
                        [0, 0, 1, 0],
                        [np.sin(theta), 0, 0, np.cos(theta)]
                    ])


                def rotation_matrix_4d_yw(theta):
                    return np.array([
                        [1, 0, 0, 0],
                        [0, np.cos(theta), 0, -np.sin(theta)],
                        [0, 0, 1, 0],
                        [0, np.sin(theta), 0, np.cos(theta)]
                    ])


                def rotate_4d(vertices, angle_xy, angle_xz, angle_xw, angle_yw):
                    rot_xy = rotation_matrix_4d_xy(angle_xy)
                    rot_xz = rotation_matrix_4d_xz(angle_xz)
                    rot_xw = rotation_matrix_4d_xw(angle_xw)
                    rot_yw = rotation_matrix_4d_yw(angle_yw)

                    rotation = rot_xy @ rot_xz @ rot_xw @ rot_yw

                    rotated = np.dot(vertices, rotation.T)
                    return rotated


                def generate_tesseract_edges(vertices):
                    edges = []
                    n = len(vertices)

                    # Соединяем вершины, которые отличаются на одну координату
                    for i in range(n):
                        for j in range(i + 1, n):
                            if np.sum(np.abs(vertices[i] - vertices[j])) == 1:
                                edges.append((i, j))

                    return edges


                def visualize_tesseract():
                    # Генерируем вершины и ребра
                    vertices = generate_tesseract_vertices()
                    edges = generate_tesseract_edges(vertices)

                    vertices = (vertices - 0.5) * 2

                    fig = plt.figure(figsize=(14, 8))
                    ax_3d = fig.add_subplot(121, projection='3d')
                    ax_parallel = fig.add_subplot(122)

                    plt.subplots_adjust(bottom=0.3)
                    ax_xy = plt.axes([0.15, 0.2, 0.7, 0.03])
                    ax_xz = plt.axes([0.15, 0.15, 0.7, 0.03])
                    ax_xw = plt.axes([0.15, 0.1, 0.7, 0.03])
                    ax_yw = plt.axes([0.15, 0.05, 0.7, 0.03])

                    slider_xy = Slider(ax_xy, 'XY rotation', 0, 2 * np.pi, valinit=0)
                    slider_xz = Slider(ax_xz, 'XZ rotation', 0, 2 * np.pi, valinit=0)
                    slider_xw = Slider(ax_xw, 'XW rotation', 0, 2 * np.pi, valinit=0)
                    slider_yw = Slider(ax_yw, 'YW rotation', 0, 2 * np.pi, valinit=0)

Иван Тырин, [5/4/2025 11:56 AM]
def update(val):
                        angle_xy = slider_xy.val
                        angle_xz = slider_xz.val
                        angle_xw = slider_xw.val
                        angle_yw = slider_yw.val

                        rotated = rotate_4d(vertices, angle_xy, angle_xz, angle_xw, angle_yw)

                        ax_3d.cla()
                        ax_parallel.cla()

                        for edge in edges:
                            points = rotated[list(edge)]
                            ax_3d.plot3D(points[:, 0], points[:, 1], points[:, 2], 'b-', alpha=0.6)

                        ax_3d.scatter(rotated[:, 0], rotated[:, 1], rotated[:, 2], c='r', s=50)

                        ax_3d.set_xlim([-2, 2])
                        ax_3d.set_ylim([-2, 2])
                        ax_3d.set_zlim([-2, 2])
                        ax_3d.set_title('3D Projection of Tesseract')
                        ax_3d.set_xlabel('X')
                        ax_3d.set_ylabel('Y')
                        ax_3d.set_zlabel('Z')

                        dimensions = ['X', 'Y', 'Z', 'W']

                        for edge in edges:
                            points = rotated[list(edge)]
                            ax_parallel.plot(dimensions, points.T, 'b-', alpha=0.2)

                        for i, point in enumerate(rotated):
                            ax_parallel.plot(dimensions, point, 'ro-', alpha=0.7)

                        ax_parallel.set_title('Parallel Coordinates Plot')
                        ax_parallel.set_ylim([-2, 2])

                        fig.canvas.draw_idle()

                    slider_xy.on_changed(update)
                    slider_xz.on_changed(update)
                    slider_xw.on_changed(update)
                    slider_yw.on_changed(update)

                    update(0)

                    plt.show()


                visualize_tesseract()
            if figure == '4д цилиндр':
                import numpy as np
                import matplotlib.pyplot as plt
                from mpl_toolkits.mplot3d import Axes3D
                from matplotlib.animation import FuncAnimation


                def hyper_cylinder(radius, height, num_points):
                    theta = np.linspace(0, 2 * np.pi, num_points)
                    z = np.linspace(-height / 2, height / 2, num_points)
                    theta, z = np.meshgrid(theta, z)

                    x = radius * np.cos(theta)
                    y = radius * np.sin(theta)

                    return x, y, z


                radius = 1
                height = 2
                num_points = 100

                x, y, z = hyper_cylinder(radius, height, num_points)

                fig = plt.figure()
                ax = fig.add_subplot(111, projection='3d')
                ax.set_title('4д цилиндр')
                ax.set_xlabel('X-axis')
                ax.set_ylabel('Y-axis')
                ax.set_zlabel('Z-axis')


                def update(frame):
                    ax.cla()  # Очистка осей
                    ax.set_title('4д цилиндр')
                    ax.set_xlabel('X-axis')
                    ax.set_ylabel('Y-axis')
                    ax.set_zlabel('Z-axis')

                    angle = frame * np.pi / 180
                    x_rot = x * np.cos(angle) - z * np.sin(angle)
                    z_rot = x * np.sin(angle) + z * np.cos(angle)

                    ax.plot_surface(x_rot, y, z_rot, color='cyan', alpha=0.7)


                ani = FuncAnimation(fig, update, frames=np.arange(0, 360, 2), interval=100)

                plt.show()
        elif user_application == 'узнать id лица':
            import cv2
            import numpy as np
            from kivy.app import App
            from kivy.uix.button import Button
            from kivy.uix.boxlayout import BoxLayout
            from kivy.uix.image import Image
            from kivy.graphics.texture import Texture
            from kivy.clock import Clock

Иван Тырин, [5/4/2025 11:56 AM]
class FaceDetectionApp(App):
                def build(self):
                    self.capture = None
                    self.face_cascade = None
                    self.face_id = None
                    layout = BoxLayout(orientation='vertical')
                    self.image_widget = Image()
                    self.button = Button(text='Открыть камеру и сканировать лицо', size_hint=(1, 0.2))
                    self.button.bind(on_press=self.toggle_camera)
                    layout.add_widget(self.image_widget)
                    layout.add_widget(self.button)
                    return layout

                def toggle_camera(self, instance):
                    if self.capture is None:
                        self.capture = cv2.VideoCapture(0)
                        self.face_cascade = cv2.CascadeClassifier(
                            cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
                        Clock.schedule_interval(self.update, 1.0 / 30.0)
                        self.button.text = 'Сканирование...'
                    else:
                        Clock.unschedule(self.update)
                        self.capture.release()
                        self.capture = None
                        self.button.text = 'Открыть камеру и сканировать лицо'
                        print(f"ID лица сохранен: {self.face_id}")

                def update(self, dt):
                    ret, frame = self.capture.read()
                    if ret:
                        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
                        gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
                        faces = self.face_cascade.detectMultiScale(gray, 1.3, 5)
                        for (x, y, w, h) in faces:
                            cv2.rectangle(frame_rgb, (x, y), (x + w, y + h), (255, 0, 0), 2)
                            self.face_id = f"{x}_{y}_{w}_{h}"
                            cv2.putText(frame_rgb, f"ID: {self.face_id}", (x, y - 10),
                                        cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 2)
                        buf = frame_rgb.tostring()
                        texture = Texture.create(size=(frame.shape[1], frame.shape[0]), colorfmt='rgb')
                        texture.blit_buffer(buf, colorfmt='rgb', bufferfmt='ubyte')
                        self.image_widget.texture = texture


            FaceDetectionApp().run()
        else:
            print('Такого приложения нет, проверьте правильность написания названия приложения.')
