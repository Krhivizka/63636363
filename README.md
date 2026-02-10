# Базовый класс "Книга"
class Book:
    def __init__(self, title, author, year):
        self.title = title
        self.author = author
        self.year = year

    def get_info(self):
        return f"'{self.title}' by {self.author} ({self.year})"

# Наследуемый класс "Учебник"
class Textbook(Book):
    def __init__(self, title, author, year, subject):
        super().__init__(title, author, year)
        self.subject = subject

    def get_info(self):
        base_info = super().get_info()
        return f"{base_info} - Subject: {self.subject}"

# Наследуемый класс "Художественная книга"
class Novel(Book):
    def __init__(self, title, author, year, genre):
        super().__init__(title, author, year)
        self.genre = genre

    def get_info(self):
        base_info = super().get_info()
        return f"{base_info} - Genre: {self.genre}"

# Пример использования
book1 = Book("Война и мир", "Лев Толстой", 1869)
textbook1 = Textbook("Математика для 5 класса", "Иванов И.И.", 2020, "Математика")
novel1 = Novel("Преступление и наказание", "Фёдор Достоевский", 1866, "Психологический роман")

print(book1.get_info())
print(textbook1.get_info())
print(novel1.get_info())
