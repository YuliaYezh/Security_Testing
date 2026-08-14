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
- **IP:** <img width="550" height="104" alt="image" src="https://github.com/user-attachments/assets/36d616bb-cdf5-46a1-8f61-532eda46d7a5" />
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

---
-
