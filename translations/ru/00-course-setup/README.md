<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T06:59:09+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "ru"
}
-->
# Начало работы с этим курсом

Мы очень рады, что вы начинаете этот курс и готовы увидеть, что вас вдохновит создать с помощью генеративного ИИ!

Чтобы обеспечить ваш успех, на этой странице описаны шаги по настройке, технические требования и информация о том, где можно получить помощь при необходимости.

## Шаги настройки

Чтобы начать обучение на этом курсе, вам нужно выполнить следующие шаги.

### 1. Форкните этот репозиторий

[Сделайте форк всего репозитория](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) в свой аккаунт GitHub, чтобы иметь возможность изменять код и выполнять задания. Вы также можете [поставить звезду (🌟) этому репозиторию](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst), чтобы легче находить его и связанные репозитории.

### 2. Создайте codespace

Чтобы избежать проблем с зависимостями при запуске кода, мы рекомендуем использовать [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) для работы с этим курсом.

Создать его можно, выбрав опцию `Code` в вашем форкнутом репозитории и затем выбрав пункт **Codespaces**.

![Диалоговое окно с кнопками для создания codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. Хранение ваших API ключей

Очень важно хранить ваши API ключи в безопасности при создании любого приложения. Мы рекомендуем не сохранять ключи напрямую в коде. Если вы закоммитите эти данные в публичный репозиторий, это может привести к проблемам с безопасностью и даже нежелательным расходам, если ключи попадут в руки злоумышленников.  
Вот пошаговое руководство, как создать файл `.env` для Python и добавить в него `GITHUB_TOKEN`:

1. **Перейдите в каталог вашего проекта**: Откройте терминал или командную строку и перейдите в корневую папку проекта, где вы хотите создать файл `.env`.

   ```bash
   cd path/to/your/project
   ```

2. **Создайте файл `.env`**: Используйте предпочитаемый текстовый редактор для создания нового файла с именем `.env`. Если вы работаете через командную строку, можно использовать `touch` (на Unix-системах) или `echo` (на Windows):

   Unix-системы:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **Отредактируйте файл `.env`**: Откройте `.env` в текстовом редакторе (например, VS Code, Notepad++ или любом другом). Добавьте следующую строку, заменив `your_github_token_here` на ваш реальный GitHub токен:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **Сохраните файл**: Сохраните изменения и закройте редактор.

5. **Установите `python-dotenv`**: Если вы еще не установили, вам нужно добавить пакет `python-dotenv`, чтобы загружать переменные окружения из файла `.env` в ваше Python-приложение. Установить его можно с помощью `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **Загрузите переменные окружения в вашем Python-скрипте**: В вашем Python-скрипте используйте пакет `python-dotenv` для загрузки переменных из файла `.env`:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

Вот и всё! Вы успешно создали файл `.env`, добавили в него GitHub токен и загрузили его в ваше Python-приложение.

## Как запускать локально на вашем компьютере

Чтобы запускать код локально, у вас должна быть установлена какая-либо версия [Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Далее, чтобы использовать репозиторий, его нужно клонировать:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

После того как вы всё скачали, можно приступать к работе!

## Дополнительные шаги

### Установка Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) — это легковесный установщик для установки [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python и некоторых пакетов.  
Conda — это менеджер пакетов, который упрощает настройку и переключение между разными [виртуальными окружениями](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) и пакетами Python. Он также полезен для установки пакетов, недоступных через `pip`.

Вы можете следовать [руководству по установке MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst).

После установки Miniconda, если вы ещё не сделали этого, клонируйте [репозиторий](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst).

Далее нужно создать виртуальное окружение. Для этого с помощью Conda создайте новый файл окружения (_environment.yml_). Если вы работаете в Codespaces, создайте его в папке `.devcontainer`, то есть `.devcontainer/environment.yml`.

Заполните файл окружения следующим содержимым:

```yml
name: <environment-name>
channels:
  - defaults
  - microsoft
dependencies:
  - python=<python-version>
  - openai
  - python-dotenv
  - pip
  - pip:
      - azure-ai-ml
```

Если при работе с conda возникают ошибки, вы можете вручную установить Microsoft AI Libraries с помощью следующей команды в терминале.

```
conda install -c microsoft azure-ai-ml
```

Файл окружения указывает необходимые зависимости. `<environment-name>` — это имя, которое вы хотите дать своему Conda окружению, а `<python-version>` — версия Python, например, `3` — последняя основная версия Python.

После этого создайте Conda окружение, выполнив команды ниже в командной строке/терминале:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Если возникнут проблемы, обратитесь к [руководству по управлению окружениями Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst).

### Использование Visual Studio Code с расширением поддержки Python

Для этого курса мы рекомендуем использовать редактор [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) с установленным [расширением поддержки Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst). Однако это скорее рекомендация, а не обязательное требование.

> **Примечание**: При открытии репозитория курса в VS Code у вас есть возможность настроить проект внутри контейнера. Это возможно благодаря специальной папке [`.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst), которая есть в репозитории курса. Подробнее об этом позже.

> **Примечание**: После клонирования и открытия папки в VS Code, редактор автоматически предложит установить расширение поддержки Python.

> **Примечание**: Если VS Code предложит открыть репозиторий в контейнере, отклоните это предложение, чтобы использовать локально установленную версию Python.

### Использование Jupyter в браузере

Вы также можете работать над проектом в [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) прямо в браузере. Как классический Jupyter, так и [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) предоставляют удобную среду разработки с такими функциями, как автодополнение, подсветка кода и др.

Чтобы запустить Jupyter локально, откройте терминал/командную строку, перейдите в папку курса и выполните:

```bash
jupyter notebook
```

или

```bash
jupyterhub
```

Это запустит экземпляр Jupyter, а URL для доступа будет показан в окне командной строки.

Перейдя по этому URL, вы увидите структуру курса и сможете открыть любой файл с расширением `*.ipynb`. Например, `08-building-search-applications/python/oai-solution.ipynb`.

### Запуск в контейнере

Альтернативой настройке всего на вашем компьютере или в Codespace является использование [контейнера](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>). Специальная папка `.devcontainer` в репозитории курса позволяет VS Code настроить проект внутри контейнера. За пределами Codespaces для этого потребуется установка Docker, и, честно говоря, это требует определённых навыков, поэтому мы рекомендуем этот способ только тем, кто уже имеет опыт работы с контейнерами.

Один из лучших способов защитить ваши API ключи при использовании GitHub Codespaces — это использовать Secrets Codespace. Пожалуйста, ознакомьтесь с руководством по [управлению секретами в Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst), чтобы узнать больше.

## Уроки и технические требования

Курс состоит из 6 теоретических уроков и 6 практических уроков с кодом.

Для практических уроков мы используем Azure OpenAI Service. Для запуска кода вам потребуется доступ к Azure OpenAI Service и API ключ. Вы можете подать заявку на доступ, [заполнив эту форму](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

Пока ваша заявка обрабатывается, в каждом практическом уроке есть файл `README.md`, где вы можете ознакомиться с кодом и результатами.

## Использование Azure OpenAI Service впервые

Если вы впервые работаете с Azure OpenAI Service, пожалуйста, следуйте этому руководству по [созданию и развертыванию ресурса Azure OpenAI Service](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst).

## Использование OpenAI API впервые

Если вы впервые работаете с OpenAI API, пожалуйста, ознакомьтесь с руководством по [созданию и использованию интерфейса](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst).

## Встречайтесь с другими учащимися

Мы создали каналы в нашем официальном [Discord-сервере AI Community](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) для общения с другими учащимися. Это отличный способ познакомиться с единомышленниками — предпринимателями, разработчиками, студентами и всеми, кто хочет прокачать свои навыки в генеративном ИИ.

[![Присоединиться к Discord-каналу](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

Команда проекта также будет присутствовать на этом Discord-сервере, чтобы помогать учащимся.

## Вклад в проект

Этот курс — проект с открытым исходным кодом. Если вы видите возможности для улучшения или обнаружили ошибки, пожалуйста, создайте [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) или зарегистрируйте [issue на GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

Команда проекта отслеживает все вклады. Участие в open source — отличный способ развить карьеру в области генеративного ИИ.

Большинство вкладов требуют согласия с Contributor License Agreement (CLA) — соглашением, подтверждающим, что вы имеете право и действительно предоставляете нам права на использование вашего вклада. Подробнее на сайте [CLA, Contributor License Agreement](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Важно: при переводе текста в этом репозитории убедитесь, что не используете машинный перевод. Мы проверяем переводы через сообщество, поэтому просим брать на себя ответственность за перевод только на тех языках, которыми вы владеете.

При отправке pull request, CLA-бот автоматически определит, нужно ли вам предоставить CLA, и отметит PR соответствующим образом (например, меткой или комментарием). Просто следуйте инструкциям бота. Это нужно сделать только один раз для всех репозиториев, использующих наш CLA.

Этот проект принял [Кодекс поведения Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). Для дополнительной информации прочитайте FAQ по Кодексу поведения или свяжитесь по адресу [Email opencode](opencode@microsoft.com) с любыми вопросами или комментариями.

## Приступим

Теперь, когда вы выполнили все необходимые шаги для прохождения курса, давайте начнем с [введения в генеративный ИИ и большие языковые модели (LLM)](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**Отказ от ответственности**:  
Этот документ был переведен с помощью сервиса автоматического перевода [Co-op Translator](https://github.com/Azure/co-op-translator). Несмотря на наши усилия по обеспечению точности, просим учитывать, что автоматические переводы могут содержать ошибки или неточности. Оригинальный документ на его исходном языке следует считать авторитетным источником. Для получения критически важной информации рекомендуется обращаться к профессиональному человеческому переводу. Мы не несем ответственности за любые недоразумения или неправильные толкования, возникшие в результате использования данного перевода.