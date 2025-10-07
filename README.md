# Multilingual Analysis — Reproduction Notes

Этот файл описывает шаги, которые мы добавили поверх авторского репозитория, чтобы воспроизводить эксперименты.
Оригинальная инструкция авторов перенесена в `README_authors.md`.


## Подготовка окружения

Мы используем стандартный `pip` и Python 3.12 — никаких дополнительных менеджеров не требуется.

В корне:

   ```bash
   git clone -b reprod --single-branch https://github.com/IsachenkoBogdan/multilingual_analysis
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```

## Запуск экспериментальных скриптов

После активации виртуального окружения:

- **Layer Embedding Decoding**

  ```bash
  cd layers
  python test_layer.py
  ```

- **Neuron Detection**

  ```bash
  cd neuron_detection
  python neuron_detection.py <язык> <количество_документов>
  ```

Остальные подпроекты (`neuron_deactivate`, `neuron_enhancement`) запускаются аналогично авторской инструкции в `README_authors.md`.


## Изменения, внесённые нами

- Зависимости вынесены в `requirements.txt` для воспроизводимости.
- Все скрипты используют `langdetect` вместо `cld3` (в соответствии с зависимостями).
- Исправлены ошибки форматирования и параметры генерации, упомянутые в открытых issues (см. историю коммитов).
- Добавлены указания по созданию окружения через стандартный `pip` и использованию Python 3.12.
