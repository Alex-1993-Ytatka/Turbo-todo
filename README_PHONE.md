
# 📱 Установка APK ТОЛЬКО С ТЕЛЕФОНА (Android)

Без ПК, только телефон + браузер.

## 0) Что у тебя уже есть
- Этот архив проекта: **turbo-todo-phone-build.zip**
- Аккаунт GitHub (можно создать на github.com)
- Аккаунт Expo (expo.dev)

## 1) Залить проект на GitHub
1. Открой **github.com** → **New repository** → Назови `turbo-todo` → Create.
2. Нажми **Add file → Upload files**.
3. Загрузить **весь** архив `turbo-todo-phone-build.zip` или его содержимое (папки backend, frontend, .github и т.д.).
4. Нажми **Commit changes**.

## 2) Создать токен Expo и добавить в GitHub Secrets
1. Зайди на **expo.dev** → Profile → **Access Tokens** → **Create new token** → Скопируй токен.
2. Вернись в GitHub → твой репозиторий → **Settings → Secrets and variables → Actions → New repository secret**.
3. Имя секрета: **EXPO_TOKEN**. Значение: токен из Expo. Сохрани.

> В репозитории уже есть workflow `.github/workflows/eas.yml` — он соберёт APK автоматически при каждом пуше.

## 3) Запустить сборку (автоматически)
1. В GitHub открой **Actions** → workflow **EAS Android Build** → появится новый запуск.
2. Открой ран, дождись окончания. В логах будет ссылка на билд на Expo.

## 4) Скачать APK на телефон
1. Нажми ссылку из логов **(expo.dev/accounts/.../projects/turbo-todo/builds/...)**.
2. На странице Expo выбери **Download APK**.
3. Подтверди установку APK (разреши установку из неизвестных источников).

Готово. Приложение установлено ✅

### Примечания
- Мы форсируем выпуск **APK** (см. `frontend/eas.json`: `build.preview.android.buildType = "apk"`).
- Для продакшн-публикации в Google Play лучше собирать **AAB** (`buildType: "app-bundle"`).
