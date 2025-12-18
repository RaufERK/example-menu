# example-menu

Мини-пример использования `@tot/ui-kit` (Layout + меню) на Vite.

## Запуск
```bash
npm install
npm run dev
```

## Обновить либу @tot/ui-kit
```bash
npm run update
```
Скрипт билдит соседний `../tot-ui-kit` и ставит свежую версию из Git с `--force`.

## Тема и цвета
- Либа хранит тему в `localStorage` (`tot-ui-kit-theme`) и ставит атрибут `data-theme="light" | "dark"` на `html`.
- Все цвета приходят из triplex-токенов и переопределений в `@tot/ui-kit/src/global.css`.
- Цвет тёмной темы завязан на `--triplex-next-DropdownMobileList-Active_Background-1-5-0` (fallback `#1e2330`) и используется для фона меню и страницы.
- Текущая тема в коде:
  ```tsx
  import { useTheme } from '@tot/ui-kit'

  const theme = useTheme() // 'light' | 'dark'
  ```

## Где править
- Основные стили темы: `tot-ui-kit/src/global.css`
- Цвета меню: `tot-ui-kit/src/components/MainMenu/MainMenu.css`
- Цвет фона layout: `tot-ui-kit/src/components/Layout/styles.css`
