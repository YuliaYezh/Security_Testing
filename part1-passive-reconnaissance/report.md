# Часть 1: Пассивная разведка

## Цель
Собрать максимально возможную информацию о трёх веб-ресурсах, используя только открытые источники и пассивные методы.

## Инструменты
- `host`
- `whatweb`
- Dnsdumpster
- `robots.txt`, `sitemap.xml`
- Google Dorks

## Ход работы

### 1. `penzgtu.ru`
`83.234.199.28`, `83.234.199.70`

- **Редиректы:** цепочка через `/DDoS01/` → `www.penzgtu.ru`
- **Веб-сервер:** nginx 1.14.1
- **CMS:** TYPO3 4.5
- **PHP:** 5.6.27
- **Куки:** `fe_typo_user`
- **Email:** `rector@penzgtu.ru`
- **robots.txt:** отсутствует
- **sitemap.xml:** не найден
- **Google Dorks:** `site:penzgtu.ru intitle:"Вход"` - найдены страницы авторизации.

### 2. `edu.penzgtu.ru`
- **IP:** `83.234.199.15`
- **Сервер:** nginx 1.14.1, PHP 7.4.12
- **CMS:** Moodle
- **Библиотеки:** jQuery 3.5.1
- **Куки:** `MoodleSession` (HttpOnly)
- **robots.txt:** запрет для Amazonbot
- **sitemap.xml:** доступен
- **Email:** `edumail@penzgtu.ru`

### 3. `stinfo.penzgtu.ru`
- **IP:** `83.234.199.70`
- **Редиректы:** через `/DDoS01/` → `/auth/login`
- **Фреймворк:** Flask (Werkzeug)
- **Библиотеки:** Bootstrap 3.3.7, jQuery 1.12.4
- **Куки:** `session` (HttpOnly)
- **robots.txt:** отсутствует
- **sitemap.xml:** не найден

## Результаты
- Наиболее информативным оказался `penzgtu.ru`.
- Отсутствие `robots.txt` на двух сайтах может раскрывать скрытые каталоги.
- Найдены почтовые адреса, которые могут быть использованы для социальной инженерии.
- Google Dorks позволил найти страницы входа, что указывает на наличие пользовательских зон.


## Скриншоты

<img width="550" height="104" alt="image" src="https://github.com/user-attachments/assets/2b0b897e-19e3-4206-abda-7ae475c019dc" />

Рисунок 1 - Применение команды host
<img width="753" height="273" alt="image" src="https://github.com/user-attachments/assets/d2fb231e-6c9e-4882-86b8-410aa3cdc8e6" />

Рисунок 2 - Применение команды whatweb
<img width="990" height="660" alt="image" src="https://github.com/user-attachments/assets/e6b69278-c15f-43d8-ba4a-95258cdc5acf" />

Рисунок 3 - Результат работы Dnsdumpster
<img width="1065" height="645" alt="image" src="https://github.com/user-attachments/assets/4b45caed-018e-42c9-98b7-d8c2075dc3a1" />

Рисунок 4 - Результат работы Dnsdumpster
