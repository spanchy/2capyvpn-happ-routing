# Кастомная маршрутизация `2CapyVPN` для приложения [Happ](https://happ.su)/[INCY](https://incy.cc/)
#### Специально подготовлен для сервиса 2CapyVPN (включая логику маршрутизации)

## Установить:
### [Статическая ссылка на Raw-DEEPLINK (посмотреть на диплинк-ссылку)](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.deeplink)
### [Статическая ссылка на Raw-JSON (голый JSON для примера конфига)](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.json)

## Преимущества:
1) [Кастомный geoip](https://github.com/spanchy/2capyvpn-geoip) - добавлены все РФ диапазоны IP (даже забугорные) от VK Company (Mail.Ru, OK, VK, My.Games/VK Games) и Яндекса (Yandex, Yandex.Cloud, Yandex.Disk и т.д.). Добавлены диапазоны и IP-адреса: **Discord** (спасибо, [@fatyzzz](https://github.com/fatyzzz/)), **Threema** и общий список **Заблокированных IP в РФ** (спасибо, [@1andrevich](https://github.com/1andrevich/))
2) [Кастомный geosite](https://github.com/spanchy/2capyvpn-geosite) - куча обновлений по сервисам, урезан максимально под данную маршрутизацию. Размер файла очень мал по сравнению с дефолтным.

## Используется DNS от Yandex (в режиме DoH) - прямые запросы (DirectSites):
- Адрес сервера - https://common.dot.dns.yandex.net/dns-query (статические адреса 77.88.8.8, 77.88.8.1).

## Используется DNS от Google (в режиме DoU) - все запросы (работает "внутри" прокси):
- Статический адрес сервера 8.8.8.8. "Внутри" прокси запрос перенаправляется `dnscrypt` с кеширующим dns-сервером. Блокировка рекламных доменов.

## Что внутри настроек:
- Ваш интернет по умолчанию работает в режиме `прокси`, так как глобальная маршрутизация включена
- Все РФ ресурсы (`category-ru`), а так же специальные категории - в `DIRECT` (посмотреть конфигурацию можно [здесь](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.json))
- Все домены ОС Windows для слежки (`win-spy`) за пользователями - в `BLOCK`
- Общеизвестные серверы-трекеры протокола BitTorrent - в `BLOCK`
- Политика обработки DNS `IPOnDemand` - если домен не попал в указанные категории для него будет выполнено сопоставление по IP.
