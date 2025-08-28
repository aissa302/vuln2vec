# Vuln2Vec

**Vuln2Vec** is a domain-specific Word2Vec model for **cybersecurity text mining and NLP research**.  
It is trained on multiple heterogeneous sources, including:  

- [NVD](https://nvd.nist.gov/) – National Vulnerability Database  
- [CNVD](https://www.cnvd.org.cn/) – China National Vulnerability Database  
- [CNNVD](http://www.cnnvd.org.cn/) – China National Vulnerability Database  
- [VarIoT](https://variotdbs.fzi.de/) – IoT vulnerability database  
- English Wikipedia (**Security category**)  
- Computer Science–related **Stack Exchange Q&As**  

The goal is to provide **high-quality embeddings** that capture cybersecurity-specific terminology, making it easier to analyze vulnerabilities, exploits, and security-related discussions.

---

## 🚀 Features
- Preprocessing & normalization of raw text
- Tokenization with support for **multi-word expressions** (e.g., `cross_site`, `access_control`)
- Ready-to-use Word2Vec embeddings for cybersecurity research

---

## 🔧 Installation
Clone the repository and install the dependencies:

```bash
git clone https://github.com/AissaBenyahya/vuln2vec.git
cd vuln2vec
pip install -r requirements.txt
```
## Preprocess raw text
```python
from preprocessor import CBSPreprocessor

preprocessor = CBSPreprocessor()
cleaned_text = preprocessor.preprocess(
    "Amasty Blog is an extension of a website page of Amasty.AMASTY BLOG Pro 2.10.3 and 2.10.4 plug-in exist in cross-site scripting vulnerabilities. The attacker can use vulnerabilities to inject cross-site code to initiate XSS attacks."
)

print(cleaned_text)
# 'amasty blog is an extension of website page of blog pro and plug_in exist in vulnerabilities the attacker can use vulnerabilities to inject cross_site code to initiate xss attacks'
```
## Tokenize into valid tokens
```python
from preprocessor import CBSPreprocessor

preprocessor = CBSPreprocessor()
valid_tokens = preprocessor.tokenize(
    "Amasty Blog is an extension of a website page of Amasty.AMASTY BLOG Pro 2.10.3 and 2.10.4 plug-in exist in cross-site scripting vulnerabilities. The attacker can use vulnerabilities to inject cross-site code to initiate XSS attacks."
)

print(valid_tokens)
# ['amasty','blog','is','an','extension','of','website','page','of','blog','pro','and',
#  'plug_in','exist','in','vulnerabilities','the','attacker','can','use','vulnerabilities',
#  'to','inject','cross_site','code','to','initiate','xss','attacks']
```

## Citation
```bash
@article{yahya2025improving,
  title={Improving critical infrastructure security through hybrid embeddings for vulnerability classification},
  author={Yahya, Aissa Ben and El Akhal, Hicham and El Alaoui, Abdelbaki El Belrhiti},
  journal={Journal of Information Security and Applications},
  volume={93},
  pages={104185},
  year={2025},
  publisher={Elsevier}
}
```