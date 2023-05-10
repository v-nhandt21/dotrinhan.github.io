---
title: "Viphoneme"
excerpt: "Pypi Package Viphoneme: Phonetization, Convert Vietnamese Grapheme to IPA <br/><img src='/images/viphoneme.png'>"
collection: portfolio
date: 2023-01-01
---

# Project Custom from vPhon for convert Raw text to IPA

* Use for embeding TTS model using Tacotron2/Fastspeech2 ...

* By using IPA, tacotron2 can deal with cases cross language as a proposal from futre paper

* Function include: Convert Grapheme to IPA, List same token output, normalize text with vinorm and wordtoken

* Requirment: vinorm, underthesea, eng_to_ipa

```
pip install vinorm
pip install underthesea
pip install eng_to_ipa
pip install git+git://github.com/quadrismegistus/prosodic.git
```

* Install viphoneme by pip
```
pip install viphoneme
```

Usage:

```python
from viphoneme import vi2IPA
phoneme = vi2IPA("Được viết vào 6/4/2020, có thể xử lí những trường hợp chứa English")

>> dɯək6 viət5 vaw2 ʂăw5 tʰaŋ5 bon5 năm1 haj1 ŋin2 xoŋ͡m1 ʈăm1 haj1_mɯəj1 , kɔ5_tʰe4 sɯ4_li5 ɲɯŋ3 ʈɯəŋ2_hɤp6 cɯə5 ˈɪŋlɪʃ
```
Function to convert to phoneme with option split each element
```python
from viphoneme import vi2IPA_split
delimit ="/"
vi2IPA_split("Được viết vào 6/4/2020, có thể xử lí những trường hợp chứa English", delimit)

>> /d/ɯə/k/6/ /v/iə/t/5/ /v/a/w/2/ /ʂ/ă/w/5/ /tʰ/a/ŋ/5/ /b/o/n/5/ /n/ă/m/1/ /h/a/j/1/ /ŋ/i/n/2/ /x/o/ŋ͡m/1/ /ʈ/ă/m/1/ /h/a/j/1/_/m/ɯə/j/1/ /,/ /k/ɔ/5/_/tʰ/e/4/ /s/ɯ/4/_/l/i/5/ /ɲ/ɯ/ŋ/3/ /ʈ/ɯə/ŋ/2/_/h/ɤ/p/6/ /c/ɯə/5/ /ɪ/ŋ/l/ɪ/ʃ/ /./
```

Parsing, split phoneme element, with listParse is list of avaible symbol, delimit is symbol to split each element
```python
Parsing(listParse, text, delimit)
```

Get list of symbol using for represent phoneme
```python
from viphoneme import syms
print(syms)
```

* Star me if you find it interesting :))

* Cite me if you use it for paper :)):

```
@inproceedings{tri2020vietnamese,
  title={Vietnamese Speech Synthesis with End-to-End Model and Text Normalization},
  author={Tri, Nguyen Minh and Nam, Cao Xuan and others},
  booktitle={2020 7th NAFOSTED Conference on Information and Computer Science (NICS)},
  pages={179--184},
  year={2020},
  organization={IEEE}
}
```

* This is for quick using to test TTS model in Vietnamese, there is too much more task to use it for production, such as OOV (You can handle it by using MFA from Kaldi or Transformer Aligner)

+ Montreal-Forced-Aligner: https://github.com/MontrealCorpusTools/Montreal-Forced-Aligner