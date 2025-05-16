# Кастомный роутинг `2CapyVPN` для приложения [Happ](https://happ.su)

#### Быстрый и универсальный роутинг, работает только для тех ресурсов, что указаны в правилах.

## Установить:
### [Статическая ссылка на Raw-DEEPLINK (посмотреть на диплинк-ссылку)](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.deeplink)
### [Статическая ссылка на Raw-JSON (голый JSON для примера конфига)](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.json)

## Преимущества (спасибо [@hydraponique](https://github.com/hydraponique/)):
1) [Кастомный geoip](https://github.com/hydraponique/roscomvpn-geoip) - добавлены все "пророссийские" диапазоны IP (даже забугорные) от VK Company (Mail.Ru, OK, VK, My.Games/VK Games) и Яндекса (Yandex, Yandex.Cloud, Yandex.Disk итд). Добавлены диапазоны и IP-адреса: **Discord** (в "proxy", спасибо, [@fatyzzz](https://github.com/fatyzzz/)), **Threema** (в "proxy")
2) [Кастомный geosite](https://github.com/hydraponique/roscomvpn-geosite) - куча обновлений по сервисам, урезан максимально под этот роутинг, ни на что более не способен, т.е. чего нет в конфиге роутинга - значит выпилено (весят очень мало по сравнению с дефолтными, тем самым разгружают ядро xray от фильтрации мусора)

## Используется DNS от AdGuard:
- [AdGuard DNS](https://adguard-dns.io/ru/public-dns.html) 94.140.14.14/94.140.15.15 с блоком рекламы (разгружаем ядро xray от лишних мегабайтов оперативной памяти, iPhone скажет спасибо). Утечек ДНС нет.

## Что внутри настроек:
- Ваш интернет по-умолчанию работает в режиме `как-есть`, так как глобальный роутинг выключен
- Все основные ресурсы, заблокированные РКН - в `PROXY` (посмотреть конфигурацию можно [здесь](https://raw.githubusercontent.com/spanchy/2capyvpn-happ-routing/refs/heads/main/raw.json))
- Все домены ОС Windows для слежки за пользователями - в `BLOCK`
- Общеизвестные серверы-трекеры протокола BitTorrent - в `BLOCK`
