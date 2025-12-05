# `example-menu`

Мини-приложение на React + Vite, показывающее, как использовать общий пакет `@data-platform/ui-shell` в отдельном проекте (можно вынести в другой репозиторий).

## Как запустить

```bash
yarn install          # один раз в корне монорепы
yarn workspace example-menu dev
```

По умолчанию меню тянет данные с `http://localhost:4000/idp/single-menu-data/VKIIw4zpK-wnEuFag4GXO`. Можно переопределить URL:

```bash
VITE_API_BASE=https://prod.api yarn workspace example-menu dev
```

## Как это повторить в другом репозитории

1. Установить пакет, опубликованный в приватном реестре:  
   `yarn add @data-platform/ui-shell`
2. В компоненте приложения:

```tsx
import { Layout } from '@data-platform/ui-shell'

const apiBase = import.meta.env.VITE_API_BASE ?? 'https://api.example.com'

export const App = () => (
  <Layout
    menuProps={{
      baseUrl: apiBase,
      activeAppId: 'example',
      systemTitle: 'Example Platform',
    }}
  >
    {/* контент */}
  </Layout>
)
```

Можно вместо `baseUrl` передать готовый массив приложений через `menuProps.apps`.

## Зачем проект

- Демонстрирует, что общий Layout/Menu живут отдельно от `new-frontend`.
- Показывает коллегам минимальный набор шагов для интеграции.
- Использует Yarn workspaces, поэтому отражает реальную локальную разработку.
# example-menu
