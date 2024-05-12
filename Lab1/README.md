# Документация программной системы

## Введение

Эта программная система представляет собой систему, имитирующую работу операционной системы компьютера, 
включающую в себя различные классы для представления ядра, процессов, сетевых протоколов, файловой системы.

## Классы и методы

### Класс OperatingSystem

Класс для представления операционной системы.

#### Основные методы

- `__init__(self, name)`: Инициализация объекта класса OperatingSystem
- `start(self)`: Запускает ОС
- `shutdown(self)`: Выключает ОС, освобождает ресурсы и сохраняет состояние системы
- `form_network(self, os: 'OperatingSystem')`: Связывает в сеть ОС с другой ОС, позволяя пересылать сигналы между ними
- `send(self, content: str, OS: str)`: Отправляет сигнал другой ОС, которая связана протоколом
- `create_file(self, name: str, content: str)`: Создаёт в файловой системе новый файл
- `delete_file(self, name: str)`: Удаляет файл из файловой системы
- `check_driver(self, name: str)`: Проверяет, установлен ли драйвер
- `view_content(self, name: str)`: Возвращает содержимое файла 
- `fork(self, resources: int)`: Создаёт новый процесс в ядре
- `terminate_process(self, name: str)`: Удаляет процесс из ядра
- `install_driver(self, name: str)`: Устанавливает драйвер

### Класс Kernel

Класс для представления ядра.

#### Основные методы

- `start(self)`: Запускает ядро ОС, создаёт первый процесс init
- `shutdown(self)`: Удаляет все процессы, освобождает ресурсы
- `create_signal(self, content: str)`: Создаёт сигнал в ядре 
- `create_process(self, name: str, resource: int)`: Возвращает новый созданный процесс, выделяет для него ресурсы
- `terminate_process(self, process: Process)`: Удаляет процесс, высвобождает ресурсы

### Класс Signal

Класс для представления сигнала.

#### Методы

- `content(self, content)`: Устанавливает содержимое для сигнала
- `content(self):`: Возвращает содержимое файла

### Класс NetworkProtocol

Класс для представления сетевого протокола

#### Методы

- `add(self, os)`: Добавляет ОС в список ОС, связанных в сеть
- `show_linked_osc(self):`: Выводит все ОС, связанные в сеть

### Класс FileSystem

Класс для представления файловой системы.

#### Методы

- `create_file(self, name: str, content: str)`: Добавляет новый созданный файл в список файлов
- `delete_file(self, file: str)`: Удаляет файл из списка файлов
- `show_all_files(self)`: Выводит все файлы в файловой системе

### Класс Process

Класс для представления процесса.

#### Методы

- `__init__(self, name, resources)`: Инициализация объекта класса Process.
- `checking(self)`: Проверка дипломов студентов.
- `print_student_info(self)`: Вывод информации о студентах.

### Класс Driver

Класс для представления драйвера.   

#### Методы

- `__init__(self, name)`: Инициализация объекта класса Driver.
- `name(self)`: Возвращает название драйвера

### Класс UserInterface

Класс для представления пользовательского интерфейса

#### Методы

- `read_file(self, file: File)`: Возвращает содержимое передавваемого файла
