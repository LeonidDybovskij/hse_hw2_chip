# Целью данного задания является поиск поиск гистоновых модификаций с помощью анализа ChIP-Seq данных.

[Ссылка на README на русском](README.ru.md)

Все операции были выполнены с терминале Linux с использованием обычного браузерного скачивания (https://www.encodeproject.org/chip-seq-matrix/?type=Experiment&replicates.library.biosample.donor.organism.scientific_name=Homo%20sapiens&assay_title=Histone%20ChIP-seq&assay_title=Mint-ChIP-seq&status=released).

На анализ были взяты данные секвенирования фибробластов (GM23248) для гистоновой метки H3K4me1. Образцы ENCFF182AFY и ENCFF335CQJ были проанализированы на фоне контроля ENCFF569WIS. Все команды в .docx файлах (папка proof). Поскольку выдача FastQC была в пределах нормы, фильтрацию я не проводил. 
Последовательности выравнивались на 14 хромосому.

Статистика выравнивания:
|  | ENCFF182AFY | ENCFF335CQJ | ENCFF569WIS |
| --- | --- | --- | --- |
| Количество чтений | 36 622 019 | 37 314 930 | 47 833 064 |
| Выровнилось уникально | 1 453 730 (3.97%) | 1 496 129 (4.01%) | 2 039 214 (4.26%) |
| Выровнилось не уникально  | 2 408 769 (6.58%) | 2 601 874 (6.97%) | 4 203 710 (8.79%) |
| Не выровнилось | 32 759 520 (89.45%) | 33 216 927 (89.02%) | 41 590 140 (86.95%) |

Как видно, большая часть последовательностей не закартировалась. Вероятно, это связано с тем, что была взята только 14-я хромосома, оставшиеся чтения приходятся на другие части генома.
Я не отбирал уникальные риды и не преобразовывал файлы .sam в бинарный формат.
Полученные диаграммы Венна находятся в папке Intervene. В обоих случаях больше пиковых последовательностей получается при наложении полученного файла на файл .bed из базы ENCODE (ENCFF806LPY). Возможно, средняя длина наших последовательностей получилась короче за счёт не уникально закартированных ридов. 
