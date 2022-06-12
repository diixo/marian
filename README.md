Компания Mozilla опубликовала собственную систему машинного перевода [...](https://opennet.ru/57292-translate)
=====
02.06.2022 21:16

Компания Mozilla выпустила инструментарий для самодостаточного машинного перевода с одного языка на другой, работающий на локальной системе пользователя без обращения к внешним облачным сервисам перевода. Проект развивается в рамках инициативы Bergamot совместно с исследователями нескольких университетов Великобритании, Эстонии и Чехии при финансовой поддержке Евросоюза. Наработки распространяются под лицензией MPL 2.0.

Проект включает в себя движок [bergamot-translator](https://github.com/browsermt/bergamot-translator), [инструменты](https://github.com/mozilla/firefox-translations-training) для самостоятельной тренировки системы машинного обучения и готовые модели для 14 языков, включая экспериментальные модели для перевода с английского на [русский](https://github.com/mozilla/firefox-translations-models/tree/main/models/dev/enru) язык и [наоборот](https://github.com/mozilla/firefox-translations-models/tree/main/models/dev/ruen). Уровень перевода можно оценить на [online-демонстрации](https://mozilla.github.io/translate).
Движок написан на языке C++ и представляет собой обвязку над фреймворком машинного перевода [Marian](https://marian-nmt.github.io), в котором применяется рекуррентная нейронная сеть (RNN) и языковые модели на основе трансформеров. Для ускорения обучения и перевода может использоваться GPU. Фреймворк Marian также используется для обеспечения работы сервиса перевода Microsoft Translator и развивается в основном инженерами из Microsoft совместно с исследователями из Эдинбургского и Познанского университетов.

Для пользователей Firefox подготовлено дополнение для перевода web-страниц, осуществляющее перевод на стороне браузера без обращения к облачным сервисам (при этом дополнение отправляет телеметрию о действиях пользователя, языке перевода и числе переведённых слов). Ранее дополнение можно было установить только в бета-выпусках и ночных сборках, но теперь оно доступно и для релизов Firefox. В браузерном дополнении движок, изначально написанный на С++, компилируется в промежуточное бинарное представление WebAssembly при помощи компилятора Emscripten. Из новых возможностей дополнения отмечается возможность перевода во время заполнения web-форм (пользователь вводит текст на родном языке и он на лету переводится на язык текущего сайта) и оценка качества перевода с автоматической пометкой сомнительных переводов для информирования пользователя о потенциальных ошибках.

Mozilla развивает собственную систему машинного перевода [...](https://opennet.ru/51718-mozilla)
=====
21.10.2019 07:14

Компания Mozilla в рамках проекта [Bergamot](https://browser.mt) приступила к созданию системы машинного перевода, работающей на стороне браузера. Проект позволит интегрировать в Firefox самодостаточный движок перевода страниц, не обращающийся к внешним облачным сервисам и обрабатывающий данные исключительно на системе пользователя. Главной целью разработки является обеспечение конфиденциальности и защита данных пользователя от возможных утечек при переводе содержимого открываемых в браузере страниц.

Разработка Bergamot ведётся в берлинском офисе Mozilla при участии исследователей из [нескольких](https://browser.mt/partners) университетов Великобритании, Эстонии и Чехии. Разработку финансирует Евросоюз в рамках гранта, полученного по программе [Horizon 2020](https://ec.europa.eu/programmes/horizon2020/en). Размер гранта составляет три миллиона евро. Проект рассчитан на три года. В Mozilla открыта вакансия специалиста по системам машинного обучения для участия в разработке движка для перевода с одного языка на другой.

Из смежных разработок, имеющих отношение к проекту Bergamot, [упомянуты](https://browser.mt/software):

- Развиваемый в Эдинбургском университете фреймворк машинного перевода [Marian](https://marian-nmt.github.io), построенный на базе рекуррентной нейронной сети. [Фреймворк](https://github.com/marian-nmt/marian) написан на языке C++, может задействовать GPU для ускорения обучения и перевода, и поставляется под лицензией MIT.
- Созданный в Пражском университете инструментарий [Neural Monkey](https://github.com/ufal/neuralmonkey) для обработки информации на естественном языке с использованием методов последовательного машинного обучения. Проект применяет фреймворк TensorFlow и может использоваться для быстрого создания прототипов систем машинного перевода и классификации информации на естественном языке. Код доступен под лицензией BSD.
- Подготовленный в Шеффилдском университете проект [QuEst++](https://github.com/ghpaetzold/questplusplus), применяемый для оценки и прогнозирования качества систем машинного перевода.
- Развиваемые в Mozilla синтезатор речи ([TTS](https://github.com/mozilla/TTS)) и движок распознавания речи ([Deep Speech](https://github.com/mozilla/DeepSpeech))
- Финансируемый Евросоюзом проект [ParaCrawl](https://paracrawl.eu), накапливающий базу синхронных переводов различных фраз на разных языках, которую можно использовать для тренировки систем машинного обучения. Основой проекта является бот [bitextor](https://github.com/bitextor), который индексирует многоязычные web-сайты и автоматически находит одинаковые тексты, представленные на нескольких языках. База примеров параллельных переводов формируется для 24 языков, в том числе для русского ([БД](https://paracrawl.eu/releases.html) для русского языка занимает 637MB в сжатом виде и включает более 12 млн примеров перевода).

Разработка Bergamot началась в январе этого года, но наработки проекта пока недоступны для публичного тестирования. Тем не менее, несколько дней назад разработчики опубликовали видео с демонстрацией начального прототипа.



Напомним, что в Firefox уже имеется встроенный механизм для перевода страниц, но он завязан на использовании внешних облачных сервисов (поддерживаются Google, Yandex и Bing) и не активирован по умолчанию (для включения в about:config следует изменить настройки "browser.translation"). Механизм перевода в том числе поддерживает автоматическое определение языка при открытии страницы на неизвестном языке и выводит специальный индикатор с предложением осуществить перевод страницы. Развиваемый в рамках проекта Bergamot прототип системы перевода использует этот же интерфейс для взаимодействия с пользователем, но вместо обращения к внешним сервисам запускается встроенный обработчик.

Marian
======


[![Build Status CUDA 10](https://img.shields.io/jenkins/s/http/vali.inf.ed.ac.uk/jenkins/view/marian/job/marian-dev-cuda-10.2.svg?label=CUDA%2010.2)](http://vali.inf.ed.ac.uk/jenkins/job/marian-dev-cuda-10.2/)
[![Build Status CUDA 11](https://img.shields.io/jenkins/s/http/vali.inf.ed.ac.uk/jenkins/view/marian/job/marian-dev-cuda-11.4.svg?label=CUDA%2011.4)](http://vali.inf.ed.ac.uk/jenkins/job/marian-dev-cuda-11.4/)
[![Build Status CPU](https://img.shields.io/jenkins/s/http/vali.inf.ed.ac.uk/jenkins/view/marian/job/marian-dev-cpu.svg?label=CPU)](http://vali.inf.ed.ac.uk/jenkins/job/marian-dev-cpu/)
[![Tests Status](https://img.shields.io/jenkins/s/http/vali.inf.ed.ac.uk/jenkins/view/marian/job/marian-regression-tests.svg?label=tests)](http://vali.inf.ed.ac.uk/jenkins/job/marian-regression-tests/)
[![Latest release](https://img.shields.io/github/release/marian-nmt/marian.svg?label=release)](https://github.com/marian-nmt/marian/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE.md)
[![Twitter](https://img.shields.io/twitter/follow/marian_nmt.svg?style=social)](https://twitter.com/intent/follow?screen_name=marian_nmt)

*Marian* is an efficient Neural Machine Translation framework written in pure
C++ with minimal dependencies.

Named in honour of Marian Rejewski, a Polish mathematician and cryptologist.

Main features:

- Efficient pure C++ implementation
- Fast multi-GPU training and GPU/CPU translation
- State-of-the-art NMT architectures: deep RNN and transformer
- Permissive open source license (MIT)
- [more detail...](https://marian-nmt.github.io/features)

If you use this, please cite:

Marcin Junczys-Dowmunt, Roman Grundkiewicz, Tomasz Dwojak, Hieu Hoang, Kenneth
Heafield, Tom Neckermann, Frank Seide, Ulrich Germann, Alham Fikri Aji, Nikolay
Bogoychev, André F. T. Martins, Alexandra Birch (2018). Marian: Fast Neural
Machine Translation in C++ (http://www.aclweb.org/anthology/P18-4020)

    @InProceedings{mariannmt,
        title     = {Marian: Fast Neural Machine Translation in {C++}},
        author    = {Junczys-Dowmunt, Marcin and Grundkiewicz, Roman and
                     Dwojak, Tomasz and Hoang, Hieu and Heafield, Kenneth and
                     Neckermann, Tom and Seide, Frank and Germann, Ulrich and
                     Fikri Aji, Alham and Bogoychev, Nikolay and
                     Martins, Andr\'{e} F. T. and Birch, Alexandra},
        booktitle = {Proceedings of ACL 2018, System Demonstrations},
        pages     = {116--121},
        publisher = {Association for Computational Linguistics},
        year      = {2018},
        month     = {July},
        address   = {Melbourne, Australia},
        url       = {http://www.aclweb.org/anthology/P18-4020}
    }

## Amun

The handwritten decoder for RNN models compatible with Marian and Nematus has
been superseded by the Marian decoder. The code is available in a separate
repository: https://github.com/marian-nmt/amun

## Website

More information on https://marian-nmt.github.io

- [Quick start](https://marian-nmt.github.io/quickstart)
- [Installation and usage documentation](https://marian-nmt.github.io/docs)
- [Usage examples](https://marian-nmt.github.io/examples)

## Acknowledgements

The development of Marian received funding from the European Union's
_Horizon 2020 Research and Innovation Programme_ under grant agreements
688139 ([SUMMA](http://www.summa-project.eu); 2016-2019),
645487 ([Modern MT](http://www.modernmt.eu); 2015-2017),
644333 ([TraMOOC](http://tramooc.eu/); 2015-2017),
644402 ([HiML](http://www.himl.eu/); 2015-2017),
825303 ([Bergamot](https://browser.mt/); 2019-2021),
the Amazon Academic Research Awards program,
the World Intellectual Property Organization,
and is based upon work supported in part by the Office of the Director of
National Intelligence (ODNI), Intelligence Advanced Research Projects Activity
(IARPA), via contract #FA8650-17-C-9117.

This software contains source code provided by NVIDIA Corporation.
