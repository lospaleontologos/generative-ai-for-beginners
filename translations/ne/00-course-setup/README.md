<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:06:14+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "ne"
}
-->
# यस कोर्ससँग सुरु गर्दै

हामी तपाईंलाई यो कोर्स सुरु गर्न र Generative AI सँग के बनाउन प्रेरित हुनुहुन्छ भनेर हेर्न पाउँदा धेरै उत्साहित छौं!

तपाईंको सफलताको सुनिश्चितताका लागि, यो पृष्ठले सेटअपका चरणहरू, प्राविधिक आवश्यकताहरू, र आवश्यक परेमा सहयोग कहाँ पाउने बारे जानकारी दिन्छ।

## सेटअपका चरणहरू

यो कोर्स लिन सुरु गर्न, तपाईंले तलका चरणहरू पूरा गर्नुपर्नेछ।

### १. यो रिपो फोर्क गर्नुहोस्

[Fork this entire repo](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) आफ्नो GitHub खातामा फोर्क गर्नुहोस् ताकि तपाईं कुनै पनि कोड परिवर्तन गर्न र चुनौतीहरू पूरा गर्न सक्नुहुनेछ। तपाईंले यो रिपोलाई [star (🌟)](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) पनि गर्न सक्नुहुन्छ जसले यसलाई र सम्बन्धित रिपोहरूलाई सजिलै फेला पार्न मद्दत गर्छ।

### २. कोडस्पेस सिर्जना गर्नुहोस्

कोड चलाउँदा कुनै निर्भरता समस्या नआओस् भनेर, हामी यो कोर्स [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) मा चलाउन सिफारिस गर्छौं।

यो तपाईंले फोर्क गरेको रिपोमा `Code` विकल्प छानेर र **Codespaces** विकल्प चयन गरेर सिर्जना गर्न सक्नुहुन्छ।

![Dialog showing buttons to create a codespace](../../../00-course-setup/images/who-will-pay.webp)

### ३. तपाईंका API कुञ्जीहरू सुरक्षित राख्ने

कुनै पनि प्रकारको एप्लिकेशन बनाउँदा तपाईंका API कुञ्जीहरू सुरक्षित राख्नु महत्त्वपूर्ण हुन्छ। हामी सिफारिस गर्छौं कि तपाईंले आफ्नो कोडमा सिधै API कुञ्जीहरू राख्नु हुँदैन। ती विवरणहरू सार्वजनिक रिपोमा कमिट गर्दा सुरक्षा समस्या र खराब उद्देश्यले प्रयोग गर्दा अनावश्यक खर्च हुन सक्छ।

यहाँ Python का लागि `.env` फाइल कसरी बनाउने र `GITHUB_TOKEN` कसरी थप्ने भन्ने चरण-दर-चरण मार्गदर्शन छ:

1. **आफ्नो प्रोजेक्ट डाइरेक्टरीमा जानुहोस्**: टर्मिनल वा कमाण्ड प्रम्प्ट खोल्नुहोस् र आफ्नो प्रोजेक्टको मूल डाइरेक्टरीमा जानुहोस् जहाँ तपाईं `.env` फाइल बनाउन चाहनुहुन्छ।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फाइल बनाउनुहोस्**: आफ्नो मनपर्ने टेक्स्ट एडिटर प्रयोग गरेर `.env` नामको नयाँ फाइल बनाउनुहोस्। कमाण्ड लाइनमा, तपाईं `touch` (Unix आधारित सिस्टममा) वा `echo` (Windows मा) प्रयोग गर्न सक्नुहुन्छ:

   Unix आधारित सिस्टमहरू:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **`.env` फाइल सम्पादन गर्नुहोस्**: `.env` फाइललाई टेक्स्ट एडिटर (जस्तै VS Code, Notepad++, वा अन्य कुनै एडिटर) मा खोल्नुहोस्। तलको लाइन थप्नुहोस्, जहाँ `your_github_token_here` लाई तपाईंको वास्तविक GitHub टोकनले प्रतिस्थापन गर्नुहोस्:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फाइल सुरक्षित गर्नुहोस्**: परिवर्तनहरू सुरक्षित गरी एडिटर बन्द गर्नुहोस्।

5. **`python-dotenv` इन्स्टल गर्नुहोस्**: यदि तपाईंले पहिले इन्स्टल गर्नुभएको छैन भने, `.env` फाइलबाट वातावरणीय भेरिएबलहरू Python एप्लिकेशनमा लोड गर्न `python-dotenv` प्याकेज इन्स्टल गर्नुहोस्। तपाईंले यसलाई `pip` प्रयोग गरेर इन्स्टल गर्न सक्नुहुन्छ:

   ```bash
   pip install python-dotenv
   ```

6. **Python स्क्रिप्टमा वातावरणीय भेरिएबलहरू लोड गर्नुहोस्**: आफ्नो Python स्क्रिप्टमा `python-dotenv` प्याकेज प्रयोग गरेर `.env` फाइलबाट वातावरणीय भेरिएबलहरू लोड गर्नुहोस्:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

यति भयो! तपाईंले सफलतापूर्वक `.env` फाइल बनाउनु भयो, GitHub टोकन थप्नुभयो, र यसलाई आफ्नो Python एप्लिकेशनमा लोड गर्नुभयो।

## आफ्नो कम्प्युटरमा स्थानीय रूपमा कसरी चलाउने

तपाईंको कम्प्युटरमा कोड स्थानीय रूपमा चलाउन, तपाईंले केही संस्करणको [Python इन्स्टल गर्नुपर्नेछ](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)।

त्यसपछि रिपो प्रयोग गर्न, तपाईंले यसलाई क्लोन गर्नुपर्नेछ:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

सबै कुरा तयार भएपछि, तपाईं सुरु गर्न सक्नुहुन्छ!

## वैकल्पिक चरणहरू

### Miniconda इन्स्टल गर्दै

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) हल्का तौलको इन्स्टलर हो जसले [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, र केही प्याकेजहरू इन्स्टल गर्न मद्दत गर्छ।  
Conda आफैं एक प्याकेज म्यानेजर हो, जसले विभिन्न Python [**भर्चुअल वातावरणहरू**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) र प्याकेजहरू सेटअप र स्विच गर्न सजिलो बनाउँछ। यसले `pip` बाट उपलब्ध नभएका प्याकेजहरू इन्स्टल गर्न पनि सहयोग गर्छ।

तपाईं [MiniConda इन्स्टलेशन गाइड](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) अनुसरण गरेर यसलाई सेटअप गर्न सक्नुहुन्छ।

Miniconda इन्स्टल भएपछि, तपाईंले [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) क्लोन गर्नुपर्नेछ (यदि पहिले गर्नुभएको छैन भने)।

अर्को, तपाईंले भर्चुअल वातावरण बनाउनुपर्नेछ। Conda प्रयोग गरेर यो गर्न, नयाँ वातावरण फाइल (_environment.yml_) बनाउनुहोस्। यदि तपाईं Codespaces प्रयोग गर्दै हुनुहुन्छ भने, यो `.devcontainer` डाइरेक्टरी भित्र बनाउनुहोस्, अर्थात् `.devcontainer/environment.yml`।

तलको स्निपेटले आफ्नो वातावरण फाइल भर्नुहोस्:

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

यदि तपाईंलाई Conda प्रयोग गर्दा त्रुटि आउँछ भने, तपाईं टर्मिनलमा तलको कमाण्ड प्रयोग गरेर Microsoft AI Libraries म्यानुअली इन्स्टल गर्न सक्नुहुन्छ।

```
conda install -c microsoft azure-ai-ml
```

वातावरण फाइलले हामीलाई चाहिने निर्भरता निर्दिष्ट गर्छ। `<environment-name>` तपाईंले आफ्नो Conda वातावरणको लागि प्रयोग गर्न चाहेको नाम हो, र `<python-version>` तपाईंले प्रयोग गर्न चाहेको Python को संस्करण हो, उदाहरणका लागि, `3` Python को पछिल्लो मुख्य संस्करण हो।

त्यसपछि, तपाईंले तलका कमाण्डहरू चलाएर आफ्नो Conda वातावरण बनाउन सक्नुहुन्छ:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

यदि कुनै समस्या आएमा [Conda वातावरण गाइड](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) हेर्नुहोस्।

### Visual Studio Code लाई Python सपोर्ट एक्सटेन्सनसहित प्रयोग गर्दै

हामी यो कोर्सका लागि [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटरलाई [Python सपोर्ट एक्सटेन्सन](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) सहित प्रयोग गर्न सिफारिस गर्छौं। यो सिफारिस हो, अनिवार्य होइन।

> **Note**: VS Code मा कोर्स रिपो खोल्दा, तपाईंले प्रोजेक्टलाई कन्टेनर भित्र सेटअप गर्ने विकल्प पाउनुहुन्छ। यो कोर्स रिपो भित्रको [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) डाइरेक्टरीको कारण हो। यसबारे पछि थप जानकारी हुनेछ।

> **Note**: जब तपाईंले रिपो क्लोन गरी VS Code मा खोल्नुहुन्छ, यसले तपाईंलाई Python सपोर्ट एक्सटेन्सन इन्स्टल गर्न सुझाव दिनेछ।

> **Note**: यदि VS Code ले रिपो कन्टेनरमा पुनः खोल्न सुझाव दियो भने, स्थानीय रूपमा इन्स्टल गरिएको Python प्रयोग गर्न यो अनुरोध अस्वीकार गर्नुहोस्।

### ब्राउजरमा Jupyter प्रयोग गर्दै

तपाईंले [Jupyter वातावरण](https://jupyter.org?WT.mc_id=academic-105485-koreyst) सिधै आफ्नो ब्राउजरमा प्रयोग गरेर पनि प्रोजेक्टमा काम गर्न सक्नुहुन्छ। क्लासिक Jupyter र [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) दुवैले स्वतः पूर्ति, कोड हाइलाइटिङ जस्ता सुविधाहरू सहित राम्रो विकास वातावरण प्रदान गर्छन्।

स्थानीय रूपमा Jupyter सुरु गर्न, टर्मिनल/कमाण्ड लाइनमा जानुहोस्, कोर्स डाइरेक्टरीमा नेभिगेट गर्नुहोस्, र निम्न कमाण्ड चलाउनुहोस्:

```bash
jupyter notebook
```

वा

```bash
jupyterhub
```

यसले Jupyter इन्स्ट्यान्स सुरु गर्नेछ र पहुँच गर्न URL कमाण्ड लाइन विन्डोमा देखाइनेछ।

URL पहुँच गरेपछि, तपाईंले कोर्सको रूपरेखा देख्नुहुनेछ र कुनै पनि `*.ipynb` फाइलमा जान सक्नुहुनेछ। उदाहरणका लागि, `08-building-search-applications/python/oai-solution.ipynb`।

### कन्टेनरमा चलाउने

आफ्नो कम्प्युटर वा Codespace मा सबै कुरा सेटअप गर्ने विकल्पको सट्टा, तपाईं [कन्टेनर](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) प्रयोग गर्न सक्नुहुन्छ। कोर्स रिपो भित्रको विशेष `.devcontainer` फोल्डरले VS Code लाई प्रोजेक्ट कन्टेनर भित्र सेटअप गर्न सक्षम बनाउँछ। Codespaces बाहेक, यसका लागि Docker इन्स्टल गर्नुपर्नेछ र यो केही काम लाग्ने भएकाले हामी यो अनुभव भएका प्रयोगकर्तालाई मात्र सिफारिस गर्छौं।

GitHub Codespaces प्रयोग गर्दा तपाईंका API कुञ्जीहरू सुरक्षित राख्नको लागि Codespace Secrets प्रयोग गर्नु उत्तम तरिका हो। कृपया [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) गाइड अनुसरण गर्नुहोस्।

## पाठहरू र प्राविधिक आवश्यकताहरू

कोर्समा ६ वटा अवधारणा पाठहरू र ६ वटा कोडिङ पाठहरू छन्।

कोडिङ पाठहरूका लागि, हामी Azure OpenAI Service प्रयोग गर्दैछौं। तपाईंलाई Azure OpenAI सेवा र API कुञ्जीको पहुँच आवश्यक पर्छ। तपाईं [यो आवेदन पूरा गरेर](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) पहुँचका लागि आवेदन दिन सक्नुहुन्छ।

आवेदन प्रक्रिया पूरा नभएसम्म, प्रत्येक कोडिङ पाठसँग `README.md` फाइल पनि हुन्छ जहाँ तपाईं कोड र आउटपुट हेर्न सक्नुहुन्छ।

## Azure OpenAI सेवा पहिलो पटक प्रयोग गर्दा

यदि तपाईं Azure OpenAI सेवा पहिलो पटक प्रयोग गर्दै हुनुहुन्छ भने, कृपया [Azure OpenAI Service स्रोत कसरी सिर्जना र डिप्लोय गर्ने](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) गाइड अनुसरण गर्नुहोस्।

## OpenAI API पहिलो पटक प्रयोग गर्दा

यदि तपाईं OpenAI API पहिलो पटक प्रयोग गर्दै हुनुहुन्छ भने, कृपया [Interface कसरी सिर्जना र प्रयोग गर्ने](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) गाइड अनुसरण गर्नुहोस्।

## अन्य सिक्नेहरूलाई भेट्नुहोस्

हामीले हाम्रो आधिकारिक [AI Community Discord server](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) मा अन्य सिक्नेहरूलाई भेट्नका लागि च्यानलहरू बनाएका छौं। यो समान सोच भएका उद्यमी, निर्माताहरू, विद्यार्थीहरू, र Generative AI मा स्तर बढाउन चाहनेहरूका लागि नेटवर्किङ गर्ने राम्रो माध्यम हो।

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

प्रोजेक्ट टोली पनि यस Discord सर्भरमा हुनेछ र सिक्नेहरूलाई सहयोग गर्नेछ।

## योगदान गर्नुहोस्

यो कोर्स खुला स्रोत पहल हो। यदि तपाईंले सुधारका क्षेत्रहरू वा समस्याहरू देख्नुभयो भने, कृपया [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) सिर्जना गर्नुहोस् वा [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) लग गर्नुहोस्।

प्रोजेक्ट टोली सबै योगदानहरू ट्र्याक गर्नेछ। खुला स्रोतमा योगदान गर्नु Generative AI मा आफ्नो करियर बनाउनको लागि अद्भुत तरिका हो।

धेरै योगदानहरूका लागि तपाईंले Contributor License Agreement (CLA) मा सहमति जनाउनु पर्ने हुन्छ जसले तपाईंले आफ्नो योगदान प्रयोग गर्ने अधिकार हामीलाई दिनुभएको छ भनी पुष्टि गर्छ। विवरणका लागि [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) हेर्नुहोस्।

महत्त्वपूर्ण: यस रिपोमा अनुवाद गर्दा कृपया मेसिन अनुवाद प्रयोग नगर्नुहोस्। हामी अनुवादहरू समुदायमार्फत जाँच गर्नेछौं, त्यसैले कृपया मात्र तपाईंलाई राम्रोसँग आउने भाषाहरूमा अनुवादका लागि स्वयंसेवक बन्नुहोस्।

जब तपाईंले Pull Request पेश गर्नुहुन्छ, CLA-bot ले स्वचालित रूपमा तपाईंलाई CLA आवश्यक छ कि छैन निर्धारण गर्नेछ र PR लाई उपयुक्त रूपमा चिन्ह लगाउनेछ (जस्तै लेबल, टिप्पणी)। बोटले दिएको निर्देशनहरू पालना गर्नुहोस्। तपाईंले यो प्रक्रिया सबै रिपोहरूमा एक पटक मात्र गर्नु पर्नेछ।

यस प्रोजेक्टले [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) अपनाएको छ। थप जानकारीका लागि Code of Conduct FAQ पढ्नुहोस् वा कुनै प्रश्न वा टिप्पणीका लागि [Email opencode](opencode@microsoft.com) मा सम्पर्क गर्नुहोस्।

## सुरु गरौं

अब तपाईंले यो कोर्स पूरा गर्न आवश्यक चरणहरू पूरा गर्नुभयो, सुरु गरौं [Generative AI र LLMs को परिचय](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) बाट।

**अस्वीकरण**:  
यो दस्तावेज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरी अनुवाद गरिएको हो। हामी शुद्धताका लागि प्रयासरत छौं भने पनि, कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादमा त्रुटि वा अशुद्धता हुन सक्छ। मूल दस्तावेज यसको मूल भाषामा नै अधिकारिक स्रोत मानिनु पर्छ। महत्वपूर्ण जानकारीका लागि व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न कुनै पनि गलतफहमी वा गलत व्याख्याका लागि हामी जिम्मेवार छैनौं।