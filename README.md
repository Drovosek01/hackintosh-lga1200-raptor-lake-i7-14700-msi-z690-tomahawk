# Мой хакинтош (репозиторий еще в процессе добавления информации)

Язык: Русский | English (will be later)

## Краткие итоги

Итоговый результат мне понравился.

Но мне не понравилось сколько времени пришлось потратить на его достижение и выяснение всех подводных камней хакитоша.

## Комплектующие

- Материнская плата
  - [MSI MAG Z690 Tomahawk WIFI](https://www.msi.com/Motherboard/MAG-Z690-TOMAHAWK-WIFI)
  - Чипсет: Z690
  - Аудио кодек: ALC4080
  - Проводная сеть: Intel I225V 2.5Gbps LAN controller
  - Беспроводная сеть: Intel Wi-Fi 6E + Bluetooth 5.3 - AX211
- Процессор
  - [Intel Core i7-14700](https://www.intel.com/content/www/us/en/products/sku/236781/intel-core-i7-processor-14700-33m-cache-up-to-5-40-ghz/specifications.html)
- ОЗУ
  - 2 x [32 GB DDR5 6000 MHz Corsair CMK64GX5M2B6000C36](https://www.corsair.com/us/en/p/memory/cmk64gx5m2b6000c30/w_608)
- Видеокарта
  - [PowerColor AMD Radeon RX 6600](https://www.powercolor.com/product-detail23.htm)
- Накопители
  - TODO
- Кулер
  - [ID-Cooling SE 224 XT Black](http://en.idcooling.com/product/detail?id=210&name=SE-224-XT%20BLACK)
- Блок питания
  - TODO

## Что протестировано

- macOS Sequoia 15.7.3
- Windows 11 Pro 25H2

У меня нет iPhone, но есть Macbook Air на M1. Я не заядлый "яблочный пользователь" и, вероятно, не знаю каких-то фишек экосистемы Apple. Что знал и что могло не работать из-за особенностей настройки хакинтоша - я протестировал.

Также здесь есть интересный чек лист, если будете проверять работу своего хакинтош - https://chriswayg.gitbook.io/opencore-visual-beginners-guide/step-by-step/hackintosh-checklist

### Что работает в macOS

- сон
- TODO

### Что не работает в macOS

- AirDrop
- TODO

### А также...

- в macOS 14 Sonoma и более старых версий macOS - Wifi с помощью [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm) будет работать без [OCLP](https://github.com/dortania/OpenCore-Legacy-Patcher/), но время идет и скоро эта версия macOS не будет считаться современной, поэтому я решил поставить macOS 15, т.к. она новее и есть уже стабильные версии
- отсутствие AirDrop не проблема, вместо него можно использовать [LocalSend](https://localsend.org/) или [Blip](https://blip.net/) или аналоги
- у меня нет и не было iOS устройств - работа iMassage и FaceTime для меня не имеет никакого значения, я ими не пользуюсь
