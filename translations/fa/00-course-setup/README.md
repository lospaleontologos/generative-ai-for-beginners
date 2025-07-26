<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:00:00+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "fa"
}
-->
# شروع کار با این دوره

ما بسیار هیجان‌زده‌ایم که شما این دوره را شروع کنید و ببینید با هوش مصنوعی مولد چه چیزهایی می‌توانید بسازید!

برای اطمینان از موفقیت شما، این صفحه مراحل راه‌اندازی، نیازمندی‌های فنی و محل دریافت کمک در صورت نیاز را توضیح می‌دهد.

## مراحل راه‌اندازی

برای شروع این دوره، باید مراحل زیر را انجام دهید.

### ۱. فورک کردن این مخزن

[این مخزن را به‌طور کامل فورک کنید](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) به حساب GitHub خود تا بتوانید هر کدی را تغییر دهید و چالش‌ها را کامل کنید. همچنین می‌توانید [این مخزن را ستاره‌دار (🌟) کنید](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) تا راحت‌تر آن و مخازن مرتبط را پیدا کنید.

### ۲. ایجاد یک codespace

برای جلوگیری از مشکلات وابستگی هنگام اجرای کد، توصیه می‌کنیم این دوره را در [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) اجرا کنید.

این کار با انتخاب گزینه `Code` در نسخه فورک شده مخزن شما و سپس انتخاب گزینه **Codespaces** قابل انجام است.

![پنجره‌ای که دکمه‌های ایجاد codespace را نشان می‌دهد](../../../00-course-setup/images/who-will-pay.webp)

### ۳. ذخیره کلیدهای API شما

حفظ امنیت کلیدهای API هنگام ساخت هر نوع برنامه‌ای اهمیت زیادی دارد. توصیه می‌کنیم کلیدهای API را مستقیماً در کد خود ذخیره نکنید. ثبت این اطلاعات در یک مخزن عمومی می‌تواند منجر به مشکلات امنیتی و حتی هزینه‌های ناخواسته در صورت سوءاستفاده شود.

در اینجا راهنمای گام‌به‌گام برای ایجاد فایل `.env` در پایتون و افزودن `GITHUB_TOKEN` آمده است:

1. **رفتن به دایرکتوری پروژه**: ترمینال یا خط فرمان خود را باز کنید و به دایرکتوری ریشه پروژه‌ای که می‌خواهید فایل `.env` را در آن بسازید، بروید.

   ```bash
   cd path/to/your/project
   ```

2. **ایجاد فایل `.env`**: با ویرایشگر متن مورد علاقه خود، یک فایل جدید به نام `.env` بسازید. اگر از خط فرمان استفاده می‌کنید، می‌توانید از دستور `touch` (در سیستم‌های مبتنی بر یونیکس) یا `echo` (در ویندوز) استفاده کنید:

   سیستم‌های مبتنی بر یونیکس:

   ```bash
   touch .env
   ```

   ویندوز:

   ```cmd
   echo . > .env
   ```

3. **ویرایش فایل `.env`**: فایل `.env` را در یک ویرایشگر متن (مثلاً VS Code، Notepad++ یا هر ویرایشگر دیگر) باز کنید. خط زیر را اضافه کنید و `your_github_token_here` را با توکن واقعی GitHub خود جایگزین کنید:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **ذخیره فایل**: تغییرات را ذخیره کرده و ویرایشگر را ببندید.

5. **نصب `python-dotenv`**: اگر قبلاً نصب نکرده‌اید، باید بسته `python-dotenv` را نصب کنید تا متغیرهای محیطی را از فایل `.env` در برنامه پایتون خود بارگذاری کنید. می‌توانید با استفاده از `pip` آن را نصب کنید:

   ```bash
   pip install python-dotenv
   ```

6. **بارگذاری متغیرهای محیطی در اسکریپت پایتون**: در اسکریپت پایتون خود، از بسته `python-dotenv` برای بارگذاری متغیرهای محیطی از فایل `.env` استفاده کنید:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

همین! شما با موفقیت فایل `.env` را ایجاد کرده، توکن GitHub خود را اضافه کرده و آن را در برنامه پایتون خود بارگذاری کرده‌اید.

## نحوه اجرای کد به صورت محلی روی کامپیوتر شما

برای اجرای کد به صورت محلی روی کامپیوتر خود، باید نسخه‌ای از [پایتون را نصب کرده باشید](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

سپس برای استفاده از مخزن، باید آن را کلون کنید:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

وقتی همه چیز آماده شد، می‌توانید شروع کنید!

## مراحل اختیاری

### نصب Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) یک نصب‌کننده سبک برای نصب [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst)، پایتون و چند بسته دیگر است.

Conda خود یک مدیر بسته است که کار راه‌اندازی و جابجایی بین [محیط‌های مجازی](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) و بسته‌های مختلف پایتون را آسان می‌کند. همچنین برای نصب بسته‌هایی که از طریق `pip` در دسترس نیستند، مفید است.

می‌توانید راهنمای نصب [MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) را دنبال کنید.

پس از نصب Miniconda، باید مخزن را کلون کنید (اگر قبلاً این کار را نکرده‌اید).

سپس باید یک محیط مجازی بسازید. برای این کار با Conda، یک فایل محیط جدید (_environment.yml_) ایجاد کنید. اگر از Codespaces استفاده می‌کنید، این فایل را در دایرکتوری `.devcontainer` بسازید، یعنی `.devcontainer/environment.yml`.

فایل محیط خود را با قطعه کد زیر پر کنید:

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

اگر هنگام استفاده از conda با خطا مواجه شدید، می‌توانید کتابخانه‌های AI مایکروسافت را به صورت دستی با دستور زیر در ترمینال نصب کنید.

```
conda install -c microsoft azure-ai-ml
```

فایل محیط وابستگی‌های مورد نیاز ما را مشخص می‌کند. `<environment-name>` نامی است که می‌خواهید برای محیط Conda خود استفاده کنید و `<python-version>` نسخه پایتونی است که می‌خواهید استفاده کنید، مثلاً `3` که آخرین نسخه اصلی پایتون است.

پس از این کار، می‌توانید محیط Conda خود را با اجرای دستورات زیر در خط فرمان/ترمینال بسازید:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

اگر با مشکلی مواجه شدید، به [راهنمای محیط‌های Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) مراجعه کنید.

### استفاده از Visual Studio Code با افزونه پشتیبانی پایتون

توصیه می‌کنیم برای این دوره از ویرایشگر [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) به همراه [افزونه پشتیبانی پایتون](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) استفاده کنید. البته این بیشتر یک توصیه است و الزام قطعی نیست.

> **توجه**: با باز کردن مخزن دوره در VS Code، می‌توانید پروژه را درون یک کانتینر راه‌اندازی کنید. این به دلیل وجود دایرکتوری ویژه [`.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) در مخزن دوره است. بعداً بیشتر درباره این موضوع توضیح داده خواهد شد.

> **توجه**: پس از کلون کردن و باز کردن دایرکتوری در VS Code، به‌طور خودکار پیشنهاد نصب افزونه پشتیبانی پایتون را دریافت خواهید کرد.

> **توجه**: اگر VS Code پیشنهاد داد مخزن را در یک کانتینر باز کنید، این درخواست را رد کنید تا از نسخه پایتون نصب شده به صورت محلی استفاده کنید.

### استفاده از Jupyter در مرورگر

شما همچنین می‌توانید پروژه را با استفاده از محیط [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) مستقیماً در مرورگر خود انجام دهید. هر دو نسخه کلاسیک Jupyter و [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) محیط توسعه بسیار خوبی با امکاناتی مانند تکمیل خودکار، برجسته‌سازی کد و غیره ارائه می‌دهند.

برای شروع Jupyter به صورت محلی، به ترمینال/خط فرمان بروید، به دایرکتوری دوره بروید و دستور زیر را اجرا کنید:

```bash
jupyter notebook
```

یا

```bash
jupyterhub
```

این کار یک نمونه Jupyter را راه‌اندازی می‌کند و آدرس URL دسترسی به آن در پنجره خط فرمان نمایش داده خواهد شد.

وقتی به URL دسترسی پیدا کردید، باید ساختار دوره را ببینید و بتوانید به هر فایل `*.ipynb` دسترسی داشته باشید. برای مثال، `08-building-search-applications/python/oai-solution.ipynb`.

### اجرای پروژه در یک کانتینر

یک جایگزین برای راه‌اندازی همه چیز روی کامپیوتر یا Codespace شما، استفاده از [کانتینر](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) است. پوشه ویژه `.devcontainer` در مخزن دوره این امکان را به VS Code می‌دهد که پروژه را درون یک کانتینر راه‌اندازی کند. خارج از Codespaces، این کار نیاز به نصب Docker دارد و واقعاً کمی پیچیده است، بنابراین این روش را فقط به کسانی که تجربه کار با کانتینرها دارند توصیه می‌کنیم.

یکی از بهترین روش‌ها برای حفظ امنیت کلیدهای API هنگام استفاده از GitHub Codespaces، استفاده از Codespace Secrets است. لطفاً راهنمای [مدیریت اسرار Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) را برای اطلاعات بیشتر دنبال کنید.

## درس‌ها و نیازمندی‌های فنی

این دوره شامل ۶ درس مفهومی و ۶ درس کدنویسی است.

برای درس‌های کدنویسی، از سرویس Azure OpenAI استفاده می‌کنیم. برای اجرای این کد به دسترسی به سرویس Azure OpenAI و یک کلید API نیاز دارید. می‌توانید با [تکمیل این درخواست](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) برای دسترسی اقدام کنید.

در حالی که منتظر پردازش درخواست خود هستید، هر درس کدنویسی همچنین شامل یک فایل `README.md` است که می‌توانید کد و خروجی‌ها را در آن مشاهده کنید.

## استفاده از سرویس Azure OpenAI برای اولین بار

اگر برای اولین بار با سرویس Azure OpenAI کار می‌کنید، لطفاً این راهنما را برای [ایجاد و استقرار یک منبع Azure OpenAI Service](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) دنبال کنید.

## استفاده از API OpenAI برای اولین بار

اگر برای اولین بار با API OpenAI کار می‌کنید، لطفاً راهنمای [ایجاد و استفاده از رابط کاربری](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) را دنبال کنید.

## آشنایی با سایر یادگیرندگان

ما در سرور رسمی [AI Community Discord](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) کانال‌هایی برای آشنایی با سایر یادگیرندگان ایجاد کرده‌ایم. این یک راه عالی برای شبکه‌سازی با کارآفرینان، سازندگان، دانشجویان و هر کسی است که می‌خواهد در هوش مصنوعی مولد پیشرفت کند.

[![عضویت در کانال دیسکورد](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

تیم پروژه نیز در این سرور دیسکورد حضور دارد تا به یادگیرندگان کمک کند.

## مشارکت

این دوره یک پروژه متن‌باز است. اگر نقاط قابل بهبود یا مشکلاتی مشاهده کردید، لطفاً یک [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) ایجاد کنید یا یک [issue در GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) ثبت کنید.

تیم پروژه تمام مشارکت‌ها را پیگیری می‌کند. مشارکت در متن‌باز راهی عالی برای ساختن مسیر شغلی شما در هوش مصنوعی مولد است.

اکثر مشارکت‌ها نیازمند موافقت با قرارداد مجوز مشارکت‌کننده (CLA) هستند که اعلام می‌کند شما حق دارید و واقعاً حقوق استفاده از مشارکت خود را به ما می‌دهید. برای جزئیات بیشتر به [وب‌سایت قرارداد مجوز مشارکت‌کننده (CLA)](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) مراجعه کنید.

مهم: هنگام ترجمه متن در این مخزن، لطفاً از ترجمه ماشینی استفاده نکنید. ما ترجمه‌ها را از طریق جامعه بررسی خواهیم کرد، پس فقط در زبان‌هایی که به آن‌ها مسلط هستید داوطلب ترجمه شوید.

وقتی یک pull request ارسال می‌کنید، ربات CLA به‌طور خودکار تعیین می‌کند که آیا نیاز به ارائه CLA دارید و PR را به‌طور مناسب برچسب‌گذاری یا کامنت‌گذاری می‌کند. فقط کافی است دستورالعمل‌های ربات را دنبال کنید. این کار فقط یک بار برای تمام مخازنی که از CLA ما استفاده می‌کنند لازم است.

این پروژه از [کد رفتار متن‌باز مایکروسافت](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) پیروی می‌کند. برای اطلاعات بیشتر، سوالات متداول کد رفتار را بخوانید یا با [ایمیل opencode](opencode@microsoft.com) تماس بگیرید.

## بیایید شروع کنیم

حالا که مراحل لازم برای تکمیل این دوره را انجام داده‌اید، بیایید با [معرفی هوش مصنوعی مولد و مدل‌های زبانی بزرگ (LLMs)](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) شروع کنیم.

**سلب مسئولیت**:  
این سند با استفاده از سرویس ترجمه هوش مصنوعی [Co-op Translator](https://github.com/Azure/co-op-translator) ترجمه شده است. در حالی که ما در تلاش برای دقت هستیم، لطفاً توجه داشته باشید که ترجمه‌های خودکار ممکن است حاوی خطاها یا نادرستی‌هایی باشند. سند اصلی به زبان بومی خود باید به عنوان منبع معتبر در نظر گرفته شود. برای اطلاعات حیاتی، ترجمه حرفه‌ای انسانی توصیه می‌شود. ما مسئول هیچ گونه سوءتفاهم یا تفسیر نادرستی که از استفاده از این ترجمه ناشی شود، نیستیم.