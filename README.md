# Как подключиться к моему прокси
[Шуруп (тг для связи)](https://t.me/shurup12312)

Статья предназначена для ограниченного круга лиц, если вы сюда попали случайно, то ВООБЩЕ НЕ ПРИБЕГАЙТЕ К ИНСТРУКЦИЯМ ИЗ СТАТЬИ, Я НИЧЕГО В ЭТОМ НЕ СМЫСЛЮ И ВСЁ ПОСТРОЕНО НА КОПИПАСТЕ ДРУГОЙ СТАТЬИ + МЕТОДЕ ТЫКА.

Оригинальная статья ChoDDyMat'а: [https://telegra.ph/Svoj-lichnyj-proksi-10-10](https://telegra.ph/Svoj-lichnyj-proksi-10-10)

Статья для телефонов: [https://telegra.ph/kak-podklyuchitsya-k-moemu-proksi-s-telefona-08-17](https://telegra.ph/kak-podklyuchitsya-k-moemu-proksi-s-telefona-08-17)

## Установка клиента

В качестве клиента Windows мы будем использовать [**Nekoray**](https://github.com/MatsuriDayo/nekoray/releases/tag/4.0.1), но вы также можете попробовать и другие клиенты. Некоторые, например, используют [Hiddify-Next](https://github.com/hiddify/hiddify-next/releases), но лично я им не пользовался и подсказать ничего не смогу.

**Весьма важно настраивать на клиентских устройствах правила, чтобы доступ к российским ресурсам не шел через прокси-сервер.**

**В нашем случае через прокси-сервер будут идти только заблокированные ресурсы, но в случае других настроек из других гайдов будьте осторожны!**

  

1) Скачиваем Nekoray ([Windows](https://github.com/MatsuriDayo/nekoray/releases/download/4.0.1/nekoray-4.0.1-2024-12-12-windows64.zip)). Если у вас уже есть старая версия программы, то крайне не советую пользоваться кнопкой "Обновление". Лучше скачать Nekoray заново и установить в новую папку.

2) Распаковываем архив в удобную папку. Программа портативная, так что установить можно на любой диск.

3) Запускаем программу (**nekoray.exe**). В появившимся окне первичной настройки выбираем ядро **sing-box.**

4) Попросите меня скинуть QR-код (или найдите последний мною скинутый QR-код) и, не закрывая окно с QR-кодом, заходим в Nekoray и нажимаем **Программа** > **Сканировать QR-код.** Если всё прошло хорошо, то в вашей программе появится новое соединение! Нажимаем по нему **ПКМ** > **Запустить.**

![](https://i.imgur.com/zzSV7LW.png)

5) Дважды кликаем на добавленное подключение. Находим кнопку "**Доп. настройки конфига**". Заходим в неё и вставляем следующий JSON-конфиг (ниже после скриншотов). Он позволит при каждом запуске подхватывать удобный обновляемый список заблокированных доменов, чтобы ходить через прокси только на ним. После вставки дважды кликаем **ОК** и возвращаемся на главное окно программы.

![](https://i.imgur.com/1T8iCgd.png)

>{  
> "experimental": {  
> "cache_file": {  
> "enabled": true  
> }  
> },  
> "route": {  
> "auto_detect_interface": true,  
> "final": "direct",  
> "rule_set": [  
> {  
> "download_detour": "direct",  
> "format": "binary",  
> "tag": "refilter_domains",  
> "type": "remote",  
> "url": "https://github.com/1andrevich/Re-filter-lists/releases/latest/download/ruleset-domain-refilter_domains.srs\"  
> },  
> {  
> "download_detour": "direct",  
> "format": "binary",  
> "tag": "refilter_ipsum",  
> "type": "remote",  
> "url": "https://github.com/1andrevich/Re-filter-lists/releases/latest/download/ruleset-ip-refilter_ipsum.srs\"  
> }  
> ]  
> }  
> }

6) Возвращаемся в главное окно программы. В интерфейсе программы заходим в **Настройки** > **Настройки маршрутов** > **Базовые маршруты**. В нижнем правом углу устанавливаем значение поля "**Outbound по-умолчанию**" на "**bypass**". Таким образом все соединения, для которых нет правил, будут идти напрямую, а не через прокси.

![](https://i.imgur.com/Grl4tNC.png)

  

7) Там же переходим в раздел "**Кастомные маршруты**" в левой нижней части окна. Заменяем содержимое поля "Редактор JSON" на следующий JSON-объект (скопировать можно под скрином). В этот конфиге вы можете добавить свои домены для обхода через прокси, в случае если их не окажется в автоматическом списке доменов, что мы добавляли до этого. Нажимаем **ОК** и возвращаемся в главное окно программы.

![](https://i.imgur.com/oVaNqyO.png)

> {"rules": [
> 
> {
> 
> "outbound": "proxy",
> 
> "rule_set": [
> 
> "refilter_domains",
> 
> "refilter_ipsum"
> 
> ]
> 
> },
> 
> {
> 
> "domain_keyword": [
> 
> "browserleaks",
> 
> ".ggpht.com",
> 
> ".googlevideo.com",
> 
> ".youtube.com",
> 
> ".ytimg.com",
> 
> ".ytimg.com",
> 
> ".googleapis.com",
> 
> "discordapp.com",
> 
> "discord.media",
> 
> "discord.com",
> 
> "discord.gg",
> 
> "discordapp.net",
> 
> "chatgpt.com",
> 
> ".openai.com",
> 
> "i.supa.codes",
> 
> "kappa.lol",
> 
> "gachi.gay",
> 
> "femboy.beauty",
> 
> "i.nuuls.com",
> 
> "7tv.app",
> 
> "api.7tv.app",
> 
> "chatis.is2511.com",
> 
> "filebin.net",
> 
> "photonengine.com",
> 
> "tiktok.com",
> 
> "capcut.com",
> 
> "docs.google.com",
> 
> "keep.google.com",
> 
> "huggingface.co",
> 
> "store.epicgames.com",
> 
> "epicgames.com",
> 
> "wikimapia.org",
> 
> ".cherry.pizza",
> 
> "thetruesize.com",
> 
> "play.cubecraft.net",
> 
> "ru.minecraft.wiki",
> 
> ".lol",
> 
> "noikcloud.xyz",
> 
> "docs.birds.land",
> 
> "prismlauncher.org",
> 
> "geoguessr.com"
> 
> ],
> 
> "outbound": "proxy"
> 
> },
> 
> {
> 
> "domain_suffix": [
> 
> "syudadirectnazvaniedomena.com"
> 
> ],
> 
> "outbound": "direct"
> 
> },
> 
> {
> 
> "outbound": "proxy",
> 
> "process_name": [
> 
> "Discord.exe",
> 
> "chatterino.exe",
> 
> "YouTubeDownloaderHD.exe",
> 
> "yt-dlp.exe",
> 
> "WhatsApp.exe",
> 
> "Telegram.exe",
> 
> "prismlauncher.exe",
> 
> "robloxplayerbeta.exe",
> 
> "RobloxCrashHandler.exe"
> 
> ]
> 
> },
> 
> {
> 
> "outbound": "direct",
> 
> "process_name": [
> 
> "syudadirectnazvanieprocessa.exe"
> 
> ]
> 
> }
> 
> ]
> 
> }

8) Если вы всё сделали верно, вы уже можете всё запустить и протестировать. Для этого нажнём на строчку с нашем подключением **правой кнопкой мыши** и нажимаем "**Запустить**". После этого обязательно ставим галочку напротив "**Режим системного прокси**".

![](https://i.imgur.com/t9k6hAK.png)

9) Пришло время протестировать наше соединение.

Из-за того, что при первом запуске подключения **Nekoray** скачивает огромный список заблокированных сайтов, **первый запуск** может занять **от 10 до 30 секунд**. Не пугаемся, и, если, Nekoray предлагает **перезапуск из-за долгого запуска** подключения - **игнорируем**.

 
Если вы всё сделали правильно, то после этих действий вы получите рабочее полноценное прокси-соединение. Кликнув по левой нижней части программы вы сможете проверить пинг установки нового соединения (не путать с обычным пингом).

![](https://i.imgur.com/V2t2xR4.png)

11) Напоследок в разделе **"Программа"** можно установить галки напротив **"Запускаться вместе с системой"** и **"Запомнить последний профиль",** чтобы ваше соединение к прокси автоматически запускалось вместе с запуском компьютера.

Теперь вы можете проверить результат работы, посетив любой из заблокированных сайтов. Если всё сделано правильно, вы это сразу поймёте! Осталось лишь починить голосовые каналы Дискорда.

#### Пускаем голосовые каналы Дискорда через прокси без TUN-режима

Делается это очень просто!

1) [Скачиваем](https://github.com/hdrover/discord-drover/releases/tag/v0.8) следующий скрипт, который заставит голосовые каналы Дискорда подключаться через прокси. Распаковываем и запускаем exe-шник.

2) В появившимся окне просто меняем порт на **2080** и нажимаем i**nstall**. Программа пожалуется, что Дискорд не выключен, так что заранее выключаем его.

![](https://i.imgur.com/az4zFxh.png)

3) Всё! Можно спокойно запускать Дискорд и проверять голосовые каналы. Скрипт-программу запускать постоянно не нужно. Она своё дело сделала.

#### Как пустить какое-нибудь приложение Windows через прокси, если оно не хочет это делать через системный прокси?

Если некая программа, например, не хочет сама видеть ваш системный прокси в Windows, то мы можем заставить её сделать это вручную с помощью TUN-режима.

1) Заходим в "**Настройки**" > "**Настройки TUN-режима**".
![](https://i.postimg.cc/6TxXvBLy/proksi1.png)

2) Ставим галку напротив "**Режим белого списка**".

3) Вписываем названия процессов нужных приложений по одному на каждую строчку в поле "**Проксировать процессы**".

![](https://i.postimg.cc/PJr6V9Xg/proksi2.png)

%% По одному процессу в строчку %%

Названия процессов можно найти в диспетчере задач. Для этого находим нужный процесс > **ПКМ** > **Свойства**. Название процесса будет указано в верхнем поле.

На примере майнкрафта:

![](https://i.postimg.cc/90MpY91F/proksi4.jpg)

![](https://i.postimg.cc/44LwN8Nx/proksi5.jpg)

4) Теперь можно установить галочку напротив и "**Режим TUN"** и "**Режим системного прокси"**.

Таким образом **Системный прокси** будет проксировать все приложения, что автоматически поддерживают прокси (браузеры, дискорд (_голосовые каналы не проксируются без TUN режима, если вы не настроили это выше_), и т.п.), а **TUN-режим** будет проксировать те процессы, которые не поддерживают прокси по стандарту, но при этом вы указали их в поле выше (в нашем примере это процесс Майнкрафта).

Примечание: **TUN-режим** работает медленнее и может вызывать большой пинг в играх.

### Дополнения к оригинальной статье от меня

Если **не присылаются картинки в дс**, надо зайти в настройки, настройки маршрутов, базовые маршруты и в колонку Домен/Прокси (снизу посередине).

![](https://i.postimg.cc/q7xxfwZW/Snimok-ekrana-2025-12-04-115647.png)

Также, если **сайты не грузятся**, или **грузятся без стилей** (оформления), то пропишите домен, к которому не может подключиться браузер, в колонку Домен/Прокси в формате:

>domain:vash.domentut.com

или

>domain:domentut.com 

так загрузятся все домены, оканчивающиеся на domentut.com

![](https://i.postimg.cc/g2RKsmyh/Snimok-ekrana-2025-12-04-115255.png)

%% не грузит сайт (пишется домен, который вам необходимо вписать) %%

![](https://i.postimg.cc/jjb4kmvy/Snimok-ekrana-2025-12-04-115326.png)

%% загрузился без оформления %%

### Список доменов для вставки в колонку Домен/Прокси:

> domain:static.spigotmc.org
> 
> domain:.steamstatic.com
> 
> domain:toxigon.com
> 
> domain:mcsrranked.com
> 
> domain:www\.mcdle.net
> 
> domain:betterttv.com
> 
> domain:thino.pkmer.net
> 
> domain:www\.youtube.com
> 
> domain:wiki.chatterino.com
> 
> domain:youtube.com
> 
> domain:proxifier.com
> 
> domain:youtu.be
> 
> domain:map.birds.land
> 
> domain:steampowered.com
> 
> domain:store.steampowered.com
> 
> domain:help.steampowered.com
> 
> domain:checkout.steampowered.com
> 
> domain:steamcommunity.com
> 
> domain:api.steampowered.com
> 
> domain:community.steamstatic.com
> 
> domain:steamuserimages-a.akamaihd.net
> 
> domain:steamstore-a.akamaihd.net
> 
> domain:steamcdn-a.akamaihd.net
> 
> domain:cdn.akamai.steamstatic.com
> 
> domain:avatars.steamstatic.com
> 
> domain:media.steampowered.com
> 
> domain:steamchat.com
> 
> domain:login.steampowered.com
> 
> domain:login.steamcommunity.com
> 
> domain:googlevideo.com
> 
> domain:ytimg.com
> 
> domain:discord-attachments-uploads-prd.storage.googleapis.com
> 
> domain:dis.gd
> 
> domain:cdn.discordapp.com
> 
> domain:discord.co
> 
> domain:discord.com
> 
> domain:discord.design
> 
> domain:discord.dev
> 
> domain:discord.gg
> 
> domain:discord.gift
> 
> domain:discord.gifts
> 
> domain:discord.media
> 
> domain:discord.new
> 
> domain:discord.store
> 
> domain:discord.tools
> 
> domain:discordapp.com
> 
> domain:discordapp.net
> 
> domain:discordmerch.com
> 
> domain:discordpartygames.com
> 
> domain:discord-activities.com
> 
> domain:discordactivities.com
> 
> domain:discordsays.com
> 
> regexp:youtube
> 
> regexp:beacons
> 
> regexp:discord
> 
> domain:chat.is
> 
> domain:chatis.is
> 
> domain:chatis.is2511.com
> 
> domain:7tv.app
> 
> domain:api.7tv.app
> 
> domain:cdn.7tv.app
> 
> domain:cdn.frankerfacez.com
> 
> domain:mc-packs.net
> 
> domain:rubukkit.org  

нажимаете ok, перезапускаете и всё работает!

(вообще, я вроде бы прочитал, и вот эта колонка - это то же самое, если бы вы написали эти домены как обычно в кастомные маршруты, ну да ладно)

### Не работает Dynmap на ШСМ (или другом локальном сервере с динмапой)

1. В Windows заходите в Параметры > Сеть и Интернет > Прокси-сервер  
2. Выключаем "Определять параметры автоматически"  
  
[![izobrazenie.png](https://i.postimg.cc/j55wgYn5/izobrazenie.png)](https://postimg.cc/QB2dCPbG)
1. Заходим в "Изменить прокси-сервер", IP-адрес и порт у вас должны быть такие же, как на скриншоте. Если нет - напишите такие же:

>127.0.0.1
>2080

Там вы можете настроить адреса, для которых НЕ будет использоваться системный прокси-сервер. Например, Radmin VPN, который создаёт локальную сеть для ШСМа, использует IP-адреса, начинающиеся на "26.". чтобы исключить их, нужно написать:  
  
>26.*

IP-адреса пишутся через точку с запятой, например:

>26.\*;192.\*;26.52.160.67

Также, вы можете настраивать подобные параметры отдельно в настройках некоторых браузеров, например, в Firefox в разделе "Параметры соединения".

[![Snimok-ekrana-2025-12-04-131511.png|700x156](https://i.postimg.cc/Twkj1wG6/Snimok-ekrana-2025-12-04-131511.png)](https://postimg.cc/dkyZSJLH)

В С Ё
