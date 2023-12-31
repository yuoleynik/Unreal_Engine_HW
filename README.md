# Unreal Engine 5 Homework

Олейник Юлия

### Подробное текстовое описание алгоритмов генерации комнат и их содержимого

- Сначала генерируется пол при помощи 2 for loop. Они создают как бы "матрицу" из полей 400х400.
- После пола генерируется наполнение комнат. Предметы (лечение, ловушки) генерируются таким образом, что они не могут перекрыть проходы к дверям из-за чего не возникает проблем с прохождением уровней.
- После предметов генерируются стены, из которые случайным образом выбираются 2 двери (кроме последнего уровня), где одна из них блюпринт с дверью, которая ведет в комнату с хилками, а другая блюпринт, которая ведет в комнату с тем же уровнем сложности, что и предыдущая.
- Дверь, которая ведёт в уровень с хилками, отмечена сердечком, а также очень ярким розово-красным цветом, в то время, как другая дверь отмеченная окружностью (ассоция с пустотой), ведёт в комнату с той же сложностью (цвет сине-голубой).
- Капуста генерируется, если выполнено условие из GameMode - IsLastRoom, что означает, последняя ли комната или нет. И генерируется на самых дальних координатах от игрока.
- В проекте расширен GameMode BP_ThirdPersonGameMode, в котором отмечены необходимые variables.
- Реализовано меню старта, рестарта в случае смерти, а также меню победителя, где также предлагается рестарт и выход (выход есть у всех меню). Они реализованы при помощи Level, Widget и GameMode.

### Описание принципа изменения уровня сложности в игре

Уровни усложняются за счёт увеличения комнаты, из-за чего генерируется больше ловушек.

### Ссылки на готовые проекты

- https://www.youtube.com/watch?v=XgIDH42RHWQ - Процедурная генерация уровней
Понравилась реализация через "матрицу" пола, благодаря которой было проще спавнить предметы в комнате, так как есть привязка к определенному "полу" размером 400х400. Однако пришлось очень многое изменить, что можно увидеть в проекте.
- https://www.youtube.com/watch?v=WznFdYWM2c8 - Или как избежать бесконечной петли
Долго мучилась с TimeLine, потому что в моей голове за реализацию движения объектов отвечает именно он, но при попытке что-либо реализовать зацикленное, он выкидывал с ошибкой. Это видео помогло мне зациклить движение ловушки. В основном видео раскрывает новую мне механику, поэтому особо много я не взяла, наверное.
- https://www.youtube.com/watch?v=kjrfYuhH2JA&t=1157s - Виджет здоровья и само здоровье
Увидела реализацию и очень понравилось. Виджет простой, реализация тоже простая и удобная при реализации взаимодействия. Однако я искала именно виджет, а не сам компонент здоровья. Такие дела
