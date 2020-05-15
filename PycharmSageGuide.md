Как использовать sage на ubuntu через pycharm ide:

1. Скачать бинари sage для соответствующей системы (в моем случае это ubuntu):
архив с именем sage-9.0-Ubuntu_18.04-x86_64.tar.bz2 с https://www.sagemath.org/
2. Распаковать его (куда душе угодно), скажем в ~/sage/.
3. Запустить из этого каталога файл sage, чтобы в первый раз запустить сам sage (возможно, 
этот шаг можно пропустить, но мне он потребовался по некоторой причине(?)).
4. Создать новый interpreter в pycharm: в gui зайти files->settings (= cntrl+alt+s), затем перейти 
во вкладку Project:<имя вашего проекта>, а там во вкладку Project Interpreter. 
Затем добавить interpreter:
- вкладка new environment
- в качестве location можете указать любую папку (лучше все environment'ы хранить в отдельной папке),
например ~/myenv/sageenv/
- в качестве Base interpreter указать ~/sage/local/bin/python3 (напомним, что в папку ~/sage 
распакован сам архив)
- обязательно поставить галку Inherit global site-packages
- галка Make available to all projects опциональна.
5. UPDATE: в папку ~/myenv/sageenv/bin/ (у нас в ~/myenv/sageenv/ лежит environment) скопировать файл sage-maxima.lisp из каталога ~/sage/local/bin:

cp ~/sage/local/bin/sage-maxima.lisp ~/myenv/sageenv/bin/sage-maxima.lisp

Все. Далее 
from sage.all import *
и пошла жара.
