<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:04:45+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "hi"
}
-->
# इस कोर्स के साथ शुरुआत करना

हम आपके इस कोर्स को शुरू करने और जनरेटिव AI के साथ आप क्या बना सकते हैं, यह देखने के लिए बहुत उत्साहित हैं!

आपकी सफलता सुनिश्चित करने के लिए, इस पेज पर सेटअप के चरण, तकनीकी आवश्यकताएं, और मदद कहां मिलेगी, यह बताया गया है।

## सेटअप के चरण

इस कोर्स को शुरू करने के लिए, आपको निम्नलिखित चरण पूरे करने होंगे।

### 1. इस रिपो को Fork करें

अपने GitHub अकाउंट में [इस पूरे रिपो को Fork करें](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) ताकि आप किसी भी कोड को बदल सकें और चैलेंज पूरे कर सकें। आप इसे और संबंधित रिपोज को आसानी से खोजने के लिए [इस रिपो को स्टार (🌟) भी कर सकते हैं](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst)।

### 2. एक codespace बनाएं

कोड चलाते समय किसी भी निर्भरता की समस्या से बचने के लिए, हम इस कोर्स को [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) में चलाने की सलाह देते हैं।

यह आपके Fork किए गए रिपो में `Code` विकल्प चुनकर और फिर **Codespaces** विकल्प चुनकर बनाया जा सकता है।

![Dialog showing buttons to create a codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. अपने API Keys को सुरक्षित रखें

कोई भी एप्लिकेशन बनाते समय अपने API keys को सुरक्षित रखना बहुत जरूरी है। हम सलाह देते हैं कि API keys को सीधे अपने कोड में न रखें। इन्हें सार्वजनिक रिपोज में कमिट करने से सुरक्षा संबंधी समस्याएं हो सकती हैं और गलत उपयोग से अनचाहे खर्च भी हो सकते हैं।  
यहाँ Python के लिए `.env` फाइल बनाने और `GITHUB_TOKEN` जोड़ने का चरण-दर-चरण तरीका दिया गया है:

1. **अपने प्रोजेक्ट डायरेक्टरी में जाएं**: टर्मिनल या कमांड प्रॉम्प्ट खोलें और उस प्रोजेक्ट की रूट डायरेक्टरी में जाएं जहाँ आप `.env` फाइल बनाना चाहते हैं।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फाइल बनाएं**: अपनी पसंदीदा टेक्स्ट एडिटर से `.env` नाम की नई फाइल बनाएं। कमांड लाइन पर, आप Unix-आधारित सिस्टम पर `touch` या Windows पर `echo` का उपयोग कर सकते हैं:

   Unix-आधारित सिस्टम:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **`.env` फाइल संपादित करें**: `.env` फाइल को किसी टेक्स्ट एडिटर (जैसे VS Code, Notepad++, या कोई अन्य) में खोलें। निम्न लाइन जोड़ें, `your_github_token_here` को अपने असली GitHub टोकन से बदलें:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फाइल सेव करें**: बदलाव सेव करें और टेक्स्ट एडिटर बंद करें।

5. **`python-dotenv` इंस्टॉल करें**: यदि आपने पहले से नहीं किया है, तो आपको `.env` फाइल से पर्यावरण चर (environment variables) लोड करने के लिए `python-dotenv` पैकेज इंस्टॉल करना होगा। इसे `pip` से इंस्टॉल करें:

   ```bash
   pip install python-dotenv
   ```

6. **अपने Python स्क्रिप्ट में पर्यावरण चर लोड करें**: अपने Python स्क्रिप्ट में `python-dotenv` पैकेज का उपयोग करके `.env` फाइल से पर्यावरण चर लोड करें:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

बस! आपने सफलतापूर्वक `.env` फाइल बनाई, अपना GitHub टोकन जोड़ा, और इसे अपने Python एप्लिकेशन में लोड किया।

## अपने कंप्यूटर पर लोकल रूप से कैसे चलाएं

अपने कंप्यूटर पर कोड चलाने के लिए, आपके पास [Python का कोई संस्करण इंस्टॉल होना चाहिए](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)।

फिर रिपोज को क्लोन करने के लिए:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

एक बार सब कुछ सेट हो जाने के बाद, आप शुरू कर सकते हैं!

## वैकल्पिक चरण

### Miniconda इंस्टॉल करना

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) एक हल्का इंस्टॉलर है जो [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, और कुछ पैकेज इंस्टॉल करता है।  
Conda एक पैकेज मैनेजर है, जो विभिन्न Python [**वर्चुअल एनवायरनमेंट्स**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) और पैकेजों के बीच स्विच करना आसान बनाता है। यह उन पैकेजों को इंस्टॉल करने में भी मदद करता है जो `pip` से उपलब्ध नहीं हैं।

इसे सेटअप करने के लिए आप [MiniConda इंस्टॉलेशन गाइड](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) का पालन कर सकते हैं।

Miniconda इंस्टॉल हो जाने के बाद, आपको रिपोज को क्लोन करना होगा (यदि आपने पहले नहीं किया है)।

फिर, आपको एक वर्चुअल एनवायरनमेंट बनाना होगा। Conda के साथ ऐसा करने के लिए, एक नया एनवायरनमेंट फाइल (_environment.yml_) बनाएं। यदि आप Codespaces का उपयोग कर रहे हैं, तो इसे `.devcontainer` डायरेक्टरी के अंदर बनाएं, यानी `.devcontainer/environment.yml`।

अपने एनवायरनमेंट फाइल में नीचे दिया गया स्निपेट डालें:

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

यदि आपको conda का उपयोग करते समय त्रुटियां मिलती हैं, तो आप टर्मिनल में निम्न कमांड से Microsoft AI Libraries मैन्युअली इंस्टॉल कर सकते हैं।

```
conda install -c microsoft azure-ai-ml
```

एनवायरनमेंट फाइल में आवश्यक निर्भरताएं (dependencies) बताई गई हैं। `<environment-name>` वह नाम है जो आप अपने Conda एनवायरनमेंट के लिए रखना चाहते हैं, और `<python-version>` वह Python का संस्करण है जिसे आप उपयोग करना चाहते हैं, उदाहरण के लिए, `3` Python का नवीनतम मुख्य संस्करण है।

इसके बाद, आप नीचे दिए गए कमांड को अपने कमांड लाइन/टर्मिनल में चलाकर Conda एनवायरनमेंट बना सकते हैं:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

यदि आपको कोई समस्या आती है, तो [Conda एनवायरनमेंट गाइड](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) देखें।

### Python सपोर्ट एक्सटेंशन के साथ Visual Studio Code का उपयोग करना

हम इस कोर्स के लिए [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटर का उपयोग करने की सलाह देते हैं, जिसमें [Python सपोर्ट एक्सटेंशन](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) इंस्टॉल हो। यह एक सुझाव है, अनिवार्य नहीं।

> **Note**: जब आप कोर्स रिपोज को VS Code में खोलते हैं, तो आपके पास प्रोजेक्ट को कंटेनर के अंदर सेटअप करने का विकल्प होता है। ऐसा इसलिए क्योंकि कोर्स रिपोज में [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) डायरेक्टरी होती है। इसके बारे में बाद में और जानकारी मिलेगी।

> **Note**: जब आप रिपोज को क्लोन करके VS Code में खोलते हैं, तो यह अपने आप Python सपोर्ट एक्सटेंशन इंस्टॉल करने का सुझाव देगा।

> **Note**: यदि VS Code आपको रिपोज को कंटेनर में फिर से खोलने का सुझाव देता है, तो इसे अस्वीकार करें ताकि आप लोकल इंस्टॉल किए गए Python का उपयोग कर सकें।

### ब्राउज़र में Jupyter का उपयोग करना

आप प्रोजेक्ट पर [Jupyter वातावरण](https://jupyter.org?WT.mc_id=academic-105485-koreyst) का उपयोग करके सीधे अपने ब्राउज़र में भी काम कर सकते हैं। क्लासिक Jupyter और [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) दोनों एक अच्छा विकास वातावरण प्रदान करते हैं, जिसमें ऑटो-कंप्लीशन, कोड हाइलाइटिंग जैसी सुविधाएं होती हैं।

लोकल Jupyter शुरू करने के लिए, टर्मिनल/कमांड लाइन खोलें, कोर्स डायरेक्टरी में जाएं, और निम्न कमांड चलाएं:

```bash
jupyter notebook
```

या

```bash
jupyterhub
```

यह एक Jupyter इंस्टेंस शुरू करेगा और कमांड लाइन विंडो में इसे एक्सेस करने के लिए URL दिखाएगा।

URL पर पहुँचने के बाद, आप कोर्स का आउटलाइन देख पाएंगे और किसी भी `*.ipynb` फाइल पर नेविगेट कर सकेंगे। उदाहरण के लिए, `08-building-search-applications/python/oai-solution.ipynb`।

### कंटेनर में चलाना

अपने कंप्यूटर या Codespace पर सब कुछ सेटअप करने के विकल्प के रूप में, आप [कंटेनर](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) का उपयोग कर सकते हैं। कोर्स रिपोज में विशेष `.devcontainer` फोल्डर VS Code को प्रोजेक्ट को कंटेनर के अंदर सेटअप करने की अनुमति देता है। Codespaces के बाहर, इसके लिए Docker इंस्टॉल करना होगा, और यह थोड़ा जटिल हो सकता है, इसलिए हम इसे केवल कंटेनर के साथ काम करने का अनुभव रखने वालों को ही सुझाते हैं।

GitHub Codespaces का उपयोग करते समय अपने API keys को सुरक्षित रखने के लिए Codespace Secrets का उपयोग करना सबसे अच्छा तरीका है। कृपया [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) गाइड का पालन करें।

## पाठ और तकनीकी आवश्यकताएं

कोर्स में 6 कॉन्सेप्ट लेसन और 6 कोडिंग लेसन हैं।

कोडिंग लेसन के लिए, हम Azure OpenAI Service का उपयोग कर रहे हैं। इस कोड को चलाने के लिए आपको Azure OpenAI सेवा और API key की आवश्यकता होगी। आप [इस आवेदन को पूरा करके](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) एक्सेस के लिए आवेदन कर सकते हैं।

जब तक आपका आवेदन प्रक्रिया में है, प्रत्येक कोडिंग लेसन में एक `README.md` फाइल भी होती है जहाँ आप कोड और आउटपुट देख सकते हैं।

## पहली बार Azure OpenAI Service का उपयोग करना

यदि आप पहली बार Azure OpenAI सेवा का उपयोग कर रहे हैं, तो कृपया इस गाइड का पालन करें कि कैसे [Azure OpenAI Service रिसोर्स बनाएं और डिप्लॉय करें।](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## पहली बार OpenAI API का उपयोग करना

यदि आप पहली बार OpenAI API का उपयोग कर रहे हैं, तो कृपया इस गाइड का पालन करें कि कैसे [इंटरफेस बनाएं और उपयोग करें।](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## अन्य शिक्षार्थियों से मिलें

हमने अपने आधिकारिक [AI Community Discord सर्वर](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) में अन्य शिक्षार्थियों से मिलने के लिए चैनल बनाए हैं। यह समान विचारधारा वाले उद्यमियों, बिल्डर्स, छात्रों, और जनरेटिव AI में आगे बढ़ने के इच्छुक लोगों के साथ नेटवर्क बनाने का एक शानदार तरीका है।

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

प्रोजेक्ट टीम भी इस Discord सर्वर पर मौजूद रहेगी ताकि किसी भी शिक्षार्थी की मदद कर सके।

## योगदान करें

यह कोर्स एक ओपन-सोर्स पहल है। यदि आप सुधार के क्षेत्र या समस्याएं देखें, तो कृपया [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) बनाएं या [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) दर्ज करें।

प्रोजेक्ट टीम सभी योगदानों को ट्रैक करेगी। ओपन सोर्स में योगदान करना जनरेटिव AI में अपने करियर को बनाने का एक शानदार तरीका है।

अधिकांश योगदानों के लिए आपको Contributor License Agreement (CLA) से सहमत होना होगा, जिसमें आप घोषणा करते हैं कि आपके पास अपने योगदान का उपयोग करने के अधिकार हैं। विवरण के लिए [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) देखें।

महत्वपूर्ण: इस रिपो में टेक्स्ट का अनुवाद करते समय कृपया मशीन अनुवाद का उपयोग न करें। हम समुदाय के माध्यम से अनुवादों की जांच करेंगे, इसलिए केवल उन भाषाओं में अनुवाद के लिए स्वयंसेवा करें जिनमें आप प्रवीण हैं।

जब आप एक पुल रिक्वेस्ट सबमिट करते हैं, तो CLA-बॉट स्वचालित रूप से निर्धारित करेगा कि आपको CLA प्रदान करने की आवश्यकता है या नहीं और PR को उपयुक्त रूप से लेबल या टिप्पणी करेगा। बस बॉट द्वारा दिए गए निर्देशों का पालन करें। आपको यह केवल एक बार सभी रिपोज में करना होगा जो हमारे CLA का उपयोग करते हैं।

इस प्रोजेक्ट ने [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) को अपनाया है। अधिक जानकारी के लिए Code of Conduct FAQ पढ़ें या किसी भी अतिरिक्त प्रश्न या टिप्पणियों के लिए [Email opencode](opencode@microsoft.com) से संपर्क करें।

## चलिए शुरू करते हैं

अब जब आपने इस कोर्स को पूरा करने के लिए आवश्यक चरण पूरे कर लिए हैं, तो चलिए [जनरेटिव AI और LLMs का परिचय](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) लेकर शुरू करते हैं।

**अस्वीकरण**:  
यह दस्तावेज़ AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) का उपयोग करके अनुवादित किया गया है। जबकि हम सटीकता के लिए प्रयासरत हैं, कृपया ध्यान दें कि स्वचालित अनुवादों में त्रुटियाँ या अशुद्धियाँ हो सकती हैं। मूल दस्तावेज़ अपनी मूल भाषा में ही अधिकारिक स्रोत माना जाना चाहिए। महत्वपूर्ण जानकारी के लिए, पेशेवर मानव अनुवाद की सलाह दी जाती है। इस अनुवाद के उपयोग से उत्पन्न किसी भी गलतफहमी या गलत व्याख्या के लिए हम जिम्मेदार नहीं हैं।