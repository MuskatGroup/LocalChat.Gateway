# Gateway — обзор

## Ответственность

- принять весь внешний HTTP/WS трафик;
- аутентифицировать запросы (JWT), кроме публичных endpoint'ов заявки/логина;
- маршрутизировать в нужный сервис;
- проставлять `X-Correlation-Id`;
- ограничивать CORS под Web (3000) и Admin (3001).

## Планируемые маршруты

| Prefix | Upstream |
|---|---|
| `/api/identity` | IdentityService |
| `/api/chat` | ChatService |
| `/hubs` / `/api/realtime` | RealtimeService |
| `/api/media` | MediaService (P1) |
| `/api/calls` | CallService (P2) |
| `/api/notifications` | NotificationService (P1) |
| `/health` | локальный health |

Admin API Identity (approve/reject) доступен только с ролью `Admin` — Gateway не дублирует бизнес-логику, но обязан не пропускать неавторизованных.

## Что сервис НЕ делает

- не хранит сообщения и пользователей;
- не расшифровывает E2EE;
- не реализует бизнес-правила заявок (это Identity).

## Зависимости

Все backend-сервисы как upstream; публичные ключи/issuer JWT согласованы с IdentityService.
