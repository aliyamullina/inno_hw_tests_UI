[![Build Status](https://app.travis-ci.com/aliyamullina/inno_hw_ui_attestation.svg?branch=main)](https://app.travis-ci.com/aliyamullina/inno_hw_ui_attestation)

# Автотестирование UI
### Web-приложение
Платформа для онлайн образования [qacoursemoodle.innopolis.university](https://qacoursemoodle.innopolis.university). 
Рассматривается пользователь с правами доступа к созданию своего курса.

### Описание
Основной задачей тестирования web-приложения было покрыть минимальным набором тест-кейсов уровень функционального тестирования в подтверждение того, что приложение выполняет свои основные функции. 
И автоматизировать тест-кейсы с помощью Selenium и Pytest, по паттерну Page Object и шаблону проектирования Фасад.

# Содержание
- [Тест-комплекты](#тест-комплекты)
    + [Тест-кейсы на авторизацию](#тест-кейсы-на-авторизацию)
    + [Тест-кейсы на изменение персональных данных](#тест-кейсы-на-изменение-персональных-данных)
    + [Тест-кейсы на создание нового курса](#тест-кейсы-на-создание-нового-курса)
- [Установка](#установка)
    + [Репозиторий](#репозиторий)
    + [Отчеты Allure](#отчеты-allure)
    + [Зависимости](#зависимости)
- [Запуск](#запуск)
    + [С помощью tox](#с-помощью-tox)
    + [С помощью pytest](#с-помощью-pytest)
    + [По тестам](#по-тестам)

# Тест-комплекты
### Тест-кейсы на авторизацию 
```
tests/auth/test_auth.py
```
#### Позитивный тест-кейс:
- Авторизоваться с действительными данными: логин и пароль.

#### Негативные тест-кейсы:
- Авторизоваться с не действительными данными: логин и пароль.
- Авторизоваться с пустыми данными: логин или пароль.

### Тесты-кейсы на изменение персональных данных 
```
tests/personaldata/test_personaldata.py
```
#### Позитивные тест-кейсы:
- Изменить основные персональные данные, указав действительные данные: имя, фамилия, почта.
- Изменить дополнительные персональные данные в блоке об имени, указав действительные данные: имя и фамилия в фонетике, отчество, альтернативное имя.
- Добавить тег с действительными данными.

#### Негативные тест-кейсы:
- Изменить основные персональные данные с не действительными данными: имя, фамилия, почта.
- Изменить основные персональные данные с не действительным email.
- Изменить имя или фамилию на пустое значение.

### Тесты-кейсы на создание нового курса 
```
tests/newcourse/test_newcourse.py
```
#### Позитивный тест-кейс:
- Создать курс с действительными данными: длинное название и короткое название курса.

#### Негативный тест-кейс:
- Создать курс с пустыми данными: длинное название или короткое название курса.

# Установка
### Репозиторий
```
git clone https://github.com/aliyamullina/inno_hw_ui_attestation.git
```
### Виртуальное окружение
Создание, перейти в директорию проекта и выполнить:
```
python -m venv venv
```
Активация для Windows:
```
venv\Scripts\activate.bat
```

Активация для Linux и MacOS:
```
source venv/bin/activate
```
### Отчеты Allure
[docs.qameta.io/allure/#_get_started](https://docs.qameta.io/allure/#_get_started)

### Зависимости
```
pip install -r requirements.txt
```

# Запуск
### С помощью tox
Ввести в терминале:
```
tox
```
### С помощью pytest
Ввести в терминале:
```
pytest --alluredir=.allure_reports
```
```
allure serve .allure_reports
```
### По тестам
Тесты на авторизацию. Ввести в терминале:
```
pytest -m auth 
```

Тесты на изменение персональных данных. Ввести в терминале:
```
pytest -m personal_data 
```

Тесты на создание нового курса. Ввести в терминале:
```
pytest -m new_course 
```
