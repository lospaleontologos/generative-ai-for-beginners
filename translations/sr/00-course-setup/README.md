<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:17:54+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "sr"
}
-->
# Почетак рада са овим курсом

Веома смо узбуђени што ћете започети овај курс и видети шта ћете бити инспирисани да направите уз помоћ генеративне вештачке интелигенције!

Да бисмо осигурали ваш успех, ова страница описује кораке за подешавање, техничке захтеве и где можете добити помоћ ако вам затреба.

## Кораци за подешавање

Да бисте започели са овим курсом, потребно је да завршите следеће кораке.

### 1. Форкујте овај репозиторијум

[Форкујте цео овај репозиторијум](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) на свој GitHub налог како бисте могли да мењате код и завршавате изазове. Такође можете [означити (🌟) овај репозиторијум](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) да бисте га лакше пронашли и повезане репозиторијуме.

### 2. Креирајте codespace

Да бисте избегли проблеме са зависностима приликом покретања кода, препоручујемо да овај курс покрећете у [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Ово можете урадити тако што ћете изабрати опцију `Code` на форкованој верзији овог репозиторијума и одабрати опцију **Codespaces**.

![Дијалог који приказује дугмад за креирање codespace-а](../../../00-course-setup/images/who-will-pay.webp)

### 3. Чување ваших API кључева

Чување ваших API кључева безбедним је важно када правите било коју врсту апликације. Препоручујемо да не чувате API кључеве директно у коду. Комитовање тих података у јавни репозиторијум може довести до безбедносних проблема, па чак и непланираних трошкова ако их злоупотреби неко са лошим намерама.  
Ево корак-по-корак упутства како да направите `.env` фајл за Python и додате `GITHUB_TOKEN`:

1. **Идите у директоријум вашег пројекта**: Отворите терминал или командну линију и идите у коренски директоријум вашег пројекта где желите да направите `.env` фајл.

   ```bash
   cd path/to/your/project
   ```

2. **Креирајте `.env` фајл**: Користите свој омиљени уређивач текста да направите нови фајл под именом `.env`. Ако користите командну линију, можете користити `touch` (на Unix системима) или `echo` (на Windows-у):

   Unix системи:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **Уредите `.env` фајл**: Отворите `.env` фајл у уређивачу текста (нпр. VS Code, Notepad++ или неки други уређивач). Додајте следећи ред у фајл, замењујући `your_github_token_here` вашим стварним GitHub токеном:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **Сачувајте фајл**: Сачувајте измене и затворите уређивач текста.

5. **Инсталирајте `python-dotenv`**: Ако већ нисте, потребно је да инсталирате пакет `python-dotenv` који учитава променљиве окружења из `.env` фајла у вашу Python апликацију. Можете га инсталирати помоћу `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **Учитајте променљиве окружења у вашем Python скрипту**: У вашем Python скрипту користите пакет `python-dotenv` да учитате променљиве окружења из `.env` фајла:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

То је то! Успешно сте направили `.env` фајл, додали ваш GitHub токен и учитали га у вашу Python апликацију.

## Како покренути локално на вашем рачунару

Да бисте покренули код локално на вашем рачунару, потребно је да имате инсталирану неку верзију [Python-а](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

Затим, да бисте користили репозиторијум, потребно је да га клоните:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

Када све буде спремно, можете почети!

## Опциони кораци

### Инсталирање Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) је лагани инсталер за инсталацију [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python-а, као и неколико пакета.  
Conda је менаџер пакета који олакшава подешавање и пребацивање између различитих Python [**виртуелних окружења**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) и пакета. Такође је користан за инсталацију пакета који нису доступни преко `pip`.

Можете пратити [MiniConda упутство за инсталацију](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) да бисте га подесили.

Када инсталирате Miniconda, потребно је да клоните [репозиторијум](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (ако то већ нисте урадили).

Затим треба да направите виртуелно окружење. Да бисте то урадили са Conda-ом, направите нови фајл за окружење (_environment.yml_). Ако пратите курс користећи Codespaces, направите овај фајл унутар `.devcontainer` директоријума, дакле `.devcontainer/environment.yml`.

Попуните ваш environment фајл са следећим примером:

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

Ако наиђете на грешке приликом коришћења conda, можете ручно инсталирати Microsoft AI библиотеке помоћу следеће команде у терминалу.

```
conda install -c microsoft azure-ai-ml
```

Фајл окружења одређује зависности које су нам потребне. `<environment-name>` је име које желите да користите за ваше Conda окружење, а `<python-version>` је верзија Python-а коју желите да користите, на пример, `3` је најновија главна верзија Python-а.

Када то урадите, можете креирати Conda окружење покретањем следећих команди у командној линији/терминалу

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Погледајте [Conda упутство за окружења](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) ако наиђете на проблеме.

### Коришћење Visual Studio Code-а са Python подршком

Препоручујемо коришћење [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) уређивача са инсталираним [Python support extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) за овај курс. Међутим, ово је више препорука него обавезан услов.

> **[!NOTE]** Отварањем репозиторијума курса у VS Code-у, имате опцију да подесите пројекат унутар контејнера. То је могуће захваљујући [специјалном `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) директоријуму унутар репозиторијума курса. Више о томе касније.

> **[!NOTE]** Када клоните и отворите директоријум у VS Code-у, он ће вам аутоматски предложити да инсталирате Python подршку.

> **[!NOTE]** Ако вам VS Code предложи да поново отворите репозиторијум у контејнеру, одбијте тај захтев да бисте користили локално инсталирану верзију Python-а.

### Коришћење Jupyter-а у прегледачу

Такође можете радити на пројекту користећи [Jupyter окружење](https://jupyter.org?WT.mc_id=academic-105485-koreyst) директно у вашем прегледачу. И класични Jupyter и [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) пружају пријатно развојно окружење са функцијама као што су аутоматско довршавање, истицање кода и сл.

Да бисте покренули Jupyter локално, идите у терминал/командну линију, навигирајте до директоријума курса и покрените:

```bash
jupyter notebook
```

или

```bash
jupyterhub
```

Ово ће покренути Jupyter инстанцу, а URL за приступ биће приказан у командној линији.

Када приступите URL-у, требало би да видите структуру курса и да можете да отворите било који `*.ipynb` фајл. На пример, `08-building-search-applications/python/oai-solution.ipynb`.

### Покретање у контејнеру

Алтернатива подешавању свега на вашем рачунару или Codespace-у је коришћење [контејнера](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>). Специјални `.devcontainer` фолдер унутар репозиторијума курса омогућава VS Code-у да подеси пројекат унутар контејнера. Изван Codespaces-а, ово захтева инсталацију Docker-а и, искрено, укључује нешто више посла, па ову опцију препоручујемо само онима који имају искуства са радом у контејнерима.

Један од најбољих начина да заштитите своје API кључеве када користите GitHub Codespaces је коришћење Codespace Secrets. Пратите [упутство за управљање Codespaces тајнама](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) да бисте сазнали више о томе.

## Лекције и технички захтеви

Курс има 6 концептуалних лекција и 6 програмерских лекција.

За програмерске лекције користимо Azure OpenAI Service. Потребан вам је приступ Azure OpenAI сервису и API кључ да бисте покренули овај код. Можете се пријавити за приступ [попуњавањем ове пријаве](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

Док чекате да ваша пријава буде обрађена, свака програмерска лекција такође садржи `README.md` фајл у коме можете видети код и резултате.

## Коришћење Azure OpenAI сервиса први пут

Ако први пут радите са Azure OpenAI сервисом, пратите ово упутство како да [креирате и деплојујете Azure OpenAI Service ресурс.](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## Коришћење OpenAI API-ја први пут

Ако први пут радите са OpenAI API-јем, пратите упутство како да [креирате и користите интерфејс.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## Упознајте друге учеснике

Креирали смо канале на нашем званичном [AI Community Discord серверу](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) за упознавање са другим учесницима. Ово је одличан начин да се повежете са другим предузетницима, програмерима, студентима и свима који желе да напредују у генеративној вештачкој интелигенцији.

[![Придружи се discord каналу](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

Тим пројекта ће такође бити на овом Discord серверу да помогне свим учесницима.

## Допринос

Овај курс је иницијатива отвореног кода. Ако приметите могућности за побољшање или проблеме, молимо вас да направите [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) или пријавите [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

Тим пројекта прати све доприносе. Допринос отвореном коду је одличан начин да изградите каријеру у генеративној вештачкој интелигенцији.

Већина доприноса захтева да се сложите са Уговором о лиценци за доприносе (CLA) којим изјављујете да имате право и заиста нам дајете права да користимо ваш допринос. За детаље посетите [CLA, Contributor License Agreement сајт](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Важно: приликом превођења текста у овом репозиторијуму, молимо вас да не користите машински превод. Преводе ће проверити заједница, па се пријављујте само за преводе на језике које добро познајете.

Када пошаљете pull request, CLA-бот ће аутоматски одредити да ли треба да доставите CLA и означити PR на одговарајући начин (нпр. етикета, коментар). Само пратите упутства бота. Ово ћете морати урадити само једном за све репозиторијуме који користе наш CLA.

Овај пројекат је усвојио [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). За више информација прочитајте FAQ о Кодексу понашања или контактирајте [Email opencode](opencode@microsoft.com) за додатна питања или коментаре.

## Хајде да почнемо

Сада када сте завршили потребне кораке за овај курс, кренимо са [уводом у генеративну вештачку интелигенцију и LLM-ове](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**Одрицање од одговорности**:  
Овај документ је преведен коришћењем AI сервиса за превођење [Co-op Translator](https://github.com/Azure/co-op-translator). Иако се трудимо да превод буде тачан, молимо вас да имате у виду да аутоматски преводи могу садржати грешке или нетачности. Оригинални документ на његовом изворном језику треба сматрати ауторитетним извором. За критичне информације препоручује се професионални људски превод. Нисмо одговорни за било каква неспоразума или погрешна тумачења која произилазе из коришћења овог превода.