# Разработка системы извлечения информации из текста: определение сущностей, событий и отношений

## Описание

Данный проект посвящен разработке системы для извлечения информации из текста на русском языке, включая определение сущностей, событий и отношений между ними. Система реализована на Python с использованием GPU для ускорения вычислений и интегрирована с Telegram посредством создания бота, который принимает текст на вход и отправляет результат ответным сообщением.

## Технологии и библиотеки

- Python 3.x
- TensorFlow
- spaCy (`ru_core_news_sm`)
- Transformers (`cointegrated/rubert-tiny`)
- PyTelegramBotAPI
- GPU оптимизация

## Установка

1. **Клонируйте репозиторий:**

   ```bash
   git clone https://github.com/YourUsername/Lab-2.git
   cd Lab-2
   ```

2. **Создайте и активируйте виртуальное окружение (рекомендуется):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # для Linux/Mac
   venv\Scripts\activate  # для Windows
   ```

3. **Установите необходимые зависимости:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Загрузите модель spaCy для русского языка:**

   ```bash
   python -m spacy download ru_core_news_sm
   ```

5. **Укажите токен вашего Telegram бота:**

   В файле `bot.py` замените `'YOUR_TELEGRAM_BOT_TOKEN'` на токен вашего бота, который вы можете получить у @BotFather.

## Использование

1. **Запустите бота:**

   ```bash
   python bot.py
   ```

2. **В Telegram найдите вашего бота и начните диалог:**

   - Отправьте команду `/start` для начала работы.
   - Отправьте любой текст на русском языке.
   - Бот обработает текст и отправит вам результаты извлечения сущностей, событий и отношений.

## Пример

**Входной текст:**

```markdown
Президент Владимир Путин встретился с министром иностранных дел Сергеем Лавровым в Москве.
```

**Ответ бота:**

```markdown
🏷 **Найденные сущности:**
- Владимир Путин (PER)
- Сергей Лавров (PER)
- Москва (LOC)

⚡️ **Найденные события:**
- встретиться

🔗 **Извлеченные отношения:**
- Президент — встретиться — министр
```

## Google Colab

Для ознакомления с работой модели и тестирования кода в Google Colab воспользуйтесь ссылкой:

[Ссылка на Colab](#https://colab.research.google.com/drive/18IKDGtk0NjgtQgo9V_FPE7DxojeRjIkN)

## Структура проекта

- `Разработка_системы_извлечения_информации_из_текста_определение_сущностей,_событий_и_отношений.ipynb` — основной файл с кодом Telegram бота.
- `requirements.txt` — список зависимостей проекта.
- `README.md` — описание проекта и инструкция по использованию.

## Заметки по оптимизации под GPU

- Убедитесь, что у вас установлены драйверы CUDA и cuDNN, совместимые с версией TensorFlow, которую вы используете.
- Проверьте, что TensorFlow действительно использует GPU, запустив программу и наблюдая за загрузкой GPU с помощью `nvidia-smi`.
