# WPS Office Ubuntu: Русификация и установка необходимых шрифтов

## Начальные действия

Скопируем (или [скачаем](https://github.com/alexsoin/wps-office-fix)) репозиторий с русификатором и шрифтами:

```bash
git clone https://github.com/alexsoin/wps-office-fix
```

Перейдем в скопированный репозиторий

```bash
cd wps-office-fix
```

## Русификация WPS Office после установки в Ubuntu 20.04

Убеждаемся что, находимся внутри папки скопированного репозитория из пункта ["Начальные действия"](#%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F).

Копируем папку `ru_RU` в директорию со списками языковых пакетов WPS Office:

```bash
cp -r ru_RU/ /opt/kingsoft/wps-office/office6/mui/ru_RU/
```

Переименовываем языковые пакеты английской версии:

```bash
sudo mv /opt/kingsoft/wps-office/office6/dicts/spellcheck/en_US/ /opt/kingsoft/wps-office/office6/dicts/spellcheck/en_US-old/
```
```bash
sudo mv /opt/kingsoft/wps-office/office6/mui/en_US/ /opt/kingsoft/wps-office/office6/mui/en_US-old/
```

Перезапускаем офис и он должен подхватить автоматически русский язык, если этого не произошло, то в левом верхнем углу справа от кнопке `Menu` нажимаем на стрелку вниз, выбираем `tools`, затем `set Language` и выбираем русский язык (после этого также WPS Office надо перезапустить).

> При обновлении WPS офиса повторите процедуру переименования языковых пакетов английской версии.

## Установка недостающих шрифтов в WPS Office в Ubuntu 20.04

Если при запуске WPS Office появляется ошибка, что нехватает шрифтов, то этот пункт как раз вам поможет.

Убеждаемся что, находимся внутри папки скопированного репозитория из пункта ["Начальные действия"](#%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F).

Запускаем команду

```bash
sudo bash fonts/install.sh
```

После окончания установки ошибки больше не будет =)


## P.S.

Уже какой раз когда устанавливаю заново ubuntu, сталкиваюсь с тем, что много времени трачу на поиск устранения этих ошибок, поэтому решил собрать всё в одном месте, но и не забываю о том, где эти решения я нашел))) Про русификатор я узнал из [этой статьи](https://www.nibbl.ru/linux/linuxday3-besplatnyj-analog-office-na-linux-i-windows.html#ustanovka-rusifikatora-v-wps-office), а проблему со шрифтами мне помог решить вот [этот репозиторий](https://github.com/IamDH4/ttf-wps-fonts).

Если вам данная статья, как и мне, помогла, то прошу поставить звезду [в этом репозитории](https://github.com/alexsoin/wps-office-fix) или описать, что не получилось в issues.
