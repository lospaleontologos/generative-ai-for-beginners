<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "00f2643fec1571acc5d38cc1a3b972d5",
  "translation_date": "2025-07-09T07:10:23+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "th"
}
-->
# เริ่มต้นกับคอร์สนี้

เรารู้สึกตื่นเต้นมากที่คุณจะเริ่มเรียนคอร์สนี้และได้เห็นสิ่งที่คุณจะได้รับแรงบันดาลใจในการสร้างด้วย Generative AI!

เพื่อให้คุณประสบความสำเร็จ หน้านี้จะสรุปขั้นตอนการตั้งค่า ข้อกำหนดทางเทคนิค และแหล่งช่วยเหลือหากต้องการ

## ขั้นตอนการตั้งค่า

เพื่อเริ่มเรียนคอร์สนี้ คุณจะต้องทำตามขั้นตอนดังต่อไปนี้

### 1. Fork Repo นี้

[Fork repo นี้ทั้งหมด](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) ไปยังบัญชี GitHub ของคุณเอง เพื่อให้คุณสามารถแก้ไขโค้ดและทำโจทย์ท้าทายได้ นอกจากนี้คุณยังสามารถ [กดดาว (🌟) ให้ repo นี้](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) เพื่อให้ค้นหา repo นี้และ repo ที่เกี่ยวข้องได้ง่ายขึ้น

### 2. สร้าง codespace

เพื่อหลีกเลี่ยงปัญหาด้าน dependency เมื่อรันโค้ด เราแนะนำให้รันคอร์สนี้ใน [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst)

คุณสามารถสร้างได้โดยเลือกตัวเลือก `Code` บนเวอร์ชันที่คุณ fork มา แล้วเลือกตัวเลือก **Codespaces**

![Dialog showing buttons to create a codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. การเก็บ API Keys ของคุณ

การเก็บ API keys ให้ปลอดภัยเป็นสิ่งสำคัญเมื่อสร้างแอปพลิเคชันใดๆ เราแนะนำให้ไม่เก็บ API keys ไว้ในโค้ดโดยตรง การ commit รายละเอียดเหล่านี้ลงใน public repository อาจทำให้เกิดปัญหาด้านความปลอดภัยและค่าใช้จ่ายที่ไม่คาดคิดหากถูกนำไปใช้โดยผู้ไม่หวังดี  
นี่คือคำแนะนำทีละขั้นตอนในการสร้างไฟล์ `.env` สำหรับ Python และเพิ่ม `GITHUB_TOKEN`:

1. **ไปยังไดเรกทอรีโปรเจกต์ของคุณ**: เปิด terminal หรือ command prompt แล้วไปยังไดเรกทอรีหลักของโปรเจกต์ที่คุณต้องการสร้างไฟล์ `.env`

   ```bash
   cd path/to/your/project
   ```

2. **สร้างไฟล์ `.env`**: ใช้โปรแกรมแก้ไขข้อความที่คุณชอบเพื่อสร้างไฟล์ใหม่ชื่อ `.env` หากใช้ command line คุณสามารถใช้คำสั่ง `touch` (บนระบบ Unix) หรือ `echo` (บน Windows):

   ระบบ Unix:

   ```bash
   touch .env
   ```

   Windows:

   ```cmd
   echo . > .env
   ```

3. **แก้ไขไฟล์ `.env`**: เปิดไฟล์ `.env` ด้วยโปรแกรมแก้ไขข้อความ (เช่น VS Code, Notepad++ หรือโปรแกรมอื่นๆ) แล้วเพิ่มบรรทัดนี้ลงไป โดยแทนที่ `your_github_token_here` ด้วย token GitHub ของคุณจริงๆ:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **บันทึกไฟล์**: บันทึกการเปลี่ยนแปลงและปิดโปรแกรมแก้ไขข้อความ

5. **ติดตั้ง `python-dotenv`**: หากยังไม่ได้ติดตั้ง คุณต้องติดตั้งแพ็กเกจ `python-dotenv` เพื่อโหลด environment variables จากไฟล์ `.env` เข้าสู่แอป Python ของคุณ คุณสามารถติดตั้งด้วย `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **โหลด environment variables ในสคริปต์ Python ของคุณ**: ในสคริปต์ Python ให้ใช้แพ็กเกจ `python-dotenv` เพื่อโหลด environment variables จากไฟล์ `.env`:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

แค่นี้ก็เรียบร้อย! คุณได้สร้างไฟล์ `.env` เพิ่ม GitHub token และโหลดเข้าแอป Python ของคุณเรียบร้อยแล้ว

## วิธีรันโค้ดบนเครื่องของคุณ

หากต้องการรันโค้ดบนเครื่องของคุณเอง คุณจะต้องติดตั้ง [Python เวอร์ชันใดเวอร์ชันหนึ่ง](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)

จากนั้นเพื่อใช้งาน repository นี้ คุณต้อง clone มายังเครื่องของคุณ:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

เมื่อคุณเตรียมทุกอย่างเรียบร้อยแล้ว ก็เริ่มต้นได้เลย!

## ขั้นตอนเสริม (Optional Steps)

### การติดตั้ง Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) เป็นตัวติดตั้งขนาดเล็กสำหรับติดตั้ง [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python และแพ็กเกจบางตัว  
Conda เป็นตัวจัดการแพ็กเกจที่ช่วยให้ตั้งค่าและสลับไปมาระหว่าง [**virtual environments**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) และแพ็กเกจต่างๆ ได้ง่าย นอกจากนี้ยังช่วยติดตั้งแพ็กเกจที่ไม่มีใน `pip` ได้ด้วย

คุณสามารถทำตาม [คู่มือการติดตั้ง MiniConda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) เพื่อเริ่มใช้งาน

เมื่อคุณติดตั้ง Miniconda แล้ว คุณต้อง clone [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (ถ้ายังไม่ได้ทำ)

ถัดไป คุณต้องสร้าง virtual environment โดยใช้ Conda สร้างไฟล์ environment ใหม่ (_environment.yml_) หากคุณใช้ Codespaces ให้สร้างไฟล์นี้ในไดเรกทอรี `.devcontainer` คือ `.devcontainer/environment.yml`

จากนั้นเติมเนื้อหาในไฟล์ environment ด้วยโค้ดตัวอย่างด้านล่างนี้:

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

ถ้าคุณเจอปัญหาในการใช้ conda คุณสามารถติดตั้ง Microsoft AI Libraries ด้วยคำสั่งนี้ใน terminal ได้เลย

```
conda install -c microsoft azure-ai-ml
```

ไฟล์ environment จะระบุ dependencies ที่เราต้องการ `<environment-name>` คือชื่อ environment ที่คุณต้องการใช้ และ `<python-version>` คือเวอร์ชัน Python ที่คุณต้องการ เช่น `3` คือเวอร์ชันหลักล่าสุดของ Python

เมื่อเตรียมไฟล์เสร็จแล้ว คุณสามารถสร้าง Conda environment ได้โดยรันคำสั่งด้านล่างใน command line/terminal

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

หากเจอปัญหาใดๆ ให้ดูที่ [คู่มือ Conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst)

### การใช้ Visual Studio Code กับส่วนขยาย Python support

เราแนะนำให้ใช้ [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) พร้อมติดตั้ง [ส่วนขยาย Python support](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) สำหรับคอร์สนี้ อย่างไรก็ตาม นี่เป็นเพียงคำแนะนำ ไม่ใช่ข้อบังคับ

> **หมายเหตุ**: เมื่อเปิด repository ของคอร์สใน VS Code คุณสามารถตั้งค่าโปรเจกต์ภายใน container ได้ เพราะใน repository มีไดเรกทอรีพิเศษ [`.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) อยู่ รายละเอียดเพิ่มเติมจะกล่าวถึงในภายหลัง

> **หมายเหตุ**: เมื่อคุณ clone และเปิดไดเรกทอรีใน VS Code โปรแกรมจะแนะนำให้ติดตั้งส่วนขยาย Python support อัตโนมัติ

> **หมายเหตุ**: หาก VS Code แนะนำให้เปิด repository ใหม่ใน container ให้ปฏิเสธคำขอนี้เพื่อใช้ Python ที่ติดตั้งในเครื่องแทน

### การใช้ Jupyter ในเบราว์เซอร์

คุณยังสามารถทำงานกับโปรเจกต์นี้โดยใช้ [Jupyter environment](https://jupyter.org?WT.mc_id=academic-105485-koreyst) ผ่านเบราว์เซอร์ได้ ทั้ง Jupyter แบบคลาสสิกและ [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) มีสภาพแวดล้อมการพัฒนาที่ดีพร้อมฟีเจอร์อย่าง auto-completion, การเน้นโค้ด ฯลฯ

เพื่อเริ่ม Jupyter บนเครื่อง ให้เปิด terminal/command line ไปยังไดเรกทอรีของคอร์ส แล้วรันคำสั่งนี้:

```bash
jupyter notebook
```

หรือ

```bash
jupyterhub
```

คำสั่งนี้จะเริ่ม Jupyter instance และแสดง URL สำหรับเข้าถึงในหน้าต่าง command line

เมื่อคุณเข้าถึง URL แล้ว คุณจะเห็นโครงร่างคอร์สและสามารถเปิดไฟล์ `*.ipynb` ใดก็ได้ เช่น `08-building-search-applications/python/oai-solution.ipynb`

### การรันใน container

อีกทางเลือกหนึ่งแทนการตั้งค่าทุกอย่างบนเครื่องหรือ Codespace คือการใช้ [container](../../../00-course-setup/<https:/en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst>)  
ไดเรกทอรีพิเศษ `.devcontainer` ใน repository ของคอร์สช่วยให้ VS Code ตั้งค่าโปรเจกต์ภายใน container ได้  
นอกเหนือจาก Codespaces คุณจะต้องติดตั้ง Docker และค่อนข้างซับซ้อน จึงแนะนำสำหรับผู้ที่มีประสบการณ์กับ container เท่านั้น

วิธีที่ดีที่สุดในการเก็บ API keys ให้ปลอดภัยเมื่อใช้ GitHub Codespaces คือการใช้ Codespace Secrets  
โปรดดูคำแนะนำ [การจัดการความลับใน Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) เพื่อเรียนรู้เพิ่มเติม

## บทเรียนและข้อกำหนดทางเทคนิค

คอร์สนี้มีบทเรียนเชิงแนวคิด 6 บท และบทเรียนเขียนโค้ด 6 บท

สำหรับบทเรียนเขียนโค้ด เราใช้ Azure OpenAI Service คุณจะต้องมีสิทธิ์เข้าถึง Azure OpenAI service และ API key เพื่อรันโค้ดนี้ คุณสามารถสมัครขอสิทธิ์ได้โดย [กรอกใบสมัครนี้](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst)

ในระหว่างรอการอนุมัติใบสมัคร บทเรียนเขียนโค้ดแต่ละบทจะมีไฟล์ `README.md` ที่คุณสามารถดูโค้ดและผลลัพธ์ได้

## การใช้ Azure OpenAI Service ครั้งแรก

หากนี่เป็นครั้งแรกที่คุณใช้ Azure OpenAI service โปรดทำตามคำแนะนำนี้เกี่ยวกับวิธี [สร้างและปรับใช้ Azure OpenAI Service resource](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## การใช้ OpenAI API ครั้งแรก

หากนี่เป็นครั้งแรกที่คุณใช้ OpenAI API โปรดทำตามคำแนะนำเกี่ยวกับวิธี [สร้างและใช้งาน Interface](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## พบปะผู้เรียนคนอื่นๆ

เราได้สร้างช่องทางในเซิร์ฟเวอร์ [AI Community Discord อย่างเป็นทางการ](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) เพื่อให้ผู้เรียนได้พบปะกัน นี่เป็นวิธีที่ดีในการสร้างเครือข่ายกับผู้ประกอบการ นักพัฒนา นักศึกษา และใครก็ตามที่ต้องการพัฒนาทักษะใน Generative AI

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

ทีมโปรเจกต์จะอยู่ใน Discord นี้เพื่อช่วยเหลือผู้เรียนทุกคน

## การมีส่วนร่วม

คอร์สนี้เป็นโครงการโอเพนซอร์ส หากคุณพบจุดที่ควรปรับปรุงหรือปัญหาใดๆ โปรดสร้าง [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) หรือลงบันทึก [GitHub issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst)

ทีมโปรเจกต์จะติดตามการมีส่วนร่วมทั้งหมด การมีส่วนร่วมในโอเพนซอร์สเป็นวิธีที่ยอดเยี่ยมในการสร้างอาชีพใน Generative AI

ส่วนใหญ่การมีส่วนร่วมจะต้องยอมรับ Contributor License Agreement (CLA) ซึ่งเป็นข้อตกลงว่าคุณมีสิทธิ์และอนุญาตให้เราใช้ผลงานของคุณ  
ดูรายละเอียดได้ที่ [เว็บไซต์ CLA, Contributor License Agreement](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst)

สำคัญ: เมื่อแปลข้อความใน repo นี้ โปรดอย่าใช้การแปลด้วยเครื่อง เราจะตรวจสอบการแปลผ่านชุมชน ดังนั้นโปรดอาสาแปลเฉพาะภาษาที่คุณมีความชำนาญเท่านั้น

เมื่อคุณส่ง pull request CLA-bot จะตรวจสอบโดยอัตโนมัติว่าคุณต้องส่ง CLA หรือไม่ และจะติดป้ายกำกับหรือคอมเมนต์ใน PR ตามนั้น  
เพียงทำตามคำแนะนำของบอท คุณจะต้องทำเพียงครั้งเดียวสำหรับทุก repo ที่ใช้ CLA ของเรา

โครงการนี้ได้นำ [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) มาใช้  
สำหรับข้อมูลเพิ่มเติม อ่าน FAQ ของ Code of Conduct หรือติดต่อ [Email opencode](opencode@microsoft.com) หากมีคำถามหรือข้อเสนอแนะเพิ่มเติม

## เริ่มกันเลย

ตอนนี้คุณได้ทำตามขั้นตอนที่จำเป็นสำหรับคอร์สนี้แล้ว มาเริ่มต้นด้วยการ [แนะนำเกี่ยวกับ Generative AI และ LLMs](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) กันเลย!

**ข้อจำกัดความรับผิดชอบ**:  
เอกสารนี้ได้รับการแปลโดยใช้บริการแปลภาษาอัตโนมัติ [Co-op Translator](https://github.com/Azure/co-op-translator) แม้เราจะพยายามให้ความถูกต้องสูงสุด แต่โปรดทราบว่าการแปลอัตโนมัติอาจมีข้อผิดพลาดหรือความไม่ถูกต้อง เอกสารต้นฉบับในภาษาต้นทางถือเป็นแหล่งข้อมูลที่เชื่อถือได้ สำหรับข้อมูลที่สำคัญ ขอแนะนำให้ใช้บริการแปลโดยผู้เชี่ยวชาญมนุษย์ เราไม่รับผิดชอบต่อความเข้าใจผิดหรือการตีความผิดใด ๆ ที่เกิดจากการใช้การแปลนี้