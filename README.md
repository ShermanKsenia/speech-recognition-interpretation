# Интерпретация моделей распознавания речи

В данном репозитории находятся файлы, которые были использованы для проведения исследования по теме "Интерпретация моделей распознавания речи". 

Автор: Ксения Шерман, студентка 2 курса ОП "Фундаментальная и Компьютерная лингвистика", группа БКЛ-201

Научный руководитель: Сериков Олег Алексеевич

# Файлы

- **Experiments_on_sound_properties.ipynb**

В этом файле содержится программа, с помощью которой можно провести тесты на понимание модели разделения звуков на *гласные/согласные*, *звонкие/глухие*, *твёрдые/мягкие*. Первым этапом является сбор данных: для каждого звука собираются соотвествующие ему вектора на каждом слое трансформера. Второй этап: тесты с обучением модели и выводом её результатов на верных данных, при групповом перемешивании и полном. Третий этап: создание таблицы, в которой можно посмотреть на то, какие звуки окружают соответствующий вектору.

Также в этом файле можно найти проверку на то, как модель оценивает похожие по реализации звуки. Таким образом, создаётся таблица, где каждая строка - это звук, встретившийся в услышанных моделью аудиозаписях, а столбец - все возможные звуки. На пересечениях находятся значения степени уверенности: чем больше значение, тем больше звуки считаются похожими. В результате создаётся две таблицы: для гласных и для согласных, - в каждой из которых остались те столбцы, звуки которых чаще получают высокие степени уверенности у услышанных звуков.

Все тесты сделаны на данных датасета [common_voice](https://huggingface.co/datasets/common_voice).

- **Experiments_on_phonemes.ipynb**

В этом файле содержится программа, с помощью которой можно провести тесты на понимание модели разделения аллофонов по фонемам на основании двух пар фонем: /z/ и /s/, /t/ и /d/. Первым этапом является сбор данных: для каждой из пар находятся слова, в которых можно встретить соотвествующие аллофоноы. Второй этап: обработка данных и тесты. На этом этапе данные очищаются от неподходящих под тесты. Так, для пары фонем /z/ и /s/ остаются только существительные. Также для каждого аллофона определяется, является ли этот звук показателем множетсвенного числа в существительных или прошедшего времени в глаголах. После этого данные с каждого из слоя подаются на вход модели в правильном и перемешанном виде.

Все тесты сделаны на данных датасета [TIMIT](https://catalog.ldc.upenn.edu/LDC93s1).

# Article

Работа была продолжена после защиты и выдвинута на воркшоп. В папке articles лежит версия статьи и тетрадка с данными для неё. К сожалению, статья не была принята:(
