# Бенчмарки

- [Бенчмарки](#бенчмарки)
  - [Предисловие](#предисловие)
  - [Заметки](#заметки)
  - [В Windows](#в-windows)
    - [Windows 11 25H2](#windows-11-25h2)
      - [GeekBench 6.5.0](#geekbench-650)
      - [CPU-Z v2.17.0](#cpu-z-v2170)
      - [Cinebench 2024](#cinebench-2024)
      - [Cinebench R23](#cinebench-r23)
      - [AIDA64 (Memory test)](#aida64-memory-test)
      - [CrystalDiskMark 9.0.1](#crystaldiskmark-901)
      - [Blackmagic RAW Speed Test](#blackmagic-raw-speed-test)
      - [Passmark PerformanceTest 11.1](#passmark-performancetest-111)
      - [NovaBench](#novabench)
  - [В macOS](#в-macos)
    - [macOS 15.7.3 Sequoia](#macos-1573-sequoia)
  - [Локальные выводы](#локальные-выводы)


## Предисловие

Изначально я запускал бенчмарки в Windows 11 25H2 и при нагрузке на процессор я наблюдал, что его частота повышается до ~5.4 ГГц буквально на 2-3 секунды, а потом падает до ~2.8-3 ГГц и держится на этой отметке все оставшееся время. И это мне показалось странным, потому что процессор 10-летней давности Intel Xeon E5-2666 v3 без разблокировки турбобуста держал примерно такую же частоту при длительной нагрузке.

Поскольку у меня все предыдущие материнские платы были с "синим биосом" и без функций оверклокинга, я не знал о многих новшествах современных материнских плат с GUI. Предыдущая материнская плата в моем компьютере была на платформе x99 с китайским брендом Jginyue x99 Titanium D3.

Я погуглил такое поведение процессора под нагрузкой и наткнулся на пост, в котором человек описывает схожую с моей ситуацию - https://www.reddit.com/r/overclocking/comments/1g6xts9/i7_14700_wont_stay_at_max_mhz/

Изначально в BIOS/UEFI параметр `Overclocking -> Advanced CPU Configuration -> Long Duration Power Limit` был выставлен на "Авто" (65 ватт) и при такой настройке при длительных нагрузках частота процессора была около ~3 ГГц (хотя его максимальная частота в турбобусте - 5,4 ГГц). Получается при длительных нагрузках поддерживалась такая частота процессора, чтобы не превышать TDP в 65 ватт.

Поскольку в официальных характеристиках процессора (например на [techpowerup](https://www.techpowerup.com/cpu-specs/core-i7-14700.c3442)) заявлен максимальный TDP в 219 ватт, **я в параметре "Long Duration Power Limit" выставил значение 180 ватт**, чтобы при длительных нагрузках иметь удовлетворительную производительность, а не уровень 10-летнего процессора Intel Xeon. И с такой настройкой я работаю за компьютером и с такой настройкой проводил итоговое тестирование в бенчмарках. Никакого разгона или андервольтинга я на текущий момент не проводил.

Для оперативной памяти DDR5 я выставил максимальный XMP-профиль 6000 MHz.

Настройки видеокарты я никак не менял и биос никак не перепрошивал.


## Заметки

Во время тестирования настоятельно рекомендую выключить все сторонние программы, особенно браузеры. Я давно где-то видел примеры того, чтобы во время работы Google Chrome для его работы резервируются ресурсы графического ускорения и если вы рендерите видео ролик, например в Davinci - с просто запущенным Google Chrome в фоне, видео будет рендерится дольше.

С бенчмарками, думаю, аналогичная ситуация, но я не проверял влияние запущенных браузеров на результаты бенчмарков. Просто завершил их работу до начала тестирования.

Разумеется между выполнениями тестирования работы в однопоточном и мультипоточном режимах нужно делать паузу ~5 минут - дать процессору время остыть.


## В Windows

### Windows 11 25H2

#### GeekBench 6.5.0

Тестирование GeekBench проводилось как с запуском Windows без сторонних загрузчиков, чтобы исключить их влияние на взаимодействие с комплектующими компьютера, так и с OpenCore.

- CPU: https://browser.geekbench.com/v6/cpu/15662858, https://browser.geekbench.com/v6/cpu/15664747
- iGPU Intel UHD 770 (OpenCL): https://browser.geekbench.com/v6/compute/5434090, https://browser.geekbench.com/v6/compute/5434836
- iGPU Intel UHD 770 (Vulkan): https://browser.geekbench.com/v6/compute/5434080, https://browser.geekbench.com/v6/compute/5434846
- GPU AMD RX 6600 (OpenCL): https://browser.geekbench.com/v6/compute/5434058, https://browser.geekbench.com/v6/compute/5487150
- GPU AMD RX 6600 (Vulkan): https://browser.geekbench.com/v6/compute/5434065, https://browser.geekbench.com/v6/compute/5487163

#### CPU-Z v2.17.0

- https://valid.x86.fr/2wc61c
- https://valid.x86.fr/qr9vd5

#### Cinebench 2024

![cinebench 2024 results](https://github.com/user-attachments/assets/ac3e8ea6-f976-40c1-b890-378fd6b01bae)

#### Cinebench R23

![cinebench R23 multi core results](https://github.com/user-attachments/assets/5e845fa0-5798-4e8a-b5a3-baa7923731de)
![cinebench R23 single core results](https://github.com/user-attachments/assets/07f43742-f1ae-41d6-9ffc-cb35f84811be)
![cinebench R23 MP ratio results](https://github.com/user-attachments/assets/39b64771-ffe2-4021-8ceb-560ff0a50081)

#### AIDA64 (Memory test)

![aida64 screenshot](https://github.com/user-attachments/assets/687a712d-51a6-4c9d-8544-b72ccf5133a3)

#### CrystalDiskMark 9.0.1

For WD Black SN850
![crystal disk mark 9 results](https://github.com/user-attachments/assets/65eb3605-8ac3-4635-a4b0-74065acf63b3)

#### Blackmagic RAW Speed Test

![Blackmagic RAW Speed Test results](https://github.com/user-attachments/assets/7941a299-1b4f-4dc9-9092-1f2ef8de4245)

#### Passmark PerformanceTest 11.1

https://www.passmark.com/baselines/V11/display.php?id=317161134007

#### NovaBench

https://novabench.com/result/8ad2358a-8891-453e-9cb1-b05974c58e4e



## В macOS

### macOS 15.7.3 Sequoia



## Локальные выводы

Изменение параметра "Long Duration Power Limit" в BIOS/UEFI на моем компьютере с 65 ватт на 180 ватт стоит учитывать и помнить, при сравнении моих результатов с результатами из интернета.

Например на сайте [notebookcheck.net на странице с i7-14700](https://www.notebookcheck.net/Intel-Core-i7-14700-Processor-Benchmarks-and-Specs.930220.0.html) результаты Geekbench 6.5 - Geekbench 6.5 Multi-Core - 14072 points, а мои результаты ~20000 points. То есть их параметр такой же, как при "Long Duration Power Limit" установленном на 65 ватт.

Получается с установкой параметра "Long Duration Power Limit" на 180 ватт, результаты работы моего процессора в бенчмарках примерно такие же, как у K-версии (с разблокированным множителем).
