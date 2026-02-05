# LDream Website

Статический сайт для приложения LDream — лендинг, страница поддержки и политика конфиденциальности.

## Структура

```
ldream-website/
├── index.html        # Главная страница (лендинг)
├── support.html      # FAQ и поддержка
├── privacy.html      # Политика конфиденциальности
├── terms.html        # Условия использования
├── 404.html          # Страница ошибки
├── styles.css        # Стили
├── _headers          # Заголовки Cloudflare Pages
├── _redirects        # Редиректы Cloudflare Pages
└── favicon.png       # Иконка (нужно добавить)
```

## Деплой на Cloudflare Pages

### Вариант 1: Через Git (рекомендуется)

1. Создай репозиторий на GitHub:
   ```bash
   cd ldream-website
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/ldream-website.git
   git push -u origin main
   ```

2. Зайди на [Cloudflare Dashboard](https://dash.cloudflare.com/)

3. Перейди в **Workers & Pages** → **Create application** → **Pages**

4. Выбери **Connect to Git** и авторизуй GitHub

5. Выбери репозиторий `ldream-website`

6. Настройки сборки:
   - **Project name**: `ldream` (или другое имя)
   - **Production branch**: `main`
   - **Build command**: (оставь пустым)
   - **Build output directory**: `/` (или оставь пустым)

7. Нажми **Save and Deploy**

### Вариант 2: Прямая загрузка

1. Зайди на [Cloudflare Dashboard](https://dash.cloudflare.com/)

2. Перейди в **Workers & Pages** → **Create application** → **Pages**

3. Выбери **Upload assets**

4. Загрузи все файлы из папки `ldream-website`

5. Нажми **Deploy site**

## Настройка домена

После деплоя ты получишь URL вида `ldream.pages.dev`.

### Подключение своего домена:

1. В настройках проекта Pages перейди в **Custom domains**

2. Нажми **Set up a custom domain**

3. Введи домен (например, `ldream.app`)

4. Следуй инструкциям для настройки DNS:
   - Если домен на Cloudflare: автоматическая настройка
   - Если домен внешний: добавь CNAME запись

## Локальный просмотр

Для просмотра сайта локально:

```bash
cd ldream-website
npx serve .
```

Или через Python:
```bash
cd ldream-website
python3 -m http.server 8000
```

Затем открой http://localhost:8000

## Что нужно добавить

- [ ] `favicon.png` — иконка сайта (можно использовать иконку приложения)
- [ ] `og-image.png` — картинка для шеринга в соцсетях (рекомендуется 1200x630px)
- [ ] Обновить email адреса (`support@ldream.app`, `privacy@ldream.app`, `legal@ldream.app`)
- [ ] Обновить URL домена в мета-тегах (сейчас `https://ldream.app`)

## URL-адреса

После деплоя будут доступны:

- `/` — главная страница
- `/support` или `/support.html` — поддержка
- `/privacy` или `/privacy.html` — политика конфиденциальности  
- `/terms` или `/terms.html` — условия использования
- `/app` — редирект на App Store
- `/download` — редирект на App Store

## Обновление контента

Просто отредактируй HTML файлы и запуш изменения в Git. Cloudflare Pages автоматически задеплоит обновления.
