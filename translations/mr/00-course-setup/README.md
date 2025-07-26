<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:05:42+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "mr"
}
-->
# या कोर्ससह सुरुवात करणे

आम्हाला आनंद आहे की तुम्ही हा कोर्स सुरू करत आहात आणि जनरेटिव्ह AI वापरून काय तयार करता येईल हे पाहणार आहात!

तुमच्या यशासाठी, या पृष्ठावर सेटअपचे टप्पे, तांत्रिक गरजा आणि मदतीसाठी कुठे संपर्क करायचा याची माहिती दिली आहे.

## सेटअप टप्पे

हा कोर्स सुरू करण्यासाठी, तुम्हाला खालील टप्पे पूर्ण करावे लागतील.

### 1. हा रेपो Fork करा

[Fork करा हा संपूर्ण रेपो](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) तुमच्या स्वतःच्या GitHub खात्यावर, जेणेकरून तुम्ही कोडमध्ये बदल करू शकता आणि आव्हाने पूर्ण करू शकता. तुम्ही हा रेपो [स्टार (🌟)](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) देखील करू शकता, ज्यामुळे तो आणि संबंधित रेपोज सहज सापडतील.

### 2. कोडस्पेस तयार करा

कोड चालवताना कोणत्याही अवलंबित्वाच्या समस्या टाळण्यासाठी, आम्ही शिफारस करतो की हा कोर्स [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) मध्ये चालवा.

हे तयार करण्यासाठी, तुमच्या Fork केलेल्या रेपोवर `Code` पर्याय निवडा आणि **Codespaces** पर्याय निवडा.

![कोडस्पेस तयार करण्यासाठी बटणे दाखवणारा संवाद](../../../00-course-setup/images/who-will-pay.webp)

### 3. तुमचे API कीज सुरक्षित ठेवणे

कोणत्याही प्रकारचे अॅप्लिकेशन तयार करताना तुमच्या API कीज सुरक्षित ठेवणे महत्त्वाचे आहे. आम्ही शिफारस करतो की API कीज थेट कोडमध्ये साठवू नका. सार्वजनिक रेपोमध्ये कीज कमिट केल्यास सुरक्षा समस्या उद्भवू शकतात आणि चुकीच्या वापरामुळे अनावश्यक खर्चही होऊ शकतो.

Python साठी `.env` फाइल कशी तयार करायची आणि `GITHUB_TOKEN` कसा जोडायचा यासाठी चरण-दर-चरण मार्गदर्शक:

1. **तुमच्या प्रोजेक्ट डायरेक्टरीमध्ये जा**: टर्मिनल किंवा कमांड प्रॉम्प्ट उघडा आणि प्रोजेक्टच्या मूळ फोल्डरमध्ये जा जिथे तुम्हाला `.env` फाइल तयार करायची आहे.

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फाइल तयार करा**: तुमच्या आवडत्या टेक्स्ट एडिटरमध्ये `.env` नावाची नवीन फाइल तयार करा. कमांड लाइन वापरत असल्यास, Unix-आधारित सिस्टमवर `touch` किंवा Windows वर `echo` वापरू शकता:

   Unix-आधारित सिस्टम:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **`.env` फाइल संपादित करा**: `.env` फाइल टेक्स्ट एडिटरमध्ये उघडा (उदा. VS Code, Notepad++, किंवा इतर कोणताही एडिटर). खालील ओळ फाइलमध्ये जोडा, `your_github_token_here` च्या जागी तुमचा खरा GitHub टोकन टाका:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फाइल जतन करा**: बदल जतन करा आणि टेक्स्ट एडिटर बंद करा.

5. **`python-dotenv` इन्स्टॉल करा**: जर आधी इन्स्टॉल केले नसेल तर, `.env` फाइलमधील पर्यावरणीय चल Python अॅप्लिकेशनमध्ये लोड करण्यासाठी `python-dotenv` पॅकेज इन्स्टॉल करा. `pip` वापरून इन्स्टॉल करू शकता:

   ```bash
   pip install python-dotenv
   ```

6. **Python स्क्रिप्टमध्ये पर्यावरणीय चल लोड करा**: तुमच्या Python स्क्रिप्टमध्ये `python-dotenv` पॅकेज वापरून `.env` फाइलमधील पर्यावरणीय चल लोड करा:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

इतकेच! तुम्ही यशस्वीपणे `.env` फाइल तयार केली, GitHub टोकन जोडला आणि Python अॅप्लिकेशनमध्ये लोड केला.

## तुमच्या संगणकावर स्थानिकरित्या कसे चालवायचे

कोड तुमच्या संगणकावर स्थानिकरित्या चालवण्यासाठी, तुमच्याकडे काही आवृत्तीची [Python इन्स्टॉल केलेली](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst) असणे आवश्यक आहे.

नंतर रेपो वापरण्यासाठी, तुम्हाला ते क्लोन करावे लागेल:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

सर्व काही तयार झाल्यावर, तुम्ही सुरुवात करू शकता!

## ऐच्छिक टप्पे

### Miniconda इन्स्टॉल करणे

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) हा Conda, Python आणि काही पॅकेजेस इन्स्टॉल करण्यासाठी हलका इंस्टॉलर आहे.  
Conda हा पॅकेज मॅनेजर आहे, जो वेगवेगळ्या Python [**व्हर्च्युअल एन्व्हायर्नमेंट्स**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) आणि पॅकेजेस सहज सेटअप आणि स्विच करण्यास मदत करतो. `pip` द्वारे उपलब्ध नसलेले पॅकेजेस इन्स्टॉल करण्यासाठीही उपयुक्त आहे.

तुम्ही [MiniConda इन्स्टॉलेशन मार्गदर्शक](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) फॉलो करू शकता.

Miniconda इन्स्टॉल केल्यानंतर, तुम्हाला रेपो क्लोन करावे लागेल (जर आधी केले नसेल तर).

नंतर, तुम्हाला व्हर्च्युअल एन्व्हायर्नमेंट तयार करायचे आहे. Conda वापरून हे करण्यासाठी, नवीन एन्व्हायर्नमेंट फाइल (_environment.yml_) तयार करा. Codespaces वापरत असल्यास, `.devcontainer` फोल्डरमध्ये तयार करा, म्हणजे `.devcontainer/environment.yml`.

खालील कोड स्निपेटने तुमची एन्व्हायर्नमेंट फाइल भरा:

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

जर तुम्हाला Conda वापरताना त्रुटी आल्या तर, टर्मिनलमध्ये खालील कमांड वापरून Microsoft AI लायब्ररी मॅन्युअली इन्स्टॉल करू शकता.

```
conda install -c microsoft azure-ai-ml
```

एन्व्हायर्नमेंट फाइलमध्ये आवश्यक अवलंबित्व नमूद केले आहेत. `<environment-name>` म्हणजे तुम्हाला तुमच्या Conda एन्व्हायर्नमेंटसाठी हवे असलेले नाव, आणि `<python-version>` म्हणजे तुम्हाला वापरायची Python ची आवृत्ती, उदा. `3` ही Python ची नवीनतम मुख्य आवृत्ती आहे.

हे केल्यानंतर, खालील कमांड्स चालवून तुमचे Conda एन्व्हायर्नमेंट तयार करा:

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

कोणतीही अडचण आल्यास [Conda एन्व्हायर्नमेंट्स मार्गदर्शक](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) पहा.

### Python सपोर्ट एक्सटेंशनसह Visual Studio Code वापरणे

आम्ही शिफारस करतो की या कोर्ससाठी [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटर आणि [Python सपोर्ट एक्सटेंशन](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) वापरा. मात्र, ही फक्त शिफारस आहे, अनिवार्य नाही.

> **टीप**: VS Code मध्ये कोर्स रेपो उघडल्यावर, तुम्हाला प्रोजेक्ट कंटेनरमध्ये सेटअप करण्याचा पर्याय मिळतो. कारण कोर्स रेपोमध्ये [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) फोल्डर आहे. याबद्दल नंतर अधिक माहिती.

> **टीप**: रेपो क्लोन करून VS Code मध्ये उघडल्यानंतर, तो आपोआप Python सपोर्ट एक्सटेंशन इन्स्टॉल करण्याचा सल्ला देतो.

> **टीप**: जर VS Code तुम्हाला रेपो कंटेनरमध्ये पुन्हा उघडण्याचा सल्ला देत असेल, तर स्थानिक इन्स्टॉल केलेली Python आवृत्ती वापरण्यासाठी हा सल्ला नाकारावा.

### ब्राउझरमध्ये Jupyter वापरणे

तुम्ही प्रोजेक्टवर [Jupyter पर्यावरण](https://jupyter.org?WT.mc_id=academic-105485-koreyst) वापरून थेट ब्राउझरमध्ये काम करू शकता. क्लासिक Jupyter आणि [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) दोन्हीमध्ये ऑटो-कंप्लीशन, कोड हायलाइटिंग यांसारख्या सुविधा आहेत.

स्थानिकरित्या Jupyter सुरू करण्यासाठी, टर्मिनल/कमांड लाइन उघडा, कोर्स डायरेक्टरीमध्ये जा आणि खालील कमांड चालवा:

```bash
jupyter notebook
```

किंवा

```bash
jupyterhub
```

यामुळे Jupyter सुरू होईल आणि त्याचा URL कमांड लाइन विंडोमध्ये दिसेल.

URL वर प्रवेश केल्यावर, तुम्हाला कोर्सचा आराखडा दिसेल आणि तुम्ही कोणत्याही `*.ipynb` फाइलवर जाऊ शकता. उदा., `08-building-search-applications/python/oai-solution.ipynb`.

### कंटेनरमध्ये चालवणे

तुमच्या संगणकावर किंवा Codespace वर सगळं सेटअप करण्याऐवजी, तुम्ही [कंटेनर](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>) वापरू शकता. कोर्स रेपोमधील विशेष `.devcontainer` फोल्डरमुळे VS Code प्रोजेक्ट कंटेनरमध्ये सेटअप करू शकतो. Codespaces व्यतिरिक्त, यासाठी Docker इन्स्टॉल करावा लागेल आणि थोडा अधिक काम लागतो, त्यामुळे कंटेनर वापराचा अनुभव असलेल्या लोकांसाठीच आम्ही शिफारस करतो.

GitHub Codespaces वापरताना तुमच्या API कीज सुरक्षित ठेवण्याचा एक उत्तम मार्ग म्हणजे Codespace Secrets वापरणे. यासाठी [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) मार्गदर्शक पहा.

## धडे आणि तांत्रिक गरजा

कोर्समध्ये ६ संकल्पना धडे आणि ६ कोडिंग धडे आहेत.

कोडिंग धड्यांसाठी, आम्ही Azure OpenAI Service वापरत आहोत. हा कोड चालवण्यासाठी तुम्हाला Azure OpenAI सेवा आणि API की आवश्यक आहे. प्रवेशासाठी तुम्ही [हा अर्ज](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst) पूर्ण करू शकता.

तुमचा अर्ज प्रक्रिया होत असताना, प्रत्येक कोडिंग धड्यात `README.md` फाइल असते जिथे तुम्ही कोड आणि आउटपुट पाहू शकता.

## Azure OpenAI Service प्रथमच वापरत असाल तर

जर तुम्ही Azure OpenAI सेवा प्रथमच वापरत असाल, तर कृपया [Azure OpenAI Service resource कसे तयार करायचे आणि तैनात करायचे](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) या मार्गदर्शकाचे पालन करा.

## OpenAI API प्रथमच वापरत असाल तर

जर तुम्ही OpenAI API प्रथमच वापरत असाल, तर कृपया [Interface कसे तयार करायचे आणि वापरायचे](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) या मार्गदर्शकाचे पालन करा.

## इतर शिकणाऱ्यांशी भेटा

आम्ही आमच्या अधिकृत [AI Community Discord server](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) मध्ये इतर शिकणाऱ्यांशी भेटण्यासाठी चॅनेल तयार केले आहेत. हे जेनरेटिव्ह AI मध्ये प्रगती करणाऱ्या उद्योजक, बिल्डर्स, विद्यार्थ्यांसाठी नेटवर्किंगसाठी उत्तम ठिकाण आहे.

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

प्रोजेक्ट टीम देखील या Discord सर्व्हरवर शिकणाऱ्यांना मदत करण्यासाठी उपलब्ध असेल.

## योगदान द्या

हा कोर्स एक ओपन-सोर्स उपक्रम आहे. तुम्हाला सुधारणा किंवा समस्या दिसल्यास, कृपया [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) तयार करा किंवा [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) नोंदवा.

प्रोजेक्ट टीम सर्व योगदानांचे निरीक्षण करेल. ओपन सोर्समध्ये योगदान देणे जनरेटिव्ह AI मध्ये तुमचा करिअर घडवण्याचा एक उत्तम मार्ग आहे.

अधिकांश योगदानांसाठी तुम्हाला Contributor License Agreement (CLA) सहमत व्हावे लागते, ज्यात तुम्ही सांगता की तुम्हाला तुमच्या योगदानाचा वापर करण्याचा अधिकार आहे. तपशीलांसाठी [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) पहा.

महत्त्वाचे: या रेपोमधील मजकूर भाषांतर करताना कृपया मशीन ट्रान्सलेशन वापरू नका. आम्ही समुदायाद्वारे भाषांतरांची पडताळणी करू, त्यामुळे फक्त तुम्ही चांगल्या प्रकारे जाणता त्या भाषांसाठीच भाषांतरासाठी स्वयंसेवक व्हा.

तुम्ही pull request सबमिट केल्यावर, CLA-बॉट आपोआप ठरवेल की तुम्हाला CLA प्रदान करायची गरज आहे का आणि PR योग्य लेबल किंवा टिप्पणीने सजवेल. फक्त बॉटच्या सूचनांचे पालन करा. हे तुम्हाला सर्व रेपोजमध्ये एकदाच करावे लागेल.

हा प्रोजेक्ट [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) स्वीकारतो. अधिक माहितीसाठी Code of Conduct FAQ वाचा किंवा [Email opencode](opencode@microsoft.com) वर संपर्क करा.

## चला सुरुवात करूया

आता तुम्ही हा कोर्स पूर्ण करण्यासाठी आवश्यक टप्पे पूर्ण केले आहेत, तर चला [जनरेटिव्ह AI आणि LLMs ची ओळख](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) घेऊन सुरुवात करूया.

**अस्वीकरण**:  
हा दस्तऐवज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून अनुवादित केला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात घ्या की स्वयंचलित अनुवादांमध्ये चुका किंवा अचूकतेची कमतरता असू शकते. मूळ दस्तऐवज त्याच्या स्थानिक भाषेत अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी अनुवाद करण्याची शिफारस केली जाते. या अनुवादाच्या वापरामुळे उद्भवणाऱ्या कोणत्याही गैरसमजुती किंवा चुकीच्या अर्थलागी आम्ही जबाबदार नाही.