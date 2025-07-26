<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:00:27+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "ur"
}
-->
# اس کورس کے ساتھ شروعات

ہم آپ کے اس کورس کو شروع کرنے اور دیکھنے کے لیے بہت پرجوش ہیں کہ آپ Generative AI کے ساتھ کیا کچھ تخلیق کرتے ہیں!

آپ کی کامیابی کو یقینی بنانے کے لیے، یہ صفحہ سیٹ اپ کے مراحل، تکنیکی ضروریات، اور مدد حاصل کرنے کے ذرائع بیان کرتا ہے۔

## سیٹ اپ کے مراحل

اس کورس کو شروع کرنے کے لیے، آپ کو درج ذیل مراحل مکمل کرنے ہوں گے۔

### 1. اس ریپو کو فورک کریں

اپنے GitHub اکاؤنٹ پر [اس پورے ریپو کو فورک کریں](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) تاکہ آپ کسی بھی کوڈ میں تبدیلی کر سکیں اور چیلنجز مکمل کر سکیں۔ آپ اسے اور متعلقہ ریپوز کو آسانی سے تلاش کرنے کے لیے [اس ریپو کو اسٹار (🌟) بھی کر سکتے ہیں](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst)۔

### 2. کوڈ اسپیس بنائیں

کوڈ چلانے کے دوران کسی بھی انحصاری کے مسائل سے بچنے کے لیے، ہم تجویز کرتے ہیں کہ آپ یہ کورس [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) میں چلائیں۔

یہ آپ کے فورک کیے ہوئے ریپو میں `Code` آپشن منتخب کر کے اور پھر **Codespaces** آپشن چن کر بنایا جا سکتا ہے۔

![کوڈ اسپیس بنانے کے بٹن دکھانے والا ڈائیلاگ](../../../00-course-setup/images/who-will-pay.webp)

### 3. اپنے API کیز محفوظ کریں

کسی بھی قسم کی ایپلیکیشن بناتے وقت اپنے API کیز کو محفوظ رکھنا بہت ضروری ہے۔ ہم تجویز کرتے ہیں کہ API کیز کو براہ راست اپنے کوڈ میں نہ رکھیں۔ اگر آپ یہ تفصیلات کسی پبلک ریپوزٹری میں کمیٹ کر دیں تو یہ سیکیورٹی کے مسائل اور غیر متوقع اخراجات کا باعث بن سکتا ہے، خاص طور پر اگر کوئی بدنیت شخص ان کا غلط استعمال کرے۔

یہاں Python کے لیے `.env` فائل بنانے اور `GITHUB_TOKEN` شامل کرنے کا مرحلہ وار طریقہ ہے:

1. **اپنے پروجیکٹ ڈائریکٹری میں جائیں**: اپنا ٹرمینل یا کمانڈ پرامپٹ کھولیں اور اس پروجیکٹ کی روٹ ڈائریکٹری میں جائیں جہاں آپ `.env` فائل بنانا چاہتے ہیں۔

   ```bash
   cd path/to/your/project
   ```

2. **`.env` فائل بنائیں**: اپنی پسندیدہ ٹیکسٹ ایڈیٹر سے `.env` نامی نئی فائل بنائیں۔ اگر آپ کمانڈ لائن استعمال کر رہے ہیں تو Unix-based سسٹمز پر `touch` یا Windows پر `echo` استعمال کر سکتے ہیں:

   Unix-based سسٹمز:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **`.env` فائل میں ترمیم کریں**: `.env` فائل کو کسی ٹیکسٹ ایڈیٹر (جیسے VS Code، Notepad++، یا کوئی اور) میں کھولیں۔ اس فائل میں درج ذیل لائن شامل کریں، اور `your_github_token_here` کو اپنے اصل GitHub ٹوکن سے بدل دیں:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **فائل محفوظ کریں**: تبدیلیاں محفوظ کریں اور ٹیکسٹ ایڈیٹر بند کر دیں۔

5. **`python-dotenv` انسٹال کریں**: اگر آپ نے پہلے سے نہیں کیا تو، آپ کو `python-dotenv` پیکیج انسٹال کرنا ہوگا تاکہ آپ کی Python ایپلیکیشن `.env` فائل سے ماحول کی متغیرات لوڈ کر سکے۔ آپ اسے `pip` کے ذریعے انسٹال کر سکتے ہیں:

   ```bash
   pip install python-dotenv
   ```

6. **اپنے Python اسکرپٹ میں ماحول کی متغیرات لوڈ کریں**: اپنے Python اسکرپٹ میں `python-dotenv` پیکیج استعمال کریں تاکہ `.env` فائل سے ماحول کی متغیرات لوڈ کی جا سکیں:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

بس! آپ نے کامیابی سے `.env` فائل بنائی، اپنا GitHub ٹوکن شامل کیا، اور اسے اپنی Python ایپلیکیشن میں لوڈ کر لیا۔

## اپنے کمپیوٹر پر لوکل طور پر کوڈ چلانا

اپنے کمپیوٹر پر کوڈ چلانے کے لیے، آپ کے پاس [Python کا کوئی ورژن انسٹال ہونا چاہیے](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)۔

اس کے بعد ریپوزٹری استعمال کرنے کے لیے، آپ کو اسے کلون کرنا ہوگا:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

جب آپ کے پاس سب کچھ تیار ہو جائے، تو آپ شروع کر سکتے ہیں!

## اختیاری مراحل

### Miniconda انسٹال کرنا

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) ایک ہلکا پھلکا انسٹالر ہے جو [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst)، Python، اور چند پیکیجز انسٹال کرنے کے لیے استعمال ہوتا ہے۔  
Conda خود ایک پیکیج مینیجر ہے جو مختلف Python [**ورچوئل ماحول**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) اور پیکیجز کو آسانی سے سیٹ اپ اور سوئچ کرنے میں مدد دیتا ہے۔ یہ ان پیکیجز کو انسٹال کرنے میں بھی مددگار ہے جو `pip` کے ذریعے دستیاب نہیں ہوتے۔

آپ [MiniConda انسٹالیشن گائیڈ](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) پر عمل کر کے اسے سیٹ اپ کر سکتے ہیں۔

Miniconda انسٹال کرنے کے بعد، اگر آپ نے پہلے نہیں کیا تو [ریپوزٹری](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) کلون کریں۔

اس کے بعد، آپ کو ایک ورچوئل ماحول بنانا ہوگا۔ Conda کے ساتھ یہ کرنے کے لیے، ایک نیا ماحول فائل (_environment.yml_) بنائیں۔ اگر آپ Codespaces استعمال کر رہے ہیں تو اسے `.devcontainer` ڈائریکٹری میں بنائیں، یعنی `.devcontainer/environment.yml`۔

اپنے ماحول کی فائل میں نیچے دیا گیا کوڈ شامل کریں:

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

اگر آپ کو conda استعمال کرتے ہوئے ایرر آ رہے ہیں تو آپ ٹرمینل میں درج ذیل کمانڈ کے ذریعے Microsoft AI Libraries دستی طور پر انسٹال کر سکتے ہیں۔

```
conda install -c microsoft azure-ai-ml
```

ماحول کی فائل میں وہ انحصار شامل ہوتے ہیں جن کی ہمیں ضرورت ہے۔ `<environment-name>` سے مراد وہ نام ہے جو آپ اپنے Conda ماحول کے لیے استعمال کرنا چاہتے ہیں، اور `<python-version>` Python کا وہ ورژن ہے جو آپ استعمال کرنا چاہتے ہیں، مثلاً `3` Python کا تازہ ترین بڑا ورژن ہے۔

یہ سب کرنے کے بعد، آپ نیچے دی گئی کمانڈز چلا کر اپنا Conda ماحول بنا سکتے ہیں:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

اگر آپ کو کوئی مسئلہ ہو تو [Conda environments guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) دیکھیں۔

### Visual Studio Code کو Python سپورٹ ایکسٹینشن کے ساتھ استعمال کرنا

ہم اس کورس کے لیے [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) ایڈیٹر کو [Python سپورٹ ایکسٹینشن](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) کے ساتھ استعمال کرنے کی سفارش کرتے ہیں۔ یہ صرف ایک سفارش ہے، لازمی شرط نہیں۔

> **نوٹ**: جب آپ کورس ریپوزٹری کو VS Code میں کھولیں گے، تو آپ کے پاس پروجیکٹ کو کنٹینر کے اندر سیٹ اپ کرنے کا آپشن ہوگا۔ یہ اس لیے ممکن ہے کیونکہ کورس ریپوزٹری میں [خاص `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) ڈائریکٹری موجود ہے۔ اس پر بعد میں مزید بات ہوگی۔

> **نوٹ**: جب آپ ریپوزٹری کو کلون کر کے VS Code میں کھولیں گے، تو یہ خود بخود آپ کو Python سپورٹ ایکسٹینشن انسٹال کرنے کی تجویز دے گا۔

> **نوٹ**: اگر VS Code آپ کو ریپوزٹری کو کنٹینر میں دوبارہ کھولنے کا کہے، تو اس درخواست کو مسترد کر دیں تاکہ آپ لوکل انسٹال شدہ Python ورژن استعمال کر سکیں۔

### براؤزر میں Jupyter استعمال کرنا

آپ اس پروجیکٹ پر [Jupyter ماحول](https://jupyter.org?WT.mc_id=academic-105485-koreyst) کو اپنے براؤزر میں بھی استعمال کر سکتے ہیں۔ کلاسک Jupyter اور [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) دونوں ایک خوشگوار ڈیولپمنٹ ماحول فراہم کرتے ہیں جس میں آٹو کمپلیشن، کوڈ ہائی لائٹنگ وغیرہ جیسی خصوصیات شامل ہیں۔

Jupyter لوکل طور پر شروع کرنے کے لیے، ٹرمینل/کمانڈ لائن میں کورس ڈائریکٹری پر جائیں اور درج ذیل کمانڈ چلائیں:

```bash
jupyter notebook
```

یا

```bash
jupyterhub
```

یہ Jupyter کا ایک انسٹانس شروع کرے گا اور اس کا URL کمانڈ لائن ونڈو میں دکھایا جائے گا۔

جب آپ اس URL تک پہنچیں گے، تو آپ کورس کا خاکہ دیکھ سکیں گے اور کسی بھی `*.ipynb` فائل پر جا سکیں گے۔ مثلاً، `08-building-search-applications/python/oai-solution.ipynb`۔

### کنٹینر میں چلانا

اپنے کمپیوٹر یا Codespace پر سب کچھ سیٹ اپ کرنے کا ایک متبادل طریقہ [کنٹینر](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) استعمال کرنا ہے۔ کورس ریپوزٹری میں موجود خاص `.devcontainer` فولڈر VS Code کو پروجیکٹ کو کنٹینر کے اندر سیٹ اپ کرنے کی سہولت دیتا ہے۔ Codespaces کے علاوہ، اس کے لیے Docker انسٹال کرنا پڑے گا، اور یہ تھوڑا پیچیدہ کام ہے، اس لیے ہم اسے صرف ان لوگوں کو تجویز کرتے ہیں جنہیں کنٹینرز کے ساتھ کام کرنے کا تجربہ ہو۔

GitHub Codespaces استعمال کرتے ہوئے اپنے API کیز کو محفوظ رکھنے کا ایک بہترین طریقہ Codespace Secrets کا استعمال ہے۔ اس بارے میں مزید جاننے کے لیے [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) گائیڈ پر عمل کریں۔

## اسباق اور تکنیکی ضروریات

کورس میں 6 تصوراتی اسباق اور 6 کوڈنگ اسباق شامل ہیں۔

کوڈنگ اسباق کے لیے، ہم Azure OpenAI Service استعمال کر رہے ہیں۔ آپ کو Azure OpenAI سروس تک رسائی اور API کی ضرورت ہوگی تاکہ یہ کوڈ چلایا جا سکے۔ آپ [یہ درخواست مکمل کر کے](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) رسائی حاصل کر سکتے ہیں۔

جب تک آپ کی درخواست پر کارروائی ہو رہی ہو، ہر کوڈنگ سبق میں ایک `README.md` فائل بھی شامل ہوتی ہے جہاں آپ کوڈ اور آؤٹ پٹ دیکھ سکتے ہیں۔

## پہلی بار Azure OpenAI Service استعمال کرنا

اگر آپ پہلی بار Azure OpenAI سروس استعمال کر رہے ہیں، تو براہ کرم اس گائیڈ پر عمل کریں کہ کیسے [Azure OpenAI Service resource بنائیں اور تعینات کریں۔](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## پہلی بار OpenAI API استعمال کرنا

اگر آپ پہلی بار OpenAI API استعمال کر رہے ہیں، تو براہ کرم اس گائیڈ پر عمل کریں کہ کیسے [انٹرفیس بنائیں اور استعمال کریں۔](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## دوسرے سیکھنے والوں سے ملیں

ہم نے اپنے سرکاری [AI Community Discord سرور](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) میں دوسرے سیکھنے والوں سے ملنے کے لیے چینلز بنائے ہیں۔ یہ دوسرے ہم خیال کاروباری افراد، تخلیق کاروں، طلباء، اور Generative AI میں مہارت حاصل کرنے کے خواہشمند افراد کے ساتھ نیٹ ورک بنانے کا بہترین ذریعہ ہے۔

[![ڈسکارڈ چینل میں شامل ہوں](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

پروجیکٹ ٹیم بھی اس Discord سرور پر موجود ہوگی تاکہ کسی بھی سیکھنے والے کی مدد کر سکے۔

## تعاون کریں

یہ کورس ایک اوپن سورس اقدام ہے۔ اگر آپ بہتری کے مواقع یا مسائل دیکھیں، تو براہ کرم [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) بنائیں یا [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) رپورٹ کریں۔

پروجیکٹ ٹیم تمام تعاون کو ٹریک کرے گی۔ اوپن سورس میں تعاون کرنا Generative AI میں اپنے کیریئر کو بنانے کا ایک شاندار طریقہ ہے۔

زیادہ تر تعاون کے لیے آپ کو Contributor License Agreement (CLA) سے اتفاق کرنا ہوگا، جس میں آپ یہ اعلان کرتے ہیں کہ آپ کے پاس اپنے تعاون کے حقوق دینے کا حق ہے اور آپ واقعی یہ حقوق دیتے ہیں۔ تفصیلات کے لیے [CLA, Contributor License Agreement ویب سائٹ](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) دیکھیں۔

اہم: اس ریپو میں متن کا ترجمہ کرتے وقت، براہ کرم مشین ترجمہ استعمال نہ کریں۔ ہم ترجموں کی کمیونٹی کے ذریعے تصدیق کریں گے، اس لیے صرف ان زبانوں میں ترجمہ کے لیے رضاکار بنیں جن میں آپ ماہر ہوں۔

جب آپ pull request جمع کرائیں گے، تو CLA-bot خود بخود فیصلہ کرے گا کہ آیا آپ کو CLA فراہم کرنا ہے اور PR کو مناسب طریقے سے لیبل یا کمنٹ کرے گا۔ بس بوٹ کی ہدایات پر عمل کریں۔ آپ کو یہ صرف ایک بار تمام ریپوزٹریز میں کرنا ہوگا جو ہمارے CLA استعمال کرتی ہیں۔

اس پروجیکٹ نے [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) اپنایا ہے۔ مزید معلومات کے لیے Code of Conduct FAQ پڑھیں یا کسی اضافی سوال یا تبصرے کے لیے [Email opencode](opencode@microsoft.com) سے رابطہ کریں۔

## چلیں شروع کرتے ہیں

اب جب کہ آپ نے اس کورس کو مکمل کرنے کے لیے ضروری مراحل پورے کر لیے ہیں، تو چلیں شروع کرتے ہیں اور [Generative AI اور LLMs کا تعارف](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) حاصل کرتے ہیں۔

**دستخطی نوٹ**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کے ذریعے ترجمہ کی گئی ہے۔ اگرچہ ہم درستگی کے لیے کوشاں ہیں، براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا عدم درستیاں ہو سکتی ہیں۔ اصل دستاویز اپنی مادری زبان میں معتبر ماخذ سمجھی جانی چاہیے۔ اہم معلومات کے لیے پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کی ذمہ داری ہم پر عائد نہیں ہوتی۔