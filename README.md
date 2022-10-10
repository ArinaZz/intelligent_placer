# Постановка задачи

Имеется фотография подмножества предметов фиксированного множества и многоугольник. Необходимо определить, можно ли расположить все предметы в многоугольнике.

## Требования к фотографии предметов

0. На изображении обязан присутствовать многоугольник на белом листе A4. Все предметы должны находится внутри области листа. 
1. Предметы не должны пересекаться
2. Один объект может присутствовать на фото один раз
3. Предметы должны иметь четко выраженные границы. Предметы не должны накладываться друг на друга, между нимы должен сохраняться отступ (отспут в данном случае - белый фон листа, минимум 1 см)
4. Свет должен падать на поверхность перпендикулярно, чтобы минимизировать количество теней на изображении (возможны отклонения соразмерные с отклонением снимка)
5. Камера направлена перпендикулярно к фотографируемой поверхности
6. Все предметы должны быть полностью видны на фото 
7. Предметы должны располагаться на белой поверхности листа
8. Ожидаются, что все предметы повернуты всегда одной стороной к камере. 
9. На фото должны быть видны все предметы, а также края белого листа бумаги, на котором они располагаются
10. Расстояние от камеры до поверхности должна быть от 20 до 30 сантиметров 

## Требования к многоугольнику

1. Многоугольник должен быть замкнут
2. Многоугольник должен быть выпуклым
3. Количество вершин многоугольника от 3 до 10

## Способ задания многоугольника

1. Многоугольник задается списком координат вершин
2. Соседние вершины многоугольника должны идти подряд в списке вершин (первая идет за последней, то есть обход по часовой стрелке)
3. Координаты вершин многоугольника соовтветствуют сантиметрам на естественной плоскости

# Сбор данных

## Расположение

- Фотографии с подмножествами предметов находятся в папке [items](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/items)
- Файлы с заданными вершинами многоугольников в файле [polygon_samples](https://github.com/ArinaZz/intelligent_placer/blob/develop/data/polygon_samples.txt) 

## Примеры
- Фотографии с подмножествами предметов, которые помещаются в многоугольник [polygon_samples_true](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/polygon_samples_true.txt), находятся в папке [true_images](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/true_images)
- Фотографии с подмножествами предметов, которые не помещаются в многоугольник [polygon_samples_false](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/polygon_samples_false.txt), находятся в папке [false_images](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/false_images)
- Фотографии с подмножествами предметов, из которых в многоугольник [polygon_samples_one_true](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/polygon_samples_one_true.txt) помещается только один предмет, находятся в папке [one_true_images](https://github.com/ArinaZz/intelligent_placer/tree/develop/data/one_true_images) 

## Данные 

### Ввод:

На вход подается фотография предметов и набор многоульников

### Выовод:

- True, если возможно поместить предметы в заданный многоугольник так, чтобы они не пересекались *см. примеры true_images* 
- False, если невозможно поместить предметы в заданный многоугольник так, чтобы они не пересекались *см. примеры false_images и one_true_images*

## Оценка качества работы

Оценкой качества работы будет является незанятая площадь в многоугольнике. Отношения незанятой площади многоугольника к общей площади.