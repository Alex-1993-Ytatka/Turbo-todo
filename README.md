# TURBO TODO — v2 (Offline + i18n + Themes + Stats + CI/CD)

Добавлено:
- Offline-режим с очередью операций + ручной синк
- i18n (ru/en/uk) через i18next
- Тёмная/светлая темы, переключатель
- Экран статистики (по задачам, streak/points)
- Backend: /me и /sync, soft-delete для задач
- CI/CD: GitHub Actions для EAS, `eas.json`

## Запуск
### Бэкенд
```bash
cd backend
cp .env.example .env
npm install
npx prisma migrate dev --name add_offline_and_stats
npm run dev
```

### Фронтенд
```bash
cd frontend
npm install
npm run start
```

### APK через EAS
```bash
npm i -g eas-cli
cd frontend
eas login
eas build -p android --profile preview
```

### Синк (ручной)
На экране Home кнопка "Sync" — отправляет локальные изменения и тянет серверные.

