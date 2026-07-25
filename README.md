# LocalChat.Gateway

Единая точка входа API и WebSocket для клиентов LocalChat (Web и Admin). Проксирует запросы в микросервисы, проверяет JWT, задаёт CORS и сквозные заголовки.

## Назначение

- YARP (или эквивалент) reverse proxy;
- маршруты `/api/identity`, `/api/chat`, `/api/realtime`, `/api/media`, `/api/calls`, `/api/notifications`;
- проброс SignalR/WebSocket в RealtimeService (и позже Call signaling);
- единый публичный origin для UI.

## Стек

- .NET 10
- YARP
- JWT Bearer validation

## Документация

- [Обзор](docs/overview.md)
- [TODO](docs/todo.md)

## Запуск

Появится вместе с skeleton проекта. В стеке поднимается через [LocalChat.Orchestrator](https://github.com/MuskatGroup/LocalChat.Orchestrator).

Плановый порт: **5000**.

## Связанные репозитории

| Репозиторий | Роль |
|---|---|
| [LocalChat.Orchestrator](https://github.com/MuskatGroup/LocalChat.Orchestrator) | Compose |
| [LocalChat.IdentityService](https://github.com/MuskatGroup/LocalChat.IdentityService) | Auth upstream |
| [LocalChat.ChatService](https://github.com/MuskatGroup/LocalChat.ChatService) | Chat upstream |
| [LocalChat.RealtimeService](https://github.com/MuskatGroup/LocalChat.RealtimeService) | WS upstream |
| [LocalChat.Web](https://github.com/MuskatGroup/LocalChat.Web) | Клиент |
| [LocalChat.Admin](https://github.com/MuskatGroup/LocalChat.Admin) | Админка |

## Лицензия

Apache-2.0 — см. [LICENSE](LICENSE).
