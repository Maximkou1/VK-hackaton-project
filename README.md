# VK-hackaton-project

## Предсказание топиков и тэгов новостей
Для обучения и дальнейшего улучшения работы модели использовалось два датасета с разметкой новостей по классам: lenta.ru (https://www.kaggle.com/datasets/yutkin/corpus-of-russian-news-articles-from-lenta) и mail.ru (был предоставлен организаторами хакатона).

Два датасета были слиты нами в один. После этого был произведен препроцессинг: некоторые топики в датасете были объединены, некоторые удалены, некоторые переименованы более подходящим образом; тексты новостей были приведены к нижнему регистру, очищены от стоп-слов и лишних знаков препинания. 

После препроцессинга данные были аугментированы, а затем на них дообучилась RuRoberta-Large. Её работа была оценена различными метриками. 

Затем каждый топик был кластеризован на пять подкластеров, и в каждом подкластере были выделены ключевые слова. Ключевые слова (тэги) были отсмотрены вручную, очищены и дополнены. Тэги предсказываются по косинусной близости самого тэга и текста новости.
