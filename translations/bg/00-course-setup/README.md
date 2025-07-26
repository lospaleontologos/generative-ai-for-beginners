<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:17:27+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "bg"
}
-->
# Започване с този курс

Много се радваме, че започвате този курс и ще видите какво ще ви вдъхнови да създадете с Generative AI!

За да гарантираме вашия успех, тази страница описва стъпките за настройка, техническите изисквания и къде да потърсите помощ при нужда.

## Стъпки за настройка

За да започнете курса, трябва да изпълните следните стъпки.

### 1. Форкнете това хранилище

[Форкнете цялото това хранилище](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) в своя GitHub акаунт, за да можете да променяте кода и да изпълнявате предизвикателствата. Можете също да [добавите това хранилище в звездички (🌟)](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst), за да го намирате по-лесно заедно с други свързани хранилища.

### 2. Създайте codespace

За да избегнете проблеми с зависимости при изпълнение на кода, препоръчваме да използвате този курс в [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Това може да се направи като изберете опцията `Code` във вашата форкната версия на хранилището и след това изберете опцията **Codespaces**.

![Диалогов прозорец с бутони за създаване на codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. Съхраняване на вашите API ключове

Важно е да пазите вашите API ключове сигурни, когато създавате каквото и да е приложение. Препоръчваме да не съхранявате API ключове директно в кода си. Ако ги качите в публично хранилище, това може да доведе до проблеми със сигурността и дори нежелани разходи, ако бъдат използвани от злонамерени лица.  
Ето стъпка по стъпка как да създадете `.env` файл за Python и да добавите `GITHUB_TOKEN`:

1. **Отидете в директорията на проекта си**: Отворете терминала или командния ред и навигирайте до кореновата директория на проекта, където искате да създадете `.env` файла.

   ```bash
   cd path/to/your/project
   ```

2. **Създайте `.env` файла**: Използвайте предпочитания текстов редактор, за да създадете нов файл с име `.env`. Ако използвате командния ред, можете да използвате `touch` (за Unix-базирани системи) или `echo` (за Windows):

   Unix-базирани системи:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **Редактирайте `.env` файла**: Отворете `.env` файла в текстов редактор (например VS Code, Notepad++ или друг). Добавете следния ред, като замените `your_github_token_here` с вашия реален GitHub токен:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **Запазете файла**: Запазете промените и затворете редактора.

5. **Инсталирайте `python-dotenv`**: Ако още не сте го направили, трябва да инсталирате пакета `python-dotenv`, който зарежда променливите на средата от `.env` файла във вашето Python приложение. Можете да го инсталирате с `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **Заредете променливите на средата в Python скрипта си**: В Python скрипта използвайте `python-dotenv`, за да заредите променливите от `.env` файла:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

Това е! Успешно създадохте `.env` файл, добавихте GitHub токена си и го заредихте в Python приложението.

## Как да стартирате локално на вашия компютър

За да стартирате кода локално на компютъра си, трябва да имате инсталирана някаква версия на [Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

След това трябва да клонирате хранилището:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

След като имате всичко изтеглено, можете да започнете!

## Допълнителни стъпки

### Инсталиране на Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) е лек инсталатор за инсталиране на [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python и няколко пакета.  
Conda е пакетен мениджър, който улеснява създаването и превключването между различни Python [**виртуални среди**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) и пакети. Той е полезен и за инсталиране на пакети, които не са налични чрез `pip`.

Можете да следвате [ръководството за инсталиране на MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst), за да го настроите.

След като инсталирате Miniconda, трябва да клонирате [хранилището](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (ако още не сте го направили).

След това трябва да създадете виртуална среда. За да го направите с Conda, създайте нов файл за средата (_environment.yml_). Ако използвате Codespaces, създайте този файл в директорията `.devcontainer`, т.е. `.devcontainer/environment.yml`.

Попълнете файла с конфигурацията по-долу:

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

Ако срещнете грешки при използване на conda, можете ръчно да инсталирате Microsoft AI Libraries с командата по-долу в терминала.

```
conda install -c microsoft azure-ai-ml
```

Файлът за средата указва зависимостите, от които се нуждаем. `<environment-name>` е името, което искате да дадете на Conda средата, а `<python-version>` е версията на Python, която искате да използвате, например `3` за последната основна версия на Python.

След това създайте Conda средата, като изпълните командите по-долу в командния ред/терминала:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Ако имате проблеми, вижте [ръководството за Conda среди](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst).

### Използване на Visual Studio Code с разширението за Python

Препоръчваме да използвате редактора [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) с инсталирано [разширение за Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) за този курс. Това е препоръка, а не задължително изискване.

> **Забележка**: Когато отворите хранилището на курса във VS Code, имате възможност да настроите проекта в контейнер. Това е възможно благодарение на специалната директория [`.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) в хранилището. Повече за това по-нататък.

> **Забележка**: След като клонирате и отворите директорията във VS Code, той автоматично ще ви предложи да инсталирате разширение за Python.

> **Забележка**: Ако VS Code ви предложи да отворите хранилището в контейнер, откажете, ако искате да използвате локално инсталираната версия на Python.

### Използване на Jupyter в браузъра

Можете да работите по проекта и чрез [Jupyter среда](https://jupyter.org?WT.mc_id=academic-105485-koreyst) директно в браузъра си. Класическият Jupyter и [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) предлагат удобна среда за разработка с функции като автодовършване, оцветяване на кода и др.

За да стартирате Jupyter локално, отворете терминала/командния ред, навигирайте до директорията на курса и изпълнете:

```bash
jupyter notebook
```

или

```bash
jupyterhub
```

Това ще стартира Jupyter и URL адресът за достъп ще се покаже в прозореца на командния ред.

След като отворите URL адреса, ще видите структурата на курса и ще можете да навигирате до всеки `*.ipynb` файл. Например, `08-building-search-applications/python/oai-solution.ipynb`.

### Стартиране в контейнер

Алтернатива на настройването на всичко на вашия компютър или Codespace е използването на [контейнер](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>). Специалната папка `.devcontainer` в хранилището позволява на VS Code да настрои проекта в контейнер. Извън Codespaces това изисква инсталиране на Docker и, честно казано, малко повече работа, затова препоръчваме това само на хора с опит в работата с контейнери.

Един от най-добрите начини да защитите API ключовете си при използване на GitHub Codespaces е чрез използване на Codespace Secrets. Моля, следвайте ръководството за [управление на тайни в Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst), за да научите повече.

## Уроци и технически изисквания

Курсът съдържа 6 концептуални урока и 6 урока с кодиране.

За уроците с кодиране използваме Azure OpenAI Service. Ще ви трябва достъп до Azure OpenAI service и API ключ, за да изпълните кода. Можете да кандидатствате за достъп, като [попълните тази заявка](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

Докато чакате заявката ви да бъде обработена, всеки урок с кодиране включва и файл `README.md`, където можете да разгледате кода и резултатите.

## Използване на Azure OpenAI Service за първи път

Ако използвате Azure OpenAI service за първи път, моля, следвайте това ръководство как да [създадете и разположите ресурс в Azure OpenAI Service.](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## Използване на OpenAI API за първи път

Ако използвате OpenAI API за първи път, моля, следвайте ръководството как да [създадете и използвате интерфейса.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## Срещнете други обучаващи се

Създадохме канали в официалния ни [AI Community Discord сървър](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) за срещи с други обучаващи се. Това е чудесен начин да се свържете с други предприемачи, разработчици, студенти и всеки, който иска да се развива в Generative AI.

[![Присъединете се към Discord канала](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

Екипът на проекта също ще бъде в този Discord сървър, за да помага на обучаващите се.

## Принос

Този курс е инициатива с отворен код. Ако забележите възможности за подобрение или проблеми, моля, създайте [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) или докладвайте [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

Екипът на проекта следи всички приноси. Приносът към проекти с отворен код е отличен начин да развиете кариерата си в Generative AI.

Повечето приноси изискват да се съгласите с Contributor License Agreement (CLA), който декларира, че имате правото и действително предоставяте правата за използване на вашия принос. За подробности посетете [CLA, Contributor License Agreement уебсайт](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Важно: при превод на текст в това хранилище, моля, не използвайте машинен превод. Ще проверяваме преводите чрез общността, затова моля, доброволствайте само за преводи на езици, на които сте компетентни.

Когато подадете pull request, CLA-бот автоматично ще определи дали трябва да предоставите CLA и ще маркира PR съответно (например с етикет или коментар). Просто следвайте инструкциите на бота. Това се прави само веднъж за всички хранилища, използващи нашия CLA.

Този проект е приел [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). За повече информация прочетете Често задаваните въпроси за Кодекса на поведение или се свържете с [Email opencode](opencode@microsoft.com) при допълнителни въпроси или коментари.

## Нека започнем

След като изпълнихте необходимите стъпки за този курс, нека започнем с [въведение в Generative AI и LLMs](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**Отказ от отговорност**:  
Този документ е преведен с помощта на AI преводаческа услуга [Co-op Translator](https://github.com/Azure/co-op-translator). Въпреки че се стремим към точност, моля, имайте предвид, че автоматизираните преводи могат да съдържат грешки или неточности. Оригиналният документ на неговия роден език трябва да се счита за авторитетен източник. За критична информация се препоръчва професионален човешки превод. Ние не носим отговорност за каквито и да е недоразумения или неправилни тълкувания, произтичащи от използването на този превод.