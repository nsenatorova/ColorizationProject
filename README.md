# Colorization

### Реализация: 
Цветные изображения переводятся из пространства RGB в Lab, где L и есть черно-белое изображение. На вход нейросети подается канал L, и на его основе генерируются остальные два канала -  a и b. Сверточная нейронная сеть написана на языке Python с использованием библиотеки Keras. Сеть состоит из 15 слоёв: 12 слоев Conv2D и 3 слоя UpSampling2D. Во 11 слоях Conv2D используется полулинейная функция активации Relu, в последнем - гиперболический тангенс tanh (т.к. в каналах a и b значения изменяются от -128 до 128 и tanh нужен, чтобы получить зеленые и синие оттенки). В качестве функции потерь выбрана среднеквадратическая ошибка MSE.

### Датасет: 
Цветные изображения размера 256х256; все изображения взяты с Computational Visual Cognition Laboratory (http://cvcl.mit.edu/database.htm). Всего в датасете 1450 изображений (в обучающем множестве 1305, в тестовом 145).
