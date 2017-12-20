---
layout: post
title: "Nine Kinds of Ancient Greek Treebanks"
date: 2017-12-20 15:46
comments: true
external-url:
categories:
- Treebanks
---

When I blog or speak about Greek treebanks, I frequently refer to one or more of the treebanks that are currently available.  Few people realize how many treebanks exist for ancient Greek, and even fewer have ever seriously looked at more than one.  I do not know of a web page that lists all of the ones I know of, so I thought it would be helpful to list them in one blog post, providing basic information about each.

So here is a catalog of treebanks for ancient Greek.

# Ancient Greek and Latin Dependency Treebank

## Overview:

- Model: Dependency
- License: [Creative Commons Attribution-ShareAlike 3.0 License](https://creativecommons.org/licenses/by-sa/3.0/us/)
- Data: [GitHub](https://perseusdl.github.io/treebank_data/)
- Documentation: [Annotation Guidelines](https://github.com/PerseusDL/treebank_data/tree/master/AGDT2/guidelines)

## Sample Display:

Screenshot taken from [this display](http://www.perseids.org/tools/arethusa/app/#/perseids?chunk=1&doc=27701)

![Euthyphro]({{ site.url }}/images/euthyphro-agnt.1.png)

## Sample Data:

```xml
<sentence subdoc="1" id="2857961" document_id="urn:cts:greekLit:tlg0059.tlg001.perseus-grc1">
  <annotator>celano</annotator>
  <word id="1" form="τί" lemma="τίς" postag="p-s---nn-" head="7" relation="SBJ" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="2" form="νεώτερον" lemma="νεώτερος" postag="a-s---nn-" head="1" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="3" form="," lemma="," postag="u--------" head="5" relation="AuxX" cite=""/>
  <word id="4" form="ὦ" lemma="ὦ" postag="i--------" head="5" relation="AuxZ" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="5" form="Σώκρατες" lemma="Σωκράτης" postag="n-s---mv-" head="7" relation="ExD" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="6" form="," lemma="," postag="u--------" head="5" relation="AuxX" cite=""/>
  <word id="7" form="γέγονεν" lemma="γίγνομαι" postag="v3sria---" head="0" relation="PRED" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="8" form="," lemma="," postag="u--------" head="9" relation="AuxX" cite=""/>
  <word id="9" form="ὅτι" lemma="ὅτι" postag="c--------" head="7" relation="AuxC" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="10" form="σὺ" lemma="σύ" postag="p-s---mn-" head="18" relation="SBJ" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="11" form="τὰς" lemma="ὁ" postag="l-p---fa-" head="15" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="12" form="ἐν" lemma="ἐν" postag="r--------" head="15" relation="AuxP" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="13" form="Λυκείῳ" lemma="Λύκειον" postag="n-s---nd-" head="12" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="14" form="καταλιπὼν" lemma="καταλείπω" postag="v-sapamn-" head="18" relation="ADV" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="15" form="διατριβὰς" lemma="διατριβή" postag="n-p---fa-" head="14" relation="OBJ" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="16" form="ἐνθάδε" lemma="ἐνθάδε" postag="d--------" head="18" relation="ADV" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="17" form="νῦν" lemma="νῦν" postag="d--------" head="18" relation="ADV" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="18" form="διατρίβεις" lemma="διατρίβω" postag="v2spia---" head="9" relation="ADV" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="19" form="περὶ" lemma="περί" postag="r--------" head="18" relation="AuxP" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="20" form="τὴν" lemma="ὁ" postag="l-s---fa-" head="23" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="21" form="τοῦ" lemma="ὁ" postag="l-s---mg-" head="22" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="22" form="βασιλέως" lemma="βασιλεύς" postag="n-s---mg-" head="23" relation="ATR" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="23" form="στοάν" lemma="στοά" postag="n-s---fa-" head="19" relation="ADV" cite="urn:cts:greekLit:tlg0059.tlg001:1"/>
  <word id="24" form=";" lemma=";" postag="u--------" head="0" relation="AuxK" cite=""/>
</sentence>
```

# Accordance Grammatical Syntax add-on to GNT28-T

## Overview:

- Model: Constituency
- License: Commercial.  Sold for use with Accordance Bible Software.  See [Grammatical Syntax add-on to GNT28-T](https://www.accordancebible.com/store/details/?pid=GNT28-T.syntax).

## Sample Display:

![Matthew 1:20 (Accordance)]({{ site.url }}/images/matt.1.20.accordance.png)

# Cascadia Syntax Graphs of the New Testament: SBL Edition

- Model: Constituency ([Headed Phrase-Structure Grammar](https://koine-greek.com/2010/03/21/the-theory-behind-the-cascadia-syntax-graphs/))
- License: Commercial.  Sold for use with Logos Bible Software.  See [Cascadia Syntax Graphs of the New Testament: SBL Edition](https://www.logos.com/product/27284/cascadia-syntax-graphs-of-the-new-testament-sbl-edition).

## Sample Display:

![Matthew 1:20 (Cascadia)]({{ site.url }}/images/matt.1.20.cascadia.png)

# Global Bible Initiative Syntax Trees

## Overview:

- Model: Constituency ([Headed Phrase-Structure Grammar](https://koine-greek.com/2010/03/21/the-theory-behind-the-cascadia-syntax-graphs/))
- License:  [CC-BY-SA License] (http://creativecommons.org/licenses/by-sa/3.0/).
- Data: [GitHub](https://github.com/biblicalhumanities/greek-new-testament)
- Documentation: [Documentation for Asia Bible Society's SBL Greek New Testament Treebank](https://github.com/biblicalhumanities/greek-new-testament/blob/master/syntax-trees/nestle1904/doc/SBLGNT%20Treebank%20Documentation.pdf)

The [Global Bible Initiative](http://www.globalbibleinitiative.org/) was formerly known as the Asia Bible Society. The Cascadia Syntax Graphs are an earlier version of the GBI trees that were released to Logos on a non-exclusive basis. In the vast majority of places, the analysis is the same.

## Sample Display:

![Matthew 1:20 (GBI)]({{ site.url }}/images/matt.1.20.gbi.png)

## Sample Data

```xml
<Node Cat="CL" Start="22" End="30" Rule="sub-CL" Head="1" nodeId="400010200240090">
    <Node Cat="conj" Start="22" End="22" UnicodeLemma="γάρ" Unicode="γὰρ" morphId="40001020024" nodeId="400010200240010">γὰρ</Node>
        <Node Cat="CL" Start="23" End="30" Rule="S-P-VC" Head="1" nodeId="400010200230080">
          <Node Cat="S" Start="23" End="26" Rule="Np2S" Head="0" HasDet="True" nodeId="400010200230041">
            <Node Cat="np" Start="23" End="26" Rule="DetCL" Head="1" HasDet="True" nodeId="400010200230040">
              <Node Cat="det" Start="23" End="23" Case="Nominative" UnicodeLemma="ὁ" Unicode="τὸ" Gender="Neuter" Number="Singular" morphId="40001020023" nodeId="400010200230010">τὸ</Node>
              <Node Cat="CL" Start="24" End="26" Rule="ADV-V" Head="1" nodeId="400010200250030">
                <Node Cat="ADV" Start="24" End="25" Rule="pp2ADV" Head="0" nodeId="400010200250021">
                  <Node Cat="pp" Start="24" End="25" Rule="PrepNp" Head="1" nodeId="400010200250020">
                    <Node Cat="prep" Start="24" End="24" UnicodeLemma="ἐν" Unicode="ἐν" morphId="40001020025" nodeId="400010200250010">ἐν</Node>
                    <Node Cat="np" Start="25" End="25" Rule="Pron2NP" Head="0" nodeId="400010200260011">
                      <Node Cat="pron" Start="25" End="25" UnicodeLemma="αὐτός" Unicode="αὐτῇ" Number="Singular" Type="Personal" morphId="40001020026" Case="Dative" Gender="Feminine" nodeId="400010200260010">αὐτῇ</Node>
                    </Node>
                  </Node>
                </Node>
                <Node Cat="V" Start="26" End="26" Rule="Vp2V" Head="0" nodeId="400010200270012">
                  <Node Cat="vp" Start="26" End="26" Rule="V2VP" Head="0" nodeId="400010200270011">
                    <Node Cat="verb" Start="26" End="26" UnicodeLemma="γεννάω" Voice="Passive" Unicode="γεννηθὲν" Tense="Aorist" Number="Singular" morphId="40001020027" Mood="Participle" Case="Nominative" Gender="Neuter" nodeId="400010200270010">γεννηθὲν</Node>
                  </Node>
                </Node>
              </Node>
            </Node>
          </Node>
          <Node Cat="P" Start="27" End="29" Rule="pp2P" Head="0" nodeId="400010200280031">
            <Node Cat="pp" Start="27" End="29" Rule="PrepNp" Head="1" nodeId="400010200280030">
              <Node Cat="prep" Start="27" End="27" UnicodeLemma="ἐκ" Unicode="ἐκ" morphId="40001020028" nodeId="400010200280010">ἐκ</Node>
              <Node Cat="np" Start="28" End="29" Rule="NpAdjp" Head="0" nodeId="400010200290020">
                <Node Cat="np" Start="28" End="28" Rule="N2NP" Head="0" nodeId="400010200290011">
                  <Node Cat="noun" Start="28" End="28" UnicodeLemma="πνεῦμα" Unicode="πνεύματός" Number="Singular" Type="Common" morphId="40001020029" Case="Genitive" Gender="Neuter" nodeId="400010200290010">πνεύματός</Node>
                </Node>
                <Node Cat="adjp" Start="29" End="29" Rule="Adj2Adjp" Head="0" nodeId="400010200310011">
                  <Node Cat="adj" Start="29" End="29" Case="Genitive" UnicodeLemma="ἅγιος" Unicode="ἁγίου·" Gender="Neuter" Number="Singular" morphId="40001020031" nodeId="400010200310010">ἁγίου</Node>
                </Node>
              </Node>
            </Node>
          </Node>
          <Node Cat="VC" Start="30" End="30" Rule="vp2VC" Head="0" nodeId="400010200300012">
            <Node Cat="vp" Start="30" End="30" Rule="V2VP" Head="0" nodeId="400010200300011">
              <Node Cat="verb" Start="30" End="30" UnicodeLemma="εἰμί" Person="Third" Voice="Active" Unicode="ἐστιν" Tense="Present" Number="Singular" morphId="40001020030" Mood="Indicative" nodeId="400010200300010">ἐστιν</Node>
            </Node>
          </Node>
        </Node>
    </Node>
</Node>
```

# Lowfat Syntax Trees

## Overview:

- Model: Constituency (eclectic model optimized for querying, derived from Global Bible Initiative Syntax Trees)
- License:  [CC-BY-SA License] (http://creativecommons.org/licenses/by-sa/3.0/).
- Data: [GitHub](https://github.com/biblicalhumanities/greek-new-testament)
- Documentation: [Documentation for Asia Bible Society's SBL Greek New Testament Treebank](https://github.com/biblicalhumanities/greek-new-testament/blob/master/syntax-trees/nestle1904/doc/SBLGNT%20Treebank%20Documentation.pdf)

## Sample Display:

![Matthew 1:20 (Lowfat)]({{ site.url }}/images/matt.1.20.lowfat.png)

## Sample Data

```xml
 <wg role="adv" class="cl" n="400010200240090">
    <w class="conj"
       osisId="Matt.1.20!24"
       n="400010200240010"
       lemma="γάρ"
       normalized="γάρ"
       strong="1063"
       discontinuous="true"
       gloss="for">γὰρ</w>
    <wg class="cl" n="400010200230080">
       <wg role="s" class="np" n="400010200230040" articular="true">
          <w class="det"
             osisId="Matt.1.20!23"
             n="400010200230010"
             lemma="ὁ"
             normalized="τό"
             strong="3588"
             number="singular"
             gender="neuter"
             case="nominative"
             gloss="that">τὸ</w>
          <wg class="cl" n="400010200250030" head="true">
             <wg role="adv" class="pp" n="400010200250020">
                <w class="prep"
                   osisId="Matt.1.20!25"
                   n="400010200250010"
                   lemma="ἐν"
                   normalized="ἐν"
                   strong="1722"
                   gloss="in">ἐν</w>
                <w class="pron"
                   type="personal"
                   osisId="Matt.1.20!26"
                   n="400010200260010"
                   lemma="αὐτός"
                   normalized="αὐτῇ"
                   strong="846"
                   number="singular"
                   gender="feminine"
                   case="dative"
                   head="true"
                   gloss="her">αὐτῇ</w>
             </wg>
             <w role="v"
                class="verb"
                osisId="Matt.1.20!27"
                n="400010200270010"
                lemma="γεννάω"
                normalized="γεννηθέν"
                strong="1080"
                number="singular"
                gender="neuter"
                case="nominative"
                tense="aorist"
                voice="passive"
                mood="participle"
                type="?"
                head="true"
                gloss="having been conceived">γεννηθὲν</w>
          </wg>
       </wg>
       <wg role="p" class="pp" n="400010200280030" head="true">
          <w class="prep"
             osisId="Matt.1.20!28"
             n="400010200280010"
             lemma="ἐκ"
             normalized="ἐκ"
             strong="1537"
             gloss="from">ἐκ</w>
          <wg class="np" n="400010200290020" head="true">
             <w class="noun"
                type="common"
                osisId="Matt.1.20!29"
                n="400010200290010"
                lemma="πνεῦμα"
                normalized="Πνεύματος"
                strong="4151"
                number="singular"
                gender="neuter"
                case="genitive"
                head="true"
                gloss="[the] Spirit">Πνεύματός</w>
             <w class="adj"
                osisId="Matt.1.20!31"
                n="400010200310010"
                lemma="ἅγιος"
                normalized="Ἁγίου"
                strong="40"
                number="singular"
                gender="neuter"
                case="genitive"
                discontinuous="true"
                gloss="Holy">Ἁγίου·</w>
          </wg>
       </wg>
       <w role="vc"
          class="verb"
          osisId="Matt.1.20!30"
          n="400010200300010"
          lemma="εἰμί"
          normalized="ἐστιν"
          strong="1510"
          number="singular"
          person="third"
          tense="present"
          voice="active"
          mood="indicative"
          gloss="is">ἐστιν</w>
    </wg>
 </wg>

```

# OpenText

## Overview:

- Model: Constituency (Systemic-Functional Linguistics)
- License: Not yet openly licensed.
- Website: [OpenText.org](http://opentext.org/)

## Sample Display:

This display is taken from a newer internal version that is not yet public:

![Matthew 1:20 (OpenText)]({{ site.url }}/images/matt.1.20.opentext.png)

This data is taken from a newer internal version that is not yet public:

## Sample Data

```xml

      <wg id="d1e1077"
          class="cl"
          connect="NT.Mat.1_c60"
          projected="yes"
          old_id="NT.Mat.1_c62">
         <wg id="d1e1078"
             next="d1e1078.b"
             role="Subject"
             class="cl"
             old_id="NT.Mat.1_c63">
            <wg id="d1e1079"
                role="Predicator"
                class="wg"
                old_id="NT.Mat.1_wg225">
               <w id="d1e1080"
                  role="Specifier"
                  old_id="NT.Mat.w340"
                  n="340"
                  lemma="ὁ"
                  class="ART"
                  num="sing"
                  cas="nom"
                  gen="neu"
                  majorDom="92"
                  subDom="24">τὸ</w>
            </wg>
         </wg>
         <wg id="d1e1089"
             role="Conjunction"
             class="wg"
             old_id="NT.Mat.1_wg226">
            <w id="d1e1090"
               role="Head"
               old_id="NT.Mat.w341"
               n="341"
               lemma="γάρ"
               class="PAR"
               majorDom="89 91"
               subDom="23 1">γὰρ</w>
         </wg>
         <wg id="d1e1078.b" prev="d1e1078">
            <wg id="d1e1084" role="Adjunct" class="wg" old_id="NT.Mat.1_wg224">
               <w id="d1e1085"
                  role="Specifier"
                  old_id="NT.Mat.w342"
                  n="342"
                  lemma="ἐν"
                  class="PRP"
                  majorDom="83 13 84 89 90 67"
                  subDom="13 9 47 23 8 22 119 80 84 5 141 76 26 48 10 56 56 6 30 23 33 136">ἐν</w>
               <w id="d1e1087"
                  role="Head"
                  old_id="NT.Mat.w343"
                  n="343"
                  lemma="αὐτός"
                  class="PRO"
                  num="sing"
                  cas="dat"
                  type="int"
                  gen="fem"
                  majorDom="92 58"
                  subDom="11 37 31">αὐτῇ</w>
            </wg>
            <wg id="d1e1079"
                role="Predicator"
                class="wg"
                old_id="NT.Mat.1_wg225">
               <w id="d1e1082"
                  role="Head"
                  old_id="NT.Mat.w344"
                  n="344"
                  lemma="γεννάω"
                  class="VBP"
                  num="sing"
                  cas="nom"
                  voc="mop"
                  gen="neu"
                  tf="aor"
                  majorDom="23 13"
                  subDom="58 52 56 129">γεννηθὲν</w>
            </wg>
         </wg>
         <wg id="d1e1092"
             next="d1e1092.b"
             role="Adjunct"
             class="wg"
             old_id="NT.Mat.1_wg227">
            <w id="d1e1093"
               role="Specifier"
               old_id="NT.Mat.w345"
               n="345"
               lemma="ἐκ"
               class="PRP"
               majorDom="84 89 90 63 68 67 57"
               subDom="4 25 77 85 121 142 12 16 20 54 33 131 162">ἐκ</w>
            <w id="d1e1095"
               role="Head"
               old_id="NT.Mat.w346"
               n="346"
               lemma="πνεῦμα"
               class="NON"
               num="sing"
               cas="gen"
               gen="neu"
               majorDom="12 26 30 14 23"
               subDom="18 33 37 42 9 6 4 186">πνεύματός</w>
         </wg>
         <wg id="d1e1099"
             role="Predicator"
             class="wg"
             old_id="NT.Mat.1_wg228">
            <w id="d1e1100"
               role="Head"
               old_id="NT.Mat.w347"
               n="347"
               lemma="εἰμί"
               class="VBF"
               augment="-"
               num="sing"
               per="3rd"
               mod="ind"
               majorDom="13 85 71 58"
               subDom="1 4 69 104 1 1 67 68">ἐστιν</w>
         </wg>
         <wg id="d1e1092.b" prev="d1e1092">
            <w id="d1e1097"
               role="Definer"
               old_id="NT.Mat.w348"
               n="348"
               lemma="ἅγιος"
               class="ADJ"
               num="sing"
               cas="gen"
               gen="neu"
               majorDom="88 53"
               subDom="24 46">ἁγίου</w>
         </wg>
      </wg>
```

# PROIEL

## Overview:

- Model: Enhanced Dependency
- License: [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License](http://creativecommons.org/licenses/by-nc-sa/3.0/us/)
- Data: [GitHub](https://github.com/proiel)
- Documentation: [Annotation Guidelines](http://folk.uio.no/daghaug/syntactic_guidelines.pdf)
- Citation: Dag T. T. Haug and Marius L. Jøhndal. 2008. 'Creating a Parallel Treebank of the Old Indo-European Bible Translations'. In Caroline Sporleder and Kiril Ribarov (eds.). Proceedings of the Second Workshop on Language Technology for Cultural Heritage Data (LaTeCH 2008) (2008), pp. 27-34.

## Sample Display:

![Matthew 1:20 (PROIEL)]({{ site.url }}/images/matt.1.20.proiel.png)

## Sample Data:

```xml
<sentence id="47628" status="reviewed" presentation-after=" ">
<token id="267082" form="τὸ" citation-part="MATT 1.20" lemma="ὁ" part-of-speech="S-" morphology="-s---nn--i" head-id="267086" relation="aux" presentation-after=" "/>
<token id="267083" form="γὰρ" citation-part="MATT 1.20" lemma="γάρ" part-of-speech="Df" morphology="---------n" head-id="267089" relation="aux" presentation-after=" "/>
<token id="267084" form="ἐν" citation-part="MATT 1.20" lemma="ἐν" part-of-speech="R-" morphology="---------n" head-id="267086" relation="adv" presentation-after=" "/>
<token id="267085" form="αὐτῇ" citation-part="MATT 1.20" lemma="αὐτός" part-of-speech="Pp" morphology="3s---fd--i" head-id="267084" relation="obl" antecedent-id="267077" information-status="old" presentation-after=" "/>
<token id="267086" form="γεννηθὲν" citation-part="MATT 1.20" lemma="γεννάω" part-of-speech="V-" morphology="-sappnn--i" head-id="267089" relation="sub" information-status="acc_gen" presentation-after=" "/>
<token id="267087" form="ἐκ" citation-part="MATT 1.20" lemma="ἐκ" part-of-speech="R-" morphology="---------n" head-id="267089" relation="xobj" presentation-after=" ">
  <slash target-id="267086" relation="xsub"/>
</token>
<token id="267088" form="πνεύματός" citation-part="MATT 1.20" lemma="πνεῦμα" part-of-speech="Nb" morphology="-s---ng--i" head-id="267087" relation="obl" antecedent-id="267035" information-status="acc_gen" presentation-after=" "/>
<token id="267089" form="ἐστιν" citation-part="MATT 1.20" lemma="εἰμί#1" part-of-speech="V-" morphology="3spia----i" relation="pred" presentation-after=" "/>
<token id="267090" form="ἁγίου" citation-part="MATT 1.20" lemma="ἅγιος" part-of-speech="A-" morphology="-s---ngp-i" head-id="267088" relation="atr" presentation-after="·"/>
</sentence>
```

# Syntacticus - based on PROIEL

## Overview:

- Model: Universal Dependency - see [universaldependencies.org](http://universaldependencies.org/). Derived from PROIEL, uses `.conll` files included as part of the PROIEL distribution.
- License: [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License](http://creativecommons.org/licenses/by-nc-sa/3.0/us/)
- Website: [syntacticus.org](http://syntacticus.org)
- Data: [GitHub](https://github.com/proiel)

## Sample Display:

As rendered [on the Syntacticus website](http://syntacticus.org/sentence/proiel:20170214:greek-nt:47628):

![Matthew 1:20 (Syntacticus)]({{ site.url }}/images/matt.1.20.syntacticus.png)

Same data, rendered in [Arborator](https://arborator.ilpga.fr/q.cgi):

![Matthew 1:20 (Arborator)]({{ site.url }}/images/matt.1.20.arborator.png)

## Sample Data:

```tsv
1   τὸ  ὁ   S   S-  NUMBs|GENDn|CASEn   5   aux _   _
2   γὰρ γάρ D   Df  INFLn   8   aux _   _
3   ἐν  ἐν  R   R-  INFLn   5   adv _   _
4   αὐτῇ    αὐτός   P   Pp  PERS3|NUMBs|GENDf|CASEd 3   obl _   _
5   γεννηθὲν    γεννάω  V   V-  NUMBs|TENSa|MOODp|VOICp|GENDn|CASEn 8   sub _   _
6   ἐκ  ἐκ  R   R-  INFLn   8   xobj    _   _
7   πνεύματός   πνεῦμα  N   Nb  NUMBs|GENDn|CASEg   6   obl _   _
8   ἐστιν   εἰμί#1  V   V-  PERS3|NUMBs|TENSp|MOODi|VOICa   0   pred    _   _
9   ἁγίου   ἅγιος   A   A-  NUMBs|GENDn|CASEg|DEGRp 7   atr _   _
```

# Treedown

## Overview:

- Model: Constituency - an eclectic model implemented as a [Domain-Specific Language (DSL)](https://en.wikipedia.org/wiki/Domain-specific_language)
- License: [Apache License 2.0](https://github.com/biblicalhumanities/treedown/blob/master/LICENSE.md)
- Implementation: [GitHub](https://github.com/biblicalhumanities/treedown)
- Description: [Treedown: A Simple Notation for Syntax](http://jonathanrobie.biblicalhumanities.org/blog/2017/05/12/lowfat-treebanks-visualizing/)

Treedown is a text-based language designed to support rapid treebanking.

## Sample Display:

![Matthew 1:20 (Treedown)]({{ site.url }}/images/matt.1.20.td.png)

## Sample Data:

The XML format for Treedown is still evolving, and treebanks using this format are not yet publicly available.  The Lowfat XML format is the basis for the current internal format.  A parser converts Treedown to Lowfat XML.
