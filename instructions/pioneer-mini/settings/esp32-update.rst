Обновление прошивки ESP-32
==========================

6 ноября вышла новая прошивка ESP-32. Для корректной работы квадрокоптера, вам обязательно нужно обновить прошивку данного контроллера.

Контроллер ESP-32 отвечает за передачу видеопотока и передачу команд управления с телефона на квадрокоптер.

**Новая версия прошивки ESP-32 и обновленный Geoscan Jump, качественно улучшают:**

* Скорость передачи видеопотока;

* Увеличено количество кадров в секунду;

* Скорость передачи команд управления;

* Стабильность WiFi соединения;

* Совместимость с большим количеством телефонов.

**Новая версия параметров автопилота версии 0007:**

* Улучшена стабильность взлета и посадки;

* Квадрокоптер быстрее отключается при переворотах и столкновениях;

* Управление в режимах полета Althold и Stabilize стало более отзывчивым;

* Убран баг с автозапуском LUA скрипта.

.. attention:: Вышел патч с прошивкой ESP32 v.0.2.7, которая исправляет баг с невозможностью подключения коптера по WiFi. Старая версия прошивки перенесена в раздел Загрузки.



Процесс обновления контроллера ESP-32
-------------------------------------

Перед началом убедитесь:

Что версия автопилота: 1.6.7257. Проверить можно в Pioneer Station. Для этого подключите квадрокоптер по USB, в правом нижнем углу программы в строчке "Версия АП" должно быть 1.6.7257. При необходимости обновите,
:doc:`firmware_upgrade`



Для обновления прошивки ESP-32, вам понадобиться специальная утилита. Данная инструкция объяснит процесс работы с ней.

1. Подключите Пионер Мини к компьютеру через Micro-USB разъем.

.. figure:: media/esp32/copter-usb.jpg
   :align: center
   :scale: 50%

2. Нажмите кнопку включения,  левый светодиод должен начать моргать.


3. Скачайте архив ESPTOOL, в нем содержится утилита для прошивки контроллера ESP-32

:download:`ESPTOOL с прошивкой ESP32 0.2.7 <media/esp32/ESPTOOL0.2.7.zip>`

.. attention:: Рекомендуется запускать на ОС Windows 10.

4. Разархивируйте ZIP архив, нажав на него правой кнопкой мыши и выбрав "Извлечь все...".

.. figure:: media/esp32/esp-zip.jpg
   :align: center

5. Откройте разархивированную папку и запустите из нее файл ESPTOOL.exe

.. attention:: Перед этим вам необходимо закрыть программу Pioneer Station, если она у вас открыта.

.. figure:: media/esp32/esptool-start.PNG
   :align: center

.. attention:: в файле par.properties содержатся параметры автопилота новой версии 0007. Они загрузятся автоматически, в данной версии программы.


6. Дождитесь обновления прошивки ESP-32, она может занимать до 5 минут.

.. figure:: media/esp32/esptool-work1.jpg
   :align: center



7. После появления сообщения "Hard resetting via RTS pin..." закройте утилиту нажатием на "крестик".

.. attention:: Приложение не должно закрываться автоматически, дождитесь надписи указанной выше.

.. figure:: media/esp32/esptool-work2.png
   :align: center

.. figure:: media/esp32/esptool-work3.png
   :align: center

8. Перезапустите Пионер Мини нажатием на кнопку включения.

.. figure:: media/esp32/copter-restart.jpg
   :align: center
   :scale: 50%

9. Квадрокоптер готов к работе.



.. attention:: Если процесс обновления не удаётся завершить из-за ошибки **>>>OFFSET_ERROR<<<** вам необходимо произвести перекалибровку акселерометра. Чтобы это сделать, перейдите на страницу :doc:`accel-mini`.


Проверка после обновления
--------------------------

Перед началом убедитесь:


1. Что параметры загружены верно.

Проверить загрузили ли вы конкретные параметры 0007 или нет, можно через номер борта, для этого отключите коптер по USB нажав кнопку "подключение", затем заново подключите, если у вас "номер борта" изменился на 501, как на снимке экрана ниже, значит все сделано верно.

.. figure:: media/esp32/properties-test.PNG
   :align: center
   :scale: 50%

При необходимости можно загрузить по ссылке ниже или на странице :doc:`autopilot_parameters`

:download:`файл параметров АП версии 0007 <media/esp32/Pioneer-mini-1.0.0007.properties>`

2. Что вы обновили прошивку ESP-32, как описано выше. Для проверки откройте Jump, в расширенных настройках включите отображение отладочной информации. В строке напротив "cur" должна быть надпись ["0.2.7"] или выше.

.. figure:: media/esp32/cur-version.png
   :align: center

Также проверить, прошло ли обновление успешно через имя WiFi сети. Если сеть называется "Pioneer_Mini" и после слова "Mini" отсуствует набор случайных цифр и букв, значит обновление не прошло.

После успешного обновления имя сети должно измениться например на "PioneerMini5afg415bb".


3. У вас установлено приложение Geoscan Jump последний версии. Номер версии можно проверить в самом приложении в вкладке "Расширенные настройки". На момент 6 ноября, это была версия "0.9 13" или выше.

.. figure:: media/esp32/jump-version.jpg
   :align: center
   :scale: 70%

.. attention:: В новой версии Jump кнопку START и STOP необходимо удерживать до тех пор, пока моторы не запустятся/остановятся.



Форма обратной связи об обновлении
----------------------------------

Ознакомьтесь с данной формой, в ней есть рекомендации по первым полетам и сбор обратной связи.

`Форма обратной связи обновления 0.9.11 "Поликарпов" <https://forms.gle/gM1mquuamwUDrqLV6>`__



Команда раннего тестирования
----------------------------

Хотите получить доступ к новым возможностям раньше остальных?

Записывайтесь в нашу команду тестирования.

Если вы хотите принять участие, вам необходимо заполнить данную форму. Через некоторое время, вам в ответном письме вышлют инструкцию для дальнейших действий.

Только для пользователей Пионер Мини.

`Заявка на тестирование <https://docs.google.com/forms/d/e/1FAIpQLSfSF_IpO0oPtfjqqSWDELDtBjv651xtfSsP6x43kTiuqeMtaA/viewform?usp=sf_link>`__











