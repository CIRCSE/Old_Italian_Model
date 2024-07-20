# Old Italian Model

This repository contains the Stanza model for Old Italian, based on the data from the UD treebank [Italian-Old](https://github.com/UniversalDependencies/UD_Italian-Old) (version 2.14). 
The model is built on parts of two _Cantiche_ of the _Divine Comedy_ of Dante Alighieri, _Inferno_ and _Purgatorio_, an Old Italian (Florentine) poem composed between approximately 1306 and 1321.

## Train data

The training data is composed as follows:

<code>train:</code> 1 748 sentences and 57 898 tokens

  _Inferno_: 902 sentences (OldItalian_Dante_Inferno-1; OldItalian_Dante_Inferno-902) - 28 995 tokens
  
  _Purgatorio_: 846 sentences (OldItalian_Dante_Purgatorio-1; OldItalian_Dante_Purgatorio-846) - 28 903 tokens
      
<code>dev:</code> 316 sentences and 12 439 tokens

  _Inferno_: 151 sentences (OldItalian_Dante_Inferno-903; OldItalian_Dante_Inferno-1053) - 6 232 tokens
  
  _Purgatorio_: 165 sentences (OldItalian_Dante_Purgatorio-847; OldItalian_Dante_Purgatorio-1011) - 6 207 tokens


## How to use

Clone this repository:
```
https://github.com/CIRCSE/Old_Italian_Model.git
cd Old_Italian_Model
```
Create and activate a python virtual environment (virtualenv, conda, minicoda, etc). Here an example with virtualenv:
```
virtualenv -p python3 venv
source venv/bin/activate
```
or if you installed virtualenv as a module:
```
python -m virtualenv -p python3 venv
source venv/bin/activate
```

install the Stanza module with:
```
pip install stanza
```

To perform a small test, launch the command  :
```
python processText.py ./OldItalianModel "Vuolsi così colà dove si puote ciò che si vuole, e più non dimandare." old_italian_out.conllu
```
this commands will produce an annotated file (```old_italian_out```) with tok,lemma,pos,parser.
If everything went correctly the conllu file should contain something similar to this:

```
# text = Vuolsi così colà dove si puote ciò che si vuole, e più non dimandare.
# sent_id = 0
1-2     Vuolsi  _       _       _       _       _       _       _       start_char=0|end_char=6
1       Vuole   volere  VERB    vta*2ips3       Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 0       root    _       _
2       si      si      PRON    pf3xim  Clitic=Yes|Person=3|PronType=Prs|Reflex=Yes     1       expl:impers     _       _
3       così    così    ADV     b       _       1       advmod  _       start_char=7|end_char=11
4       colà    colà    ADV     b       _       1       advmod:lmod     _       start_char=12|end_char=16
5       dove    dove    ADV     b       _       7       advmod:lmod     _       start_char=17|end_char=21
6       si      si      PRON    pf3ypa  Clitic=Yes|Person=3|PronType=Prs|Reflex=Yes     7       expl:impers     _       start_char=22|end_char=24
7       puote   potere  VERB    vtp2ips3        Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin|Voice=Pass        4       acl:relcl       _       start_char=25|end_char=30
8       ciò     cio'    PRON    pd      PronType=Dem    7       obj     _       start_char=31|end_char=34
9       che     che     PRON    pr      PronType=Rel    11      nsubj   _       start_char=35|end_char=38
10      si      si      PRON    pf3yia  Clitic=Yes|Person=3|PronType=Prs|Reflex=Yes     11      expl:impers     _       start_char=39|end_char=41
11      vuole   volere  VERB    vta*2ips3       Mood=Ind|Number=Sing|Person=3|Tense=Pres|VerbForm=Fin|Voice=Act 8       acl:relcl       _       start_char=42|end_char=47|SpaceAfter=No
12      ,       ,       PUNCT   _       _       16      punct   _       start_char=47|end_char=48
13      e       e       CCONJ   cscc    _       16      cc      _       start_char=49|end_char=50
14      più     più     ADV     b       _       16      advmod  _       start_char=51|end_char=54
15      non     non     ADV     b       PronType=Neg    16      advmod:neg      _       start_char=55|end_char=58
16      dimandare       domandare       VERB    vta1mps2        Mood=Imp|Number=Sing|Person=2|Tense=Pres|VerbForm=Fin|Voice=Act 1       conj    _       start_char=59|end_char=68|SpaceAfter=No
17      .       .       PUNCT   _       _       1       punct   _       start_char=68|end_char=69|SpaceAfter=No

```


Similarly, if the file to be annotated is in conllu format, use:
```
python processConllu.py  ./OldItalianModel <conlluFile.conllu> old_italian_out.conllu
```


## Contact

For further details, please contact: giovanni.moretti@unicatt.it, claudia.corbetta@unibg.it 

