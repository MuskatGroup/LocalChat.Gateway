# Gateway — TODO

## P0 — MVP

- [ ] ASP.NET Core + YARP проект (.NET 10)
- [ ] маршруты Identity / Chat / Realtime
- [ ] JWT Bearer (issuer/audience из Identity)
- [ ] CORS для Web и Admin
- [ ] `/health`
- [ ] `X-Correlation-Id` middleware
- [ ] Dockerfile
- [ ] конфиг кластеров через env

## P1

- [ ] маршруты Media и Notification
- [ ] rate limiting на публичные endpoint'ы заявок/логина
- [ ] раздельные CORS-политики Web vs Admin

## P2

- [ ] маршруты Call / signaling WS
- [ ] WAF-подобные лимиты на upload size (media)
- [ ] метрики (Prometheus) и трассировка

## Вне скоупа

- UI и криптография клиента.
