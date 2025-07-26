<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T06:59:34+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "ar"
}
-->
# البدء مع هذه الدورة

نحن متحمسون جدًا لبدء هذه الدورة ورؤية ما ستلهمك لبنائه باستخدام الذكاء الاصطناعي التوليدي!

لضمان نجاحك، توضح هذه الصفحة خطوات الإعداد، والمتطلبات التقنية، وأين يمكنك الحصول على المساعدة إذا لزم الأمر.

## خطوات الإعداد

لبدء هذه الدورة، ستحتاج إلى إكمال الخطوات التالية.

### 1. استنساخ هذا المستودع

[قم باستنساخ هذا المستودع بالكامل](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) إلى حساب GitHub الخاص بك لتتمكن من تعديل أي كود وإكمال التحديات. يمكنك أيضًا [وضع علامة (🌟) على هذا المستودع](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) لتسهيل العثور عليه وعلى المستودعات ذات الصلة.

### 2. إنشاء مساحة أكواد (codespace)

لتجنب أي مشاكل في التبعيات عند تشغيل الكود، نوصي بتشغيل هذه الدورة في [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

يمكنك إنشاء ذلك عن طريق اختيار خيار `Code` على نسختك المستنسخة من هذا المستودع ثم اختيار خيار **Codespaces**.

![مربع حوار يظهر أزرار لإنشاء مساحة أكواد](../../../00-course-setup/images/who-will-pay.webp)

### 3. تخزين مفاتيح API الخاصة بك

من المهم الحفاظ على مفاتيح API الخاصة بك آمنة عند بناء أي نوع من التطبيقات. نوصي بعدم تخزين أي مفاتيح API مباشرة في الكود الخاص بك. قد يؤدي حفظ هذه التفاصيل في مستودع عام إلى مشاكل أمنية وحتى تكاليف غير مرغوب فيها إذا استُخدمت من قبل جهة خبيثة.

إليك دليل خطوة بخطوة حول كيفية إنشاء ملف `.env` للبايثون وإضافة `GITHUB_TOKEN`:

1. **انتقل إلى مجلد مشروعك**: افتح الطرفية أو موجه الأوامر وانتقل إلى المجلد الجذري لمشروعك حيث تريد إنشاء ملف `.env`.

   ```bash
   cd path/to/your/project
   ```

2. **إنشاء ملف `.env`**: استخدم محرر النصوص المفضل لديك لإنشاء ملف جديد باسم `.env`. إذا كنت تستخدم سطر الأوامر، يمكنك استخدام `touch` (في أنظمة يونكس) أو `echo` (في ويندوز):

   أنظمة يونكس:

   ```bash
   touch .env
   ```

   ويندوز:

   ```cmd
   echo . > .env
   ```

3. **تحرير ملف `.env`**: افتح ملف `.env` في محرر نصوص (مثل VS Code، Notepad++، أو أي محرر آخر). أضف السطر التالي إلى الملف، مع استبدال `your_github_token_here` برمز GitHub الخاص بك:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **حفظ الملف**: احفظ التغييرات وأغلق محرر النصوص.

5. **تثبيت `python-dotenv`**: إذا لم تكن قد قمت بذلك مسبقًا، ستحتاج إلى تثبيت حزمة `python-dotenv` لتحميل متغيرات البيئة من ملف `.env` إلى تطبيق البايثون الخاص بك. يمكنك تثبيتها باستخدام `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **تحميل متغيرات البيئة في سكريبت البايثون الخاص بك**: في سكريبت البايثون، استخدم حزمة `python-dotenv` لتحميل متغيرات البيئة من ملف `.env`:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

هذا كل شيء! لقد أنشأت ملف `.env` بنجاح، وأضفت رمز GitHub الخاص بك، وقمت بتحميله في تطبيق البايثون الخاص بك.

## كيفية التشغيل محليًا على جهازك

لتشغيل الكود محليًا على جهازك، ستحتاج إلى تثبيت نسخة من [Python](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

بعد ذلك، لاستخدام المستودع، تحتاج إلى نسخه (clone):

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

بمجرد أن يكون كل شيء جاهزًا، يمكنك البدء!

## خطوات اختيارية

### تثبيت Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) هو مثبت خفيف لتثبيت [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst)، والبايثون، وبعض الحزم الأخرى.

Conda هو مدير حزم يسهل إعداد والتبديل بين بيئات بايثون [افتراضية](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) مختلفة والحزم. كما أنه مفيد لتثبيت الحزم التي لا تتوفر عبر `pip`.

يمكنك اتباع [دليل تثبيت MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) لإعداده.

بعد تثبيت Miniconda، تحتاج إلى استنساخ [المستودع](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (إذا لم تكن قد فعلت ذلك مسبقًا).

بعدها، تحتاج إلى إنشاء بيئة افتراضية. للقيام بذلك باستخدام Conda، قم بإنشاء ملف بيئة جديد (_environment.yml_). إذا كنت تستخدم Codespaces، أنشئ هذا الملف داخل مجلد `.devcontainer`، أي `.devcontainer/environment.yml`.

قم بملء ملف البيئة بالمقتطف التالي:

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

إذا واجهت أخطاء عند استخدام conda، يمكنك تثبيت مكتبات Microsoft AI يدويًا باستخدام الأمر التالي في الطرفية.

```
conda install -c microsoft azure-ai-ml
```

يحدد ملف البيئة التبعيات التي نحتاجها. `<environment-name>` يشير إلى الاسم الذي ترغب في استخدامه لبيئة Conda الخاصة بك، و `<python-version>` هو إصدار البايثون الذي تريد استخدامه، على سبيل المثال، `3` هو أحدث إصدار رئيسي من بايثون.

بعد ذلك، يمكنك إنشاء بيئة Conda الخاصة بك عن طريق تشغيل الأوامر التالية في سطر الأوامر/الطرفية:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

راجع [دليل بيئات Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) إذا واجهت أي مشاكل.

### استخدام Visual Studio Code مع امتداد دعم بايثون

نوصي باستخدام محرر [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) مع تثبيت [امتداد دعم بايثون](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) لهذه الدورة. مع ذلك، هذا مجرد توصية وليس شرطًا إلزاميًا.

> **ملاحظة**: عند فتح مستودع الدورة في VS Code، لديك خيار إعداد المشروع داخل حاوية (container). وذلك بسبب وجود مجلد [خاص `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) داخل المستودع. سنتحدث عن هذا لاحقًا.

> **ملاحظة**: بمجرد استنساخ وفتح المجلد في VS Code، سيقترح عليك تلقائيًا تثبيت امتداد دعم بايثون.

> **ملاحظة**: إذا اقترح VS Code إعادة فتح المستودع داخل حاوية، يمكنك رفض هذا الطلب لاستخدام نسخة بايثون المثبتة محليًا.

### استخدام Jupyter في المتصفح

يمكنك أيضًا العمل على المشروع باستخدام بيئة [Jupyter](https://jupyter.org?WT.mc_id=academic-105485-koreyst) مباشرة من متصفحك. توفر كل من Jupyter الكلاسيكي و[Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) بيئة تطوير مريحة مع ميزات مثل الإكمال التلقائي، تمييز الكود، وغيرها.

لتشغيل Jupyter محليًا، توجه إلى الطرفية/موجه الأوامر، انتقل إلى مجلد الدورة، ونفذ:

```bash
jupyter notebook
```

أو

```bash
jupyterhub
```

سيبدأ هذا تشغيل نسخة Jupyter وسيتم عرض عنوان URL للوصول إليها في نافذة سطر الأوامر.

بمجرد الوصول إلى العنوان، يجب أن ترى مخطط الدورة وتتمكن من التنقل إلى أي ملف `*.ipynb`. على سبيل المثال، `08-building-search-applications/python/oai-solution.ipynb`.

### التشغيل داخل حاوية

بديل لإعداد كل شيء على جهازك أو في Codespace هو استخدام [حاوية](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>). يتيح مجلد `.devcontainer` الخاص داخل مستودع الدورة لـ VS Code إعداد المشروع داخل حاوية. خارج Codespaces، سيتطلب هذا تثبيت Docker، وبصراحة، يتطلب بعض الجهد، لذا نوصي بهذا فقط لمن لديهم خبرة في العمل مع الحاويات.

واحدة من أفضل الطرق للحفاظ على أمان مفاتيح API الخاصة بك عند استخدام GitHub Codespaces هي استخدام أسرار Codespace. يرجى اتباع دليل [إدارة أسرار Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) لمعرفة المزيد.

## الدروس والمتطلبات التقنية

تتضمن الدورة 6 دروس مفاهيمية و6 دروس برمجية.

بالنسبة للدروس البرمجية، نستخدم خدمة Azure OpenAI. ستحتاج إلى الوصول إلى خدمة Azure OpenAI ومفتاح API لتشغيل هذا الكود. يمكنك التقديم للحصول على الوصول عن طريق [إكمال هذا الطلب](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

أثناء انتظار معالجة طلبك، يتضمن كل درس برمجي أيضًا ملف `README.md` حيث يمكنك عرض الكود والنتائج.

## استخدام خدمة Azure OpenAI لأول مرة

إذا كانت هذه هي المرة الأولى التي تعمل فيها مع خدمة Azure OpenAI، يرجى اتباع هذا الدليل حول كيفية [إنشاء ونشر مورد خدمة Azure OpenAI.](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## استخدام OpenAI API لأول مرة

إذا كانت هذه هي المرة الأولى التي تعمل فيها مع OpenAI API، يرجى اتباع الدليل حول كيفية [إنشاء واستخدام الواجهة.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## التعرف على المتعلمين الآخرين

أنشأنا قنوات في خادم [AI Community Discord الرسمي](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) للقاء المتعلمين الآخرين. هذه طريقة رائعة للتواصل مع رواد أعمال وبناة وطلاب يشاركونك نفس الاهتمام ويرغبون في تطوير مهاراتهم في الذكاء الاصطناعي التوليدي.

[![انضم إلى قناة الديسكورد](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

سيكون فريق المشروع أيضًا متواجدًا على هذا الخادم لمساعدة أي متعلم.

## المساهمة

هذه الدورة هي مبادرة مفتوحة المصدر. إذا لاحظت مجالات لتحسين أو مشاكل، يرجى إنشاء [طلب سحب (Pull Request)](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) أو تسجيل [مشكلة على GitHub](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

سيتابع فريق المشروع جميع المساهمات. المساهمة في المصادر المفتوحة طريقة رائعة لبناء مسيرتك المهنية في الذكاء الاصطناعي التوليدي.

معظم المساهمات تتطلب منك الموافقة على اتفاقية ترخيص المساهم (CLA) التي توضح أنك تملك الحق وأنك تمنحنا الحقوق لاستخدام مساهمتك. لمزيد من التفاصيل، قم بزيارة [موقع اتفاقية ترخيص المساهم (CLA)](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

مهم: عند ترجمة النصوص في هذا المستودع، يرجى التأكد من عدم استخدام الترجمة الآلية. سنقوم بالتحقق من الترجمات عبر المجتمع، لذا يرجى التطوع فقط للترجمات في اللغات التي تجيدها.

عند تقديم طلب سحب، سيقوم CLA-bot تلقائيًا بتحديد ما إذا كنت بحاجة إلى تقديم CLA وتزيين طلب السحب بشكل مناسب (مثل وضع علامة أو تعليق). فقط اتبع التعليمات التي يقدمها الروبوت. ستحتاج إلى القيام بذلك مرة واحدة فقط عبر جميع المستودعات التي تستخدم اتفاقيتنا.

هذا المشروع اعتمد [مدونة قواعد السلوك مفتوحة المصدر من مايكروسوفت](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). لمزيد من المعلومات، اقرأ الأسئلة الشائعة حول مدونة السلوك أو تواصل عبر البريد الإلكتروني [Email opencode](opencode@microsoft.com) لأي أسئلة أو تعليقات إضافية.

## لنبدأ

الآن بعد أن أكملت الخطوات اللازمة لإتمام هذه الدورة، لنبدأ بـ [مقدمة في الذكاء الاصطناعي التوليدي ونماذج اللغة الكبيرة](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**إخلاء المسؤولية**:  
تمت ترجمة هذا المستند باستخدام خدمة الترجمة الآلية [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الموثوق به. للمعلومات الهامة، يُنصح بالاعتماد على الترجمة البشرية المهنية. نحن غير مسؤولين عن أي سوء فهم أو تفسير ناتج عن استخدام هذه الترجمة.