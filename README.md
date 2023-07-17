# Задача 9 - CV, синтетические данные

Для выполнения данной задачи я решил не изобретать велосипед и воспользоваться готовыми фреймворками и решениями. В частности, для создания синтетического датасета я использовал Unity и библиотеку, специально разработанную для этих целей - https://github.com/Unity-Technologies/com.unity.perception/.

Это отличное решение, позволяющее создавать синтетические данные любого уровня качества. Я выбрал не самое оптимальное решение (как выяснилось позже), но одно из самых быстрых. Я не создавал интерьер самостоятельно, а использовал альтернативный подход. Я воспользовался сценарием в библиотеке, который автоматически создавал фотографии моделей мебели с разных углов и генерировал разметку для них. Модели мебели я взял из бесплатных ассетов. Единственной сложностью в этом процессе было найти подходящие ассеты.

Затем передо мной возникла задача создать или обучить уже готовую модель на моем датасете. Для простоты и эксперимента я выбрал второй вариант и использовал модель PyTorch YOLOv5 - https://github.com/ultralytics/yolov5. Я дообучил эту модель на своих данных, предварительно преобразовав формат аннотаций из SOLO в COCO, а затем в YOLO TXT.
![ЧТо-то осмысленное нейросеть распознаёт, но не хватает дообучение нейросети](1_1.jpg)