<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:05:11+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "bn"
}
-->
# এই কোর্স শুরু করা

আমরা খুবই উচ্ছ্বসিত যে আপনি এই কোর্স শুরু করতে যাচ্ছেন এবং দেখতে পাবেন কীভাবে Generative AI দিয়ে কিছু অনুপ্রেরণামূলক কিছু তৈরি করা যায়!

আপনার সফলতা নিশ্চিত করতে, এই পৃষ্ঠায় সেটআপের ধাপসমূহ, প্রযুক্তিগত প্রয়োজনীয়তা এবং প্রয়োজনে সাহায্য কোথায় পাবেন তা বর্ণনা করা হয়েছে।

## সেটআপের ধাপসমূহ

এই কোর্স শুরু করার জন্য, আপনাকে নিচের ধাপগুলো সম্পন্ন করতে হবে।

### ১. এই রিপো ফর্ক করুন

[Fork this entire repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) আপনার নিজের GitHub অ্যাকাউন্টে, যাতে আপনি কোড পরিবর্তন করতে এবং চ্যালেঞ্জগুলো সম্পন্ন করতে পারেন। আপনি চাইলে [এই রিপোতে (🌟) স্টার](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) দিতে পারেন, যাতে এটি এবং সম্পর্কিত রিপোগুলো সহজে খুঁজে পান।

### ২. একটি codespace তৈরি করুন

কোড চালানোর সময় কোনো ডিপেন্ডেন্সি সমস্যা এড়াতে, আমরা সুপারিশ করি এই কোর্সটি [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) এ চালানোর।

এটি তৈরি করতে, আপনার ফর্ক করা রিপোর `Code` অপশন নির্বাচন করুন এবং **Codespaces** অপশনটি বেছে নিন।

![Dialog showing buttons to create a codespace](../../../00-course-setup/images/who-will-pay.webp)

### ৩. আপনার API কী সংরক্ষণ

যেকোনো ধরনের অ্যাপ্লিকেশন তৈরি করার সময় আপনার API কী নিরাপদে রাখা খুবই গুরুত্বপূর্ণ। আমরা সুপারিশ করি সরাসরি আপনার কোডে API কী সংরক্ষণ না করতে। পাবলিক রিপোজিটরিতে এই তথ্য কমিট করলে নিরাপত্তা ঝুঁকি এবং অনাকাঙ্ক্ষিত খরচ হতে পারে যদি কেউ খারাপ উদ্দেশ্যে ব্যবহার করে।

Python এর জন্য `.env` ফাইল তৈরি করে `GITHUB_TOKEN` কী যোগ করার ধাপে ধাপে নির্দেশিকা নিচে দেওয়া হলো:

1. **আপনার প্রজেক্ট ডিরেক্টরিতে যান**: টার্মিনাল বা কমান্ড প্রম্পট খুলে আপনার প্রজেক্টের মূল ডিরেক্টরিতে যান যেখানে `.env` ফাইল তৈরি করতে চান।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` ফাইল তৈরি করুন**: আপনার পছন্দের টেক্সট এডিটর ব্যবহার করে `.env` নামে একটি নতুন ফাইল তৈরি করুন। কমান্ড লাইন ব্যবহার করলে Unix-ভিত্তিক সিস্টেমে `touch` অথবা Windows-এ `echo` ব্যবহার করতে পারেন:

   Unix-ভিত্তিক সিস্টেম:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **`.env` ফাইল সম্পাদনা করুন**: `.env` ফাইলটি একটি টেক্সট এডিটরে (যেমন VS Code, Notepad++, বা অন্য যেকোনো এডিটর) খুলুন। নিচের লাইনটি যোগ করুন, যেখানে `your_github_token_here` এর জায়গায় আপনার আসল GitHub টোকেন বসান:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **ফাইলটি সংরক্ষণ করুন**: পরিবর্তনগুলো সেভ করে এডিটর বন্ধ করুন।

5. **`python-dotenv` ইনস্টল করুন**: যদি আগে না করে থাকেন, তাহলে `.env` ফাইল থেকে পরিবেশ ভেরিয়েবল লোড করার জন্য `python-dotenv` প্যাকেজ ইনস্টল করতে হবে। `pip` ব্যবহার করে ইনস্টল করতে পারেন:

   ```bash
   pip install python-dotenv
   ```

6. **আপনার Python স্ক্রিপ্টে পরিবেশ ভেরিয়েবল লোড করুন**: আপনার Python স্ক্রিপ্টে `python-dotenv` প্যাকেজ ব্যবহার করে `.env` ফাইল থেকে পরিবেশ ভেরিয়েবল লোড করুন:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

এতটুকুই! আপনি সফলভাবে `.env` ফাইল তৈরি করেছেন, আপনার GitHub টোকেন যোগ করেছেন এবং এটি Python অ্যাপ্লিকেশনে লোড করেছেন।

## আপনার কম্পিউটারে লোকালি কোড চালানো

আপনার কম্পিউটারে কোড লোকালি চালানোর জন্য, আপনার কাছে [Python এর কোনো একটি সংস্করণ ইনস্টল থাকা](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst) প্রয়োজন।

তারপর রিপোজিটরি ব্যবহার করতে, আপনাকে এটি ক্লোন করতে হবে:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

সবকিছু ঠিকঠাক ক্লোন হয়ে গেলে, আপনি শুরু করতে পারেন!

## ঐচ্ছিক ধাপসমূহ

### Miniconda ইনস্টল করা

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) হলো একটি হালকা ইনস্টলার যা [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python এবং কিছু প্যাকেজ ইনস্টল করার জন্য ব্যবহৃত হয়। Conda নিজেই একটি প্যাকেজ ম্যানেজার, যা বিভিন্ন Python [**ভার্চুয়াল এনভায়রনমেন্ট**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) এবং প্যাকেজ সেটআপ ও পরিবর্তন সহজ করে। এটি এমন প্যাকেজ ইনস্টল করতেও সাহায্য করে যা `pip` দিয়ে পাওয়া যায় না।

আপনি [MiniConda ইনস্টলেশন গাইড](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) অনুসরণ করে এটি সেটআপ করতে পারেন।

Miniconda ইনস্টল করার পর, আপনাকে রিপোজিটরি ক্লোন করতে হবে (যদি আগে না করে থাকেন)।

এরপর, একটি ভার্চুয়াল এনভায়রনমেন্ট তৈরি করতে হবে। Conda দিয়ে এটি করতে, একটি নতুন এনভায়রনমেন্ট ফাইল (_environment.yml_) তৈরি করুন। Codespaces ব্যবহার করলে এটি `.devcontainer` ডিরেক্টরির মধ্যে তৈরি করুন, অর্থাৎ `.devcontainer/environment.yml`।

নিচের স্নিপেট দিয়ে আপনার এনভায়রনমেন্ট ফাইল পূরণ করুন:

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

যদি Conda ব্যবহার করতে গিয়ে কোনো সমস্যা হয়, তাহলে ম্যানুয়ালি Microsoft AI Libraries ইনস্টল করতে পারেন নিচের কমান্ড দিয়ে:

```
conda install -c microsoft azure-ai-ml
```

এনভায়রনমেন্ট ফাইলটি আমাদের প্রয়োজনীয় ডিপেন্ডেন্সিগুলো নির্দিষ্ট করে। `<environment-name>` হলো আপনার পছন্দের Conda এনভায়রনমেন্টের নাম, আর `<python-version>` হলো আপনি যে Python সংস্করণ ব্যবহার করতে চান, যেমন `3` হলো Python এর সর্বশেষ প্রধান সংস্করণ।

সবকিছু ঠিকঠাক হলে, নিচের কমান্ডগুলো চালিয়ে আপনার Conda এনভায়রনমেন্ট তৈরি করুন:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

যদি কোনো সমস্যা হয়, [Conda এনভায়রনমেন্ট গাইড](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) দেখুন।

### Visual Studio Code এবং Python সাপোর্ট এক্সটেনশন ব্যবহার

আমরা এই কোর্সের জন্য [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) এডিটর এবং [Python সাপোর্ট এক্সটেনশন](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) ব্যবহার করার পরামর্শ দিই। তবে এটি বাধ্যতামূলক নয়, শুধুমাত্র সুপারিশ।

> **Note**: কোর্স রিপোজিটরি VS Code এ খুললে, আপনি প্রজেক্টটি একটি কন্টেইনারের মধ্যে সেটআপ করার অপশন পাবেন। কারণ কোর্স রিপোজিটরির মধ্যে একটি [বিশেষ `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) ডিরেক্টরি রয়েছে। পরে এ বিষয়ে আরও জানানো হবে।

> **Note**: রিপোজিটরি ক্লোন করে VS Code এ খুললে, এটি স্বয়ংক্রিয়ভাবে Python সাপোর্ট এক্সটেনশন ইনস্টল করার প্রস্তাব দেবে।

> **Note**: যদি VS Code আপনাকে রিপোজিটরি কন্টেইনারে পুনরায় খুলতে বলে, তাহলে এই অনুরোধটি প্রত্যাখ্যান করুন যাতে আপনি লোকালি ইনস্টল করা Python ব্যবহার করতে পারেন।

### ব্রাউজারে Jupyter ব্যবহার

আপনি ব্রাউজারের মধ্যেই [Jupyter পরিবেশ](https://jupyter.org?WT.mc_id=academic-105485-koreyst) ব্যবহার করে প্রজেক্টে কাজ করতে পারেন। ক্লাসিক Jupyter এবং [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) উভয়ই স্বয়ংসম্পূর্ণ উন্নয়ন পরিবেশ দেয়, যেমন অটো-কমপ্লিশন, কোড হাইলাইটিং ইত্যাদি।

লোকালি Jupyter চালু করতে, টার্মিনাল/কমান্ড লাইন থেকে কোর্স ডিরেক্টরিতে যান এবং চালান:

```bash
jupyter notebook
```

অথবা

```bash
jupyterhub
```

এটি একটি Jupyter ইনস্ট্যান্স শুরু করবে এবং অ্যাক্সেসের জন্য URL কমান্ড লাইন উইন্ডোতে দেখাবে।

URL অ্যাক্সেস করলে, আপনি কোর্সের আউটলাইন দেখতে পাবেন এবং যেকোনো `*.ipynb` ফাইলে যেতে পারবেন। উদাহরণস্বরূপ, `08-building-search-applications/python/oai-solution.ipynb`।

### কন্টেইনারে চালানো

আপনার কম্পিউটার বা Codespace এ সবকিছু সেটআপ করার বিকল্প হিসেবে [কন্টেইনার](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) ব্যবহার করা যেতে পারে। কোর্স রিপোজিটরির বিশেষ `.devcontainer` ফোল্ডারটি VS Code কে প্রজেক্টটি কন্টেইনারের মধ্যে সেটআপ করার সুযোগ দেয়। Codespaces ছাড়া এটি করতে হলে Docker ইনস্টল করতে হবে, এবং এটি কিছুটা জটিল, তাই আমরা কেবল কন্টেইনার নিয়ে কাজের অভিজ্ঞতা থাকা লোকদের জন্য এটি সুপারিশ করি।

GitHub Codespaces ব্যবহার করার সময় আপনার API কী নিরাপদ রাখার অন্যতম সেরা উপায় হলো Codespace Secrets ব্যবহার করা। বিস্তারিত জানতে [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) গাইডটি অনুসরণ করুন।

## পাঠ এবং প্রযুক্তিগত প্রয়োজনীয়তা

কোর্সটিতে ৬টি ধারণাগত পাঠ এবং ৬টি কোডিং পাঠ রয়েছে।

কোডিং পাঠগুলোর জন্য আমরা Azure OpenAI Service ব্যবহার করছি। এই কোড চালানোর জন্য আপনার Azure OpenAI সার্ভিসে অ্যাক্সেস এবং API কী প্রয়োজন। অ্যাক্সেস পেতে [এই আবেদনটি পূরণ](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) করতে পারেন।

আপনার আবেদন প্রক্রিয়াধীন থাকাকালীন, প্রতিটি কোডিং পাঠের সাথে একটি `README.md` ফাইল থাকবে যেখানে আপনি কোড এবং আউটপুট দেখতে পারবেন।

## প্রথমবার Azure OpenAI Service ব্যবহার

যদি এটি আপনার প্রথমবার Azure OpenAI সার্ভিস ব্যবহার করা হয়, তাহলে দয়া করে এই গাইডটি অনুসরণ করুন কিভাবে [Azure OpenAI Service রিসোর্স তৈরি ও ডিপ্লয় করবেন।](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## প্রথমবার OpenAI API ব্যবহার

যদি এটি আপনার প্রথমবার OpenAI API ব্যবহার করা হয়, তাহলে দয়া করে এই গাইডটি অনুসরণ করুন কিভাবে [ইন্টারফেস তৈরি ও ব্যবহার করবেন।](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## অন্যান্য শিক্ষার্থীদের সাথে পরিচিত হন

আমরা আমাদের অফিসিয়াল [AI Community Discord সার্ভারে](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) অন্যান্য শিক্ষার্থীদের সাথে পরিচিত হওয়ার জন্য চ্যানেল তৈরি করেছি। এটি অন্যান্য উদ্যোক্তা, নির্মাতা, ছাত্র এবং Generative AI-তে দক্ষতা বাড়াতে আগ্রহী যেকোনো ব্যক্তির সাথে নেটওয়ার্ক গড়ার একটি চমৎকার সুযোগ।

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

প্রজেক্ট টিমও এই Discord সার্ভারে থাকবে শিক্ষার্থীদের সাহায্য করার জন্য।

## অবদান রাখা

এই কোর্স একটি ওপেন-সোর্স উদ্যোগ। যদি আপনি উন্নতির কোনো দিক বা সমস্যা দেখতে পান, অনুগ্রহ করে একটি [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) তৈরি করুন অথবা একটি [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) লগ করুন।

প্রজেক্ট টিম সব অবদান নজরদারি করবে। ওপেন সোর্সে অবদান রাখা Generative AI-তে আপনার ক্যারিয়ার গড়ার একটি অসাধারণ উপায়।

অধিকাংশ অবদানের জন্য আপনাকে Contributor License Agreement (CLA) এ সম্মত হতে হবে, যা ঘোষণা করে যে আপনি আপনার অবদান ব্যবহারের জন্য আমাদের অধিকার প্রদান করছেন। বিস্তারিত জানতে [CLA, Contributor License Agreement ওয়েবসাইট](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) দেখুন।

গুরুত্বপূর্ণ: এই রিপোতে অনুবাদ করার সময়, দয়া করে মেশিন অনুবাদ ব্যবহার করবেন না। আমরা কমিউনিটির মাধ্যমে অনুবাদ যাচাই করব, তাই শুধুমাত্র আপনি যে ভাষায় দক্ষ, সেই ভাষায় অনুবাদের জন্য স্বেচ্ছাসেবক হোন।

আপনি যখন একটি pull request জমা দেবেন, CLA-বট স্বয়ংক্রিয়ভাবে নির্ধারণ করবে আপনি CLA প্রদান করতে হবে কিনা এবং PR-এ উপযুক্ত লেবেল বা মন্তব্য যোগ করবে। বটের নির্দেশনা অনুসরণ করুন। আপনাকে এটি সমস্ত রিপোজিটরির জন্য একবারই করতে হবে।

এই প্রজেক্ট [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) গ্রহণ করেছে। আরও তথ্যের জন্য Code of Conduct FAQ পড়ুন অথবা অতিরিক্ত প্রশ্ন বা মন্তব্যের জন্য [Email opencode](opencode@microsoft.com) এ যোগাযোগ করুন।

## চলুন শুরু করি

আপনি এখন এই কোর্স সম্পন্ন করার জন্য প্রয়োজনীয় ধাপগুলো শেষ করেছেন, চলুন শুরু করি [Generative AI এবং LLMs এর পরিচিতি](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) নিয়ে।

**অস্বীকৃতি**:  
এই নথিটি AI অনুবাদ সেবা [Co-op Translator](https://github.com/Azure/co-op-translator) ব্যবহার করে অনূদিত হয়েছে। আমরা যথাসাধ্য সঠিকতার চেষ্টা করি, তবে স্বয়ংক্রিয় অনুবাদে ত্রুটি বা অসঙ্গতি থাকতে পারে। মূল নথিটি তার নিজস্ব ভাষায়ই কর্তৃত্বপূর্ণ উৎস হিসেবে বিবেচিত হওয়া উচিত। গুরুত্বপূর্ণ তথ্যের জন্য পেশাদার মানব অনুবাদ গ্রহণ করার পরামর্শ দেওয়া হয়। এই অনুবাদের ব্যবহারে সৃষ্ট কোনো ভুল বোঝাবুঝি বা ভুল ব্যাখ্যার জন্য আমরা দায়ী নই।