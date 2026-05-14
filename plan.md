---
created: 14.05.2026
project: [[personal-site-on-quarto]]
tags: #personal #quarto #plan
---

# Детальний план створення персонального сайту-візитівки на Quarto

## 1. Огляд проєкту

**Мета:** Створити сучасний персональний сайт-візитівку для Яценка Романа Миколайовича — директора Навчально-наукового інституту інформаційних технологій ХНЕУ ім. С. Кузнеця, доцента кафедри економічної кібернетики і системного аналізу, к.е.н.

**Технологія:** [Quarto](https://quarto.org/docs/websites/) — статичний генератор сайтів, що підтримує публікацію на GitHub Pages.

**Репозиторій:** [roman-yatsenko.github.io](https://github.com/roman-yatsenko/roman-yatsenko.github.io)

---

## 2. Технічні рішення

### 2.1. Тема та дизайн

- **Тема:** Bootswatch `flatly` або `cosmo` — мінімалістична, сучасна, добре читається.
  - Альтернатива: кастомна тема на основі SCSS змінних Quarto з акцентним кольором `#0d6efd` (IT-blue) та монопросторовим шрифтом для деталей.
- **Шаблон About-сторінки:** `trestles` (фото зліва, контент справа) — відповідно до вимог.
- **Навігація:** верхня горизонтальна панель (navbar) з логотипом-ініціалами `RY`.
- **Footer:** мінімальний — рік, GitHub-посилання, LinkedIn, Facebook.
- **Мова:** Українська (основна), з можливістю англомовних заголовків метаданих.

### 2.2. Структура файлів проєкту

```
roman-yatsenko.github.io/
├── _quarto.yml          # конфігурація сайту, навігація, тема
├── index.qmd            # About (головна)
├── experience.qmd       # Досвід та освіта
├── teaching.qmd         # Викладання
├── projects.qmd         # Проєкти
├── science.qmd          # Наука
├── contacts.qmd         # Контакти
├── styles.scss          # кастомні стилі
├── images/
│   └── avatar.jpg       # фото з it.hneu.edu.ua/contacts/
└── .github/
    └── workflows/
        └── publish.yml  # GitHub Actions для автодеплою
```

### 2.3. Конфігурація `_quarto.yml`

```yaml
project:
  type: website
  output-dir: docs

website:
  title: "Роман Яценко"
  favicon: images/favicon.ico
  navbar:
    left:
      - href: index.qmd
        text: Про мене
      - href: experience.qmd
        text: Досвід
      - href: teaching.qmd
        text: Викладання
      - href: projects.qmd
        text: Проєкти
      - href: science.qmd
        text: Наука
      - href: contacts.qmd
        text: Контакти
    right:
      - icon: github
        href: https://github.com/roman-yatsenko
      - icon: linkedin
        href: https://linkedin.com/in/yatsenkorm
      - icon: facebook
        href: https://www.facebook.com/profile.php?id=61576990610124

format:
  html:
    theme: [flatly, styles.scss]
    toc: false
    lang: uk
```

---

## 3. Сторінки сайту: детальний зміст

### 3.1. `index.qmd` — Про мене (About)

**Шаблон:** `trestles`

**YAML-заголовок:**
```yaml
---
title: "Роман Яценко"
about:
  template: trestles
  image: images/avatar.jpg
  links:
    - icon: github
      text: GitHub
      href: https://github.com/roman-yatsenko
    - icon: linkedin
      text: LinkedIn
      href: https://linkedin.com/in/yatsenkorm
    - icon: telegram
      text: Telegram
      href: https://t.me/YaRo_Kharkiv
    - icon: envelope
      text: Email
      href: mailto:roman.yatsenko@hneu.net
    - icon: facebook
      text: Facebook
      href: https://www.facebook.com/profile.php?id=61576990610124
---
```

**Зміст:**
- **Заголовок блоку:** К.е.н., доцент | Директор ННІ ІТ ХНЕУ
- **Фото:** завантажити з https://it.hneu.edu.ua/contacts/ та зберегти як `images/avatar.jpg`
- **Основний опис (про себе):**
  - Директор (керівник) [Навчально-наукового інституту інформаційних технологій ХНЕУ ім. С. Кузнеця](https://it.hneu.edu.ua/)
  - Доцент кафедри [економічної кібернетики і системного аналізу](https://ek.hneu.edu.ua/)
  - Технічний керівник проєкту ["Єдиний кабінет ХНЕУ ім. С. Кузнеця"](https://cabinet.hneu.edu.ua/)
- **Блок напрямів діяльності** (3 колонки або картки):
  - 🎓 **Освіта** — розробка цифрових освітніх екосистем університету, e-learning, підтримка безперервності вищої освіти
  - 💻 **Розробка** — веброзробка на Python/Django, інформаційні системи для ЗВО, агентний AI development
  - 🔬 **Наука** — моделі адаптивного управління навчальним процесом, IT в управлінні, машинне навчання в економіці

---

### 3.2. `experience.qmd` — Досвід та освіта

**Зміст:**

#### Посади (Досвід роботи)
| Роки | Посада | Місце |
|------|--------|-------|
| 2024 — тепер | Директор ННІ ІТ | [ХНЕУ ім. С. Кузнеця](https://it.hneu.edu.ua/) |
| ... | Доцент кафедри економічної кібернетики | [ХНЕУ ім. С. Кузнеця](https://ek.hneu.edu.ua/) |

> Детальний перелік посад — з https://ek.hneu.edu.ua/vykladachi/yatsenko-roman-mykolajovych/ (секція "Досвід роботи")

#### Освіта
> Заповнити з https://ek.hneu.edu.ua/vykladachi/yatsenko-roman-mykolajovych/ (секція "Освіта")
- ХНЕУ ім. С. Кузнеця, к.е.н. (захист дисертації)
- ...

#### Підвищення кваліфікації та сертифікати
- Міжгалузевий інститут ПК ХНЕУ, «Використання ППП Statistica» (2007)
- Регіональний інститут безперервної освіти ПНДУ, «Математичні моделі в економіці» (2013)
- ХНЕУ, «Розвиток комунікативної компетентності НПП» (2018) — [сертифікат](https://drive.google.com/file/d/1Lk2Ns9T2mZgs1AJpfPxM56r9gBVSRxBd/view?usp=drive_link)
- HVD Hotels (Bulgaria, Varna), «Development of multimedia technologies for international networks support: European experience» (2022) — [сертифікат](https://ek.hneu.edu.ua/wp-content/uploads/2024/02/Roman-YATSENKO_2022_rotated.pdf)
- Genesis (Київ), «Створення та розвиток IT-продуктів» (2022) — [сертифікат](https://drive.google.com/file/d/1pME5BuMcImYMMj-I5bPFgzu7epujv7GW/view?usp=drive_link)
- ХНЕУ, «Академічна доброчесність: практика застосування» (2022) — [сертифікат](https://drive.google.com/file/d/1ddZE2kUDbnSSqsdOgoIxStHDqHbVz9jt/view?usp=drive_link)
- IBM / Coursera, «Fundamentals of Scalable Data Science» (2021) — [сертифікат](https://drive.google.com/file/d/1LPLoO4_C0au076ZlZsiOycPFd1XHvohX/view?usp=drive_link)
- IBM / Coursera, «Advanced Machine Learning and Signal Processing» (2021) — [сертифікат](https://drive.google.com/file/d/1t7YdOFRZKG8cZdxW-jfmylDUFAP7fSHJ/view?usp=drive_link)
- IBM / Coursera, «Applied AI with DeepLearning» (2021) — [сертифікат](https://drive.google.com/file/d/16FOiua7aqPqYwFFv9Kb3RMFyZf3H7Q0x/view?usp=drive_link)
- «Основи Web UI розробки 2022» (2022) — [сертифікат](https://drive.google.com/file/d/1NDAKqoBfURuGI7YoUA0LSfD-b-suhQ37/view?usp=drive_link)
- Prometheus, «Як створити масовий відкритий онлайн-курс» (2016)
- Компанія Prognoz, «Математичні моделі в економіці та їх комп'ютерна реалізація» (2013)

#### Нагороди та відзнаки
| Рік | Відзнака |
|-----|---------|
| 2009 | Переможець IV обласного конкурсу "Найкращий молодий науковець Харківщини" (суспільно-економічні науки) |
| 2017 | Почесна грамота Департаменту освіти Харківської міської ради |
| 2018 | Подяка Міністерства освіти і науки України |
| 2019 | Почесна Грамота Адміністрації Шевченківського району Харківської міської Ради |
| 2021 | Грамота МОН України |
| 2021 | Подяка Харківського міського голови |
| 2023 | Почесна грамота МОН України |
| 2024 | Почесна грамота Харківської міської ради |

---

### 3.3. `teaching.qmd` — Викладання

**Зміст:**

#### Вступ
Викладацька діяльність на [кафедрі економічної кібернетики і системного аналізу](https://ek.hneu.edu.ua/vykladachi/yatsenko-roman-mykolajovych/) ХНЕУ ім. С. Кузнеця.

#### Головна дисципліна — акцент
> Виділити окремим блоком/картою:

**[Програмування](https://pns.hneu.edu.ua/course/view.php?id=8027)** — флагманська дисципліна, що охоплює основи алгоритмізації та програмування, об'єктно-орієнтований підхід, прикладне застосування Python у вирішенні реальних задач.

#### Повний перелік навчальних дисциплін
- [Програмування](https://pns.hneu.edu.ua/course/view.php?id=8027) ⭐ *(головна дисципліна)*
- [Сучасні технології аналітики даних в середовищі Python](https://pns.hneu.edu.ua/course/view.php?id=8027)
- Web-технології
- Бази даних
- Електронна комерція
- Методи і моделі машинного навчання на мові програмування Python
- Сучасні парадигми програмування
- Тренінг «Підвищення персональної продуктивності»

#### Розклад
[Персональний розклад занять](http://services.hneu.edu.ua/) на сайті ХНЕУ ім. С. Кузнеця.

---

### 3.4. `projects.qmd` — Проєкти

**Зміст:**

#### Головний проєкт — "Єдиний кабінет ХНЕУ ім. С. Кузнеця" (виділити окремо)

**Роль:** Технічний керівник проєкту

[**Єдиний кабінет ХНЕУ ім. С. Кузнеця**](https://cabinet.hneu.edu.ua/) — інформаційна система для автоматизації бізнес-процесів та управління даними освітнього процесу університету.

**Призначення:**
- Персоналізовані інформаційні сервіси для всіх учасників освітнього процесу
- Інтеграція КІС та ПНС (Moodle) в єдиному середовищі
- Додаткова функціональність поверх існуючих систем університету

**Підсистеми:**
- **Кабінет здобувача:** індивідуальний навчальний план, розклад, оцінки
- **Кабінет викладача:** відомості успішності, документи освітнього процесу
- **Кабінет співробітника:** довідники, бізнес-процеси, статистика, звіти

**Технологічний стек:**

| Категорія | Технології |
|-----------|-----------|
| Клієнт | Bootstrap, Tabulator |
| Сервер | Python, Django, Django REST Framework |
| База даних | MySQL |
| Тестування | Django TestCase, Selenium |
| Документація | MkDocs |

> **Інновація:** У проєкті започатковано використання **агентного AI development** на основі фреймворку [OpenSpec](https://github.com/Fission-AI/OpenSpec).

#### Інші проєкти

**[Сайт ПНС ХНЕУ ім. С. Кузнеця](https://pns.hneu.edu.ua/)** — компетенції у Moodle: розробка, адміністрування та розвиток платформи персональних навчальних систем університету.

**[UniTwin](https://unitwin.lpnu.ua/en)** — участь у проєкті Erasmus+ KA2 "University Infrastructure for Workforce Development focusing on Twin Transition" (Green. Digital. Inclusive.), №101236638. Партнери: Університет Лісабону (координатор), KTH Royal Institute of Technology (Швеція), Університет Алькала (Іспанія), ЛНУ «Львівська Політехніка», ХНЕУ та ін.

> Додаткові проєкти — доповнити з [LinkedIn / Projects](https://www.linkedin.com/in/yatsenkorm/details/projects/)

---

### 3.5. `science.qmd` — Наука

**Зміст:**

#### Наукові профілі
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-4285F4?style=flat)](https://scholar.google.com.ua/citations?hl=uk&user=IS9XHAQAAAAJ)
[![ORCID](https://img.shields.io/badge/ORCID-A6CE39?style=flat)](https://orcid.org/0000-0001-7968-6890)
[![Scopus](https://img.shields.io/badge/Scopus-E9711C?style=flat)](https://www.scopus.com/authid/detail.uri?authorId=57218566711)

Посилання: [Google Академія](https://scholar.google.com.ua/citations?hl=uk&user=IS9XHAQAAAAJ) | [ORCID 0000-0001-7968-6890](https://orcid.org/0000-0001-7968-6890) | [Scopus](https://www.scopus.com/authid/detail.uri?authorId=57218566711)

#### Наукові інтереси

**Головний напрям:**
- Моделі адаптивного управління навчальним процесом в системах дистанційного навчання
- Моделювання цінової політики підприємства
- Інформаційні системи і технології в управлінні

**Поточні інтереси:**
- Уніфіковані системи створення навчального контенту
- Економіко-математичне моделювання в системах електронної комерції
- Мультимедійні та освітні дистанційні системи

**Інший дослідницький досвід:**
- Нейромережеві методи і методи машинного навчання в економічному моделюванні
- Імітаційне моделювання фінансових потоків на макрорівні

#### Публікації
Загальна кількість публікацій — **124**: наукових — 78 (зокрема 12 монографій); навчально-методичних — 42 (з них 5 навчальних посібників, 2 з грифом МОН).

#### Ключовий науковий проєкт (виділити)

**Керівник науково-дослідної роботи:**

> **"Розробка відкритої цифрової інклюзивної освітньої екосистеми університету для забезпечення безперервності вищої освіти в Україні"**
>
> Терміни: 01.01.2026 — 31.12.2027 | Фінансування: загальний фонд державного бюджету
>
> Проєкт спрямований на розробку науково обґрунтованої моделі та практичних рекомендацій щодо створення відкритої цифрової інклюзивної освітньої екосистеми (ВЦІОЕС) для ЗВО України. Передбачає інтеграцію LMS, адміністративних систем, підтримку мікрокваліфікацій, інклюзивного навчання та відкритих освітніх ресурсів (OER).

---

### 3.6. `contacts.qmd` — Контакти

**Зміст:**
- Email: [roman.yatsenko@hneu.net](mailto:roman.yatsenko@hneu.net)
- Telegram: [@YaRo_Kharkiv](https://t.me/YaRo_Kharkiv)
- LinkedIn: [linkedin.com/in/yatsenkorm](https://linkedin.com/in/yatsenkorm)
- GitHub: [github.com/roman-yatsenko](https://github.com/roman-yatsenko)
- Facebook: [Роман Яценко](https://www.facebook.com/profile.php?id=61576990610124)
- Місце роботи: [ХНЕУ ім. С. Кузнеця](https://hneu.edu.ua/), пр. Науки 9-А, Харків, 61166, Україна

---

## 4. Кастомні стилі (`styles.scss`)

```scss
// Акцентний IT-колір та монопросторовий шрифт для коду/тегів
$primary: #0d6efd;
$font-family-monospace: 'JetBrains Mono', 'Fira Code', monospace;

// Картки для блоків напрямів діяльності
.activity-card {
  border-left: 4px solid $primary;
  padding: 1rem 1.5rem;
  margin-bottom: 1rem;
  background: rgba($primary, 0.04);
  border-radius: 0 8px 8px 0;
}

// Виділення головного проєкту
.featured-project {
  border: 2px solid $primary;
  border-radius: 8px;
  padding: 1.5rem;
  margin-bottom: 2rem;
}
```

---

## 5. Деплой на GitHub Pages

### 5.1. Метод: GitHub Actions (рекомендований)

Файл `.github/workflows/publish.yml`:
```yaml
name: Publish to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: quarto-dev/quarto-actions/publish@v2
        with:
          target: gh-pages
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### 5.2. Налаштування репозиторію
- Репозиторій: `roman-yatsenko/roman-yatsenko.github.io`
- GitHub Pages: Source → GitHub Actions
- URL сайту: `https://roman-yatsenko.github.io`

---

## 6. Порядок виконання (Checklist)

### Фаза 1 — Підготовка
- [ ] Встановити Quarto CLI (https://quarto.org/docs/get-started/)
- [ ] Ініціалізувати Quarto website проєкт в поточному workspace `quarto create project website`
- [ ] Налаштувати `_quarto.yml` (навігація, тема, мова)
- [ ] Завантажити фото з https://it.hneu.edu.ua/contacts/ → `images/avatar.jpg`
- [ ] Створити `styles.scss` з кастомними стилями

### Фаза 2 — Наповнення сторінок
- [ ] `index.qmd` — About з шаблоном trestles, фото, посилання, блок напрямів
- [ ] `experience.qmd` — Досвід, освіта, сертифікати, нагороди
- [ ] `teaching.qmd` — Дисципліни з посиланнями, акцент на Програмування
- [ ] `projects.qmd` — Єдиний кабінет (головний), UniTwin, ПНС, LinkedIn-проєкти
- [ ] `science.qmd` — Профілі, інтереси, публікації, ODEES-проєкт
- [ ] `contacts.qmd` — Усі контакти включно з Facebook

### Фаза 3 — Технічна перевірка
- [ ] Локальний білд: `quarto preview`
- [ ] Перевірити всі посилання (особливо на курси ПНС, профілі)
- [ ] Перевірити адаптивність (мобільна версія)
- [ ] Перевірити метадані (title, description для SEO)

### Фаза 4 — Публікація
- [ ] `git push` до репозиторію `roman-yatsenko.github.io`
- [ ] Перевірити GitHub Actions → успішний деплой
- [ ] Верифікувати сайт на `https://roman-yatsenko.github.io`

---

## 7. Додаткові деталі та примітки

### Фото
- URL для отримання: https://it.hneu.edu.ua/contacts/ — секція директора
- Резервне: https://ek.hneu.edu.ua/wp-content/gallery/prepodavately-kafedry/YAtsenko-Roman-Nykolaevych.jpg

### Курси ПНС
- Програмування: https://pns.hneu.edu.ua/course/view.php?id=8027
- Сучасні технології аналітики даних в Python: уточнити правильний `id` курсу на ПНС (у промпті вказано однаковий id для обох — перевірити)

### Проєкти з LinkedIn
- Потребує ручного перегляду LinkedIn-профілю (https://www.linkedin.com/in/yatsenkorm/details/projects/) — LinkedIn не дозволяє автоматичний парсинг
- Додати проєкти вручну після перегляду

### OpenSpec
- Framework для агентного AI development: https://github.com/Fission-AI/OpenSpec
- Використовується в проєкті "Єдиний кабінет" — відзначити як інновацію

### Quarto About Templates
- Документація: https://quarto.org/docs/websites/website-about.html
- Обраний шаблон: `trestles` (бічна панель з фото і посиланнями, основний контент справа)
