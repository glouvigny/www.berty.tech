---
title: "Будет ли приложение скрывать IP-адреса и метаданные?"
id: 10
private: true
---

На данный момент нет механизма скрытия IP-адресов. В P2P сети узлы должны знать IP-адреса друг друга, чтобы коммуницировать.

С одной стороны, информация рассредоточена как капли в океане (в отличие от централизованных сервисов, которые сохраняют IP-адреса всех пользователей в одном месте), с другой стороны, IP-адреса пользователей, таким образом, становится публичными в сети.

Проблема, конечно, становится меньше, если пользователь подключается к сети через посредника (на мобильных устройствах это будет практически всегда), в этом случае, только случайно выбранный узел (по сути, любой узел IPFS в сети имеет включённую функцию работы в качестве посредника) будет знать реальный IP-адрес пользователя.

Проблема также не возникает, когда пользователи Berty общаются в автономном режиме, используя транспорты с прямым подключением: BLE, Apple MultipeerConnectivity, Android Nearby. Однако, в этом случае, пользователи смогут обнаруживать на короткой дистанции других пользователей Berty, которые активировали эти транспорты.

Для других случаев, в настоящее время мы работаем над добавлением в протокол использования системы смешивания сети, такой как у I2P или Tor, для сокращения утечек IP-адресов.

Что касается метаданных, то мы создали [свой протокол](https://berty.tech/docs/protocol/) , который делает сбор метаданных максимально сложным:
* Не требуется ни телефон, ни электронная почта для регистрации, идентификация пользователя основана только на криптографии открытого ключа
* Не требуя никаких видов регистрации или использования централизованной службы на любом уровне (мы можем предложить опциональную службу каталога, чтобы легко находить контакты, с одной целью упрощения использования приложения для пользователей, которые этого хотят)
* Регулярно переключать точки рандеву (вид адресов, где узлы встречаются друг с другом)
* Возможность отключить ссылку для запросов в контакты или создать новую, отозвав предыдущую
* Создавая связанный идентификатор, пользователь, присоединившийся к групповому разговору, будет делать это с использованием идентификации, специфичной для этой группы

**Мы прилагаем все усилия к тому, чтобы обеспечить конфиденциальность пользователей. Поэтому мы стремимся обеспечить максимальную анонимность наших пользователей и сделать сбор метаданных как можно более сложным.**