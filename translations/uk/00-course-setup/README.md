<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:19:48+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "uk"
}
-->
# Початок роботи з цим курсом

Ми дуже раді, що ви розпочинаєте цей курс і побачите, що вас надихне створити за допомогою генеративного ШІ!

Щоб забезпечити ваш успіх, на цій сторінці наведено кроки налаштування, технічні вимоги та інформацію про те, де можна отримати допомогу, якщо це буде потрібно.

## Кроки налаштування

Щоб почати проходити цей курс, вам потрібно виконати наступні кроки.

### 1. Форкніть цей репозиторій

[Зробіть форк усього цього репозиторію](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) у свій обліковий запис GitHub, щоб мати змогу змінювати код і виконувати завдання. Ви також можете [поставити зірочку (🌟) цьому репозиторію](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst), щоб легше знаходити його та пов’язані репозиторії.

### 2. Створіть codespace

Щоб уникнути проблем із залежностями під час запуску коду, ми рекомендуємо запускати цей курс у [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Це можна зробити, вибравши опцію `Code` у вашій форкнутій версії цього репозиторію та обравши опцію **Codespaces**.

![Діалогове вікно з кнопками для створення codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. Збереження ваших API ключів

Забезпечення безпеки ваших API ключів дуже важливе при створенні будь-яких додатків. Ми рекомендуємо не зберігати API ключі безпосередньо у коді. Комітування таких даних у публічний репозиторій може призвести до проблем із безпекою та навіть небажаних витрат, якщо ними скористається зловмисник.  
Ось покрокова інструкція, як створити файл `.env` для Python і додати `GITHUB_TOKEN`:

1. **Перейдіть до каталогу вашого проєкту**: Відкрийте термінал або командний рядок і перейдіть до кореневої папки вашого проєкту, де ви хочете створити файл `.env`.

   ```bash
   cd path/to/your/project
   ```

2. **Створіть файл `.env`**: Використайте улюблений текстовий редактор, щоб створити новий файл з назвою `.env`. Якщо ви працюєте з командним рядком, можна використати `touch` (на системах Unix) або `echo` (на Windows):

   Unix-подібні системи:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **Відредагуйте файл `.env`**: Відкрийте `.env` у текстовому редакторі (наприклад, VS Code, Notepad++ або будь-якому іншому). Додайте наступний рядок, замінивши `your_github_token_here` на ваш реальний GitHub токен:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **Збережіть файл**: Збережіть зміни та закрийте редактор.

5. **Встановіть `python-dotenv`**: Якщо ви ще не встановили, потрібно додати пакет `python-dotenv`, щоб завантажувати змінні середовища з файлу `.env` у ваш Python-додаток. Це можна зробити за допомогою `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **Завантажте змінні середовища у вашому Python-скрипті**: У вашому Python-скрипті використайте пакет `python-dotenv` для завантаження змінних середовища з файлу `.env`:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

Ось і все! Ви успішно створили файл `.env`, додали свій GitHub токен і завантажили його у ваш Python-додаток.

## Як запускати локально на вашому комп’ютері

Щоб запускати код локально на вашому комп’ютері, вам потрібно мати встановлену якусь версію [Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Щоб скористатися репозиторієм, його потрібно клонувати:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

Після того, як усе буде готово, можете починати!

## Додаткові кроки

### Встановлення Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) — це легкий інсталятор для встановлення [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, а також кількох пакетів.  
Conda — це менеджер пакетів, який полегшує налаштування та перемикання між різними [віртуальними середовищами](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) Python і пакетами. Він також корисний для встановлення пакетів, яких немає у `pip`.

Ви можете скористатися [інструкцією з встановлення Miniconda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst).

Після встановлення Miniconda потрібно клонувати [репозиторій](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (якщо ви ще цього не зробили).

Далі потрібно створити віртуальне середовище. Для цього з Conda створіть новий файл середовища (_environment.yml_). Якщо ви працюєте у Codespaces, створіть його у каталозі `.devcontainer`, тобто `.devcontainer/environment.yml`.

Заповніть файл середовища наступним фрагментом:

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

Якщо у вас виникають помилки при використанні conda, ви можете вручну встановити Microsoft AI Libraries за допомогою такої команди у терміналі.

```
conda install -c microsoft azure-ai-ml
```

Файл середовища визначає залежності, які нам потрібні. `<environment-name>` — це ім’я, яке ви хочете використати для свого Conda-середовища, а `<python-version>` — версія Python, яку ви хочете використовувати, наприклад, `3` — це остання основна версія Python.

Після цього ви можете створити своє Conda-середовище, виконавши наведені нижче команди у командному рядку/терміналі:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Якщо виникнуть проблеми, зверніться до [інструкції з Conda середовищ](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst).

### Використання Visual Studio Code з розширенням підтримки Python

Для цього курсу ми рекомендуємо використовувати редактор [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) з встановленим [розширенням підтримки Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst). Проте це радше рекомендація, а не обов’язкова вимога.

> **Примітка**: Відкривши репозиторій курсу у VS Code, у вас є можливість налаштувати проєкт у контейнері. Це можливо завдяки [спеціальному каталогу `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst), який є у репозиторії курсу. Про це буде більше пізніше.

> **Примітка**: Після клонування та відкриття каталогу у VS Code, редактор автоматично запропонує встановити розширення підтримки Python.

> **Примітка**: Якщо VS Code запропонує повторно відкрити репозиторій у контейнері, відхиліть це, щоб використовувати локально встановлену версію Python.

### Використання Jupyter у браузері

Ви також можете працювати над проєктом, використовуючи [Jupyter середовище](https://jupyter.org?WT.mc_id=academic-105485-koreyst) прямо у браузері. Як класичний Jupyter, так і [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) пропонують зручне середовище розробки з такими функціями, як автозаповнення, підсвічування коду тощо.

Щоб запустити Jupyter локально, відкрийте термінал/командний рядок, перейдіть до каталогу курсу і виконайте:

```bash
jupyter notebook
```

або

```bash
jupyterhub
```

Це запустить інстанс Jupyter, а URL для доступу буде показано у вікні командного рядка.

Після переходу за URL ви побачите структуру курсу і зможете відкривати будь-які файли `*.ipynb`. Наприклад, `08-building-search-applications/python/oai-solution.ipynb`.

### Запуск у контейнері

Альтернативою налаштуванню всього на вашому комп’ютері або у Codespace є використання [контейнера](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>). Спеціальна папка `.devcontainer` у репозиторії курсу дозволяє VS Code налаштувати проєкт у контейнері. Позаяк поза Codespaces це потребує встановлення Docker і, чесно кажучи, трохи складніше, ми рекомендуємо це лише тим, хто має досвід роботи з контейнерами.

Один із найкращих способів захистити ваші API ключі при використанні GitHub Codespaces — це використання Codespace Secrets. Будь ласка, ознайомтеся з [інструкцією з керування секретами в Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst), щоб дізнатися більше.

## Уроки та технічні вимоги

Курс містить 6 концептуальних уроків і 6 уроків з кодування.

Для уроків з кодування ми використовуємо Azure OpenAI Service. Вам знадобиться доступ до Azure OpenAI service та API ключ для запуску цього коду. Ви можете подати заявку на доступ, [заповнивши цю форму](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

Поки ваша заявка обробляється, у кожному уроці з кодування також є файл `README.md`, де ви можете переглянути код і результати.

## Використання Azure OpenAI Service вперше

Якщо ви вперше працюєте з Azure OpenAI service, будь ласка, дотримуйтесь цієї інструкції, як [створити та розгорнути ресурс Azure OpenAI Service](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst).

## Використання OpenAI API вперше

Якщо ви вперше працюєте з OpenAI API, будь ласка, дотримуйтесь інструкції, як [створити та використовувати інтерфейс](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst).

## Познайомтесь з іншими учнями

Ми створили канали в нашому офіційному [AI Community Discord сервері](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) для знайомства з іншими учнями. Це чудовий спосіб налагодити зв’язки з іншими однодумцями — підприємцями, розробниками, студентами та всіма, хто хоче підвищити свій рівень у генеративному ШІ.

[![Приєднатися до Discord каналу](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

Команда проєкту також буде на цьому Discord сервері, щоб допомагати учням.

## Внесок у проєкт

Цей курс є ініціативою з відкритим кодом. Якщо ви бачите можливості для покращення або помилки, будь ласка, створіть [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) або зареєструйте [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

Команда проєкту відстежуватиме всі внески. Внесок у відкритий код — це чудовий спосіб розвивати кар’єру у генеративному ШІ.

Більшість внесків вимагають вашої згоди з Contributor License Agreement (CLA), що підтверджує, що ви маєте право і дійсно надаєте нам права на використання вашого внеску. Детальніше дивіться на сайті [CLA, Contributor License Agreement](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Важливо: при перекладі тексту в цьому репозиторії, будь ласка, не використовуйте машинний переклад. Ми перевірятимемо переклади через спільноту, тому просимо братися за переклади лише тих мов, якими ви володієте.

Коли ви надсилаєте pull request, CLA-бот автоматично визначить, чи потрібно вам надати CLA, і відповідно позначить PR (наприклад, міткою або коментарем). Просто дотримуйтесь інструкцій бота. Це потрібно зробити лише один раз для всіх репозиторіїв, які використовують наш CLA.

Цей проєкт прийняв [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). Для додаткової інформації прочитайте FAQ щодо Кодексу поведінки або звертайтеся на [Email opencode](opencode@microsoft.com) з будь-якими питаннями чи коментарями.

## Почнемо

Тепер, коли ви виконали всі необхідні кроки для проходження курсу, почнемо з [вступу до генеративного ШІ та великих мовних моделей (LLMs)](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**Відмова від відповідальності**:  
Цей документ було перекладено за допомогою сервісу автоматичного перекладу [Co-op Translator](https://github.com/Azure/co-op-translator). Хоча ми прагнемо до точності, будь ласка, майте на увазі, що автоматичні переклади можуть містити помилки або неточності. Оригінальний документ рідною мовою слід вважати авторитетним джерелом. Для критично важливої інформації рекомендується звертатися до професійного людського перекладу. Ми не несемо відповідальності за будь-які непорозуміння або неправильні тлумачення, що виникли внаслідок використання цього перекладу.