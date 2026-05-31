# SocPublic Bot

Отдельный бот для мониторинга VK страницы `smm.studia` и автоматического создания заданий на SocPublic.

## Что делает

1. Каждую минуту проверяет последний пост в `vk.com/smm.studia`
2. При появлении нового поста — создаёт задание на SocPublic через эмуляцию формы (cookies)
3. Задание создаётся **без баланса** — нужно вручную пополнить и запустить через сайт SocPublic

## Запуск на Railway

1. Создать новый проект Railway, подключить этот репозиторий
2. Добавить переменные окружения:
   - `SP_SECRET` — cookie `secret` из SocPublic
   - `SP_SESSION_ID` — cookie `session_id` из SocPublic
   - `SP_PARENT_ID` — cookie `parent_id` (обычно user id)
   - `PYTHONUNBUFFERED=1` — для нормальных логов
3. Deploy

## Как обновить cookies

Если бот пишет "Cookies устарели" в логах:

1. Зайди на SocPublic в браузере, авторизуйся
2. F12 → Application → Cookies → `socpublic.com`
3. Скопируй значения cookies `secret`, `session_id`, `parent_id`
4. Обнови в Railway → Variables
5. Передеплой произойдёт автоматически

## Следующие шаги (TODO)

- [ ] Автоматическое пополнение баланса задания (7-14 заявок)
- [ ] Автоматический запуск задания
- [ ] Уведомления в Telegram о созданных заданиях
