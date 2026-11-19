> [!IMPORTANT]
> OmniDentBench has moved to [FreedomIntelligence/OmniDentBench](https://github.com/FreedomIntelligence/OmniDentBench). The canonical repository contains the dataset, evaluator, and project website. Existing tags and past releases remain available here.

<p align="center">
  <a href="https://freedomintelligence.github.io/OmniDentBench/"><img src="https://freedomintelligence.github.io/OmniDentBench/images/logo.png" alt="OmniDentBench logo" width="112"></a>
</p>

<h1 align="center">OmniDentBench</h1>

<p align="center"><strong>A multilingual, multimodal benchmark for dental AI reasoning</strong></p>

<p align="center">
  <a href="https://freedomintelligence.github.io/OmniDentBench/">Project website</a> ·
  <a href="#quick-start">Quick start</a> ·
  <a href="data">Dataset</a> ·
  <a href="#institutions-and-team">Institutions &amp; team</a> ·
  <a href="#citation-and-licensing">Citation &amp; licensing</a>
</p>

<p align="center">
  <a href="https://github.com/FreedomIntelligence/OmniDentBench-Benchmark/stargazers"><img src="https://img.shields.io/github/stars/FreedomIntelligence/OmniDentBench-Benchmark?style=social" alt="GitHub stars"></a>
</p>

OmniDentBench (ODB) evaluates how AI models reason through dental questions across **12 specialties** and **8 languages**. Of its **1,178 items**, **1,099** use figures. The release includes the dataset, reference answers, scoring rubrics, and an evaluator for reproducible model comparisons.

| Question format | Items | Evaluation |
| --- | ---: | --- |
| Exact answer | 605 | Objective scoring |
| Multiple choice | 108 | Objective scoring |
| Open-ended | 465 | Weighted, item-specific rubrics with safety red flags |

## Institutions and team

OmniDentBench brings together dental clinicians and researchers. The [official project website](https://freedomintelligence.github.io/OmniDentBench/) lists the following institutions as project partners and identifies the project team by role.

<p align="center">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/CUHK.webp" alt="The Chinese University of Hong Kong, Shenzhen" width="112">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/HKU.webp" alt="Faculty of Dentistry, The University of Hong Kong" width="112">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/peking-university.webp" alt="Peking University" width="112">
</p>
<p align="center">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/the-prince-philip-dentap-hospital.webp" alt="The Prince Philip Dental Hospital" width="112">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/mayo-clinic-logo.webp" alt="Mayo Clinic" width="112">
<img src="https://freedomintelligence.github.io/OmniDentBench/images/logo/lmu-klinikum-logo.webp" alt="Ludwig-Maximilians-Universität München Klinikum (LMU Klinikum)" width="112">
</p>

<details>
<summary>View all 16 partner institutions</summary>

- The Chinese University of Hong Kong, Shenzhen
- Faculty of Dentistry, The University of Hong Kong
- Freedom AI
- Peking University
- Peking-Tsinghua Center for Life Sciences
- Peking University National Biomedical Imaging Center
- The Prince Philip Dental Hospital
- Mayo Clinic
- Ludwig-Maximilians-Universität München Klinikum (LMU Klinikum)
- SEGi University & Colleges
- National Hospital Abuja
- College of Medicine, University of Lagos (CMUL)
- Bayero University Kano
- Usmanu Danfodiyo University Sokoto
- University of Maiduguri
- Madda Walabu University

</details>

### Steering chairs

| Junwen Wang | Zuolin Jin | Benyou Wang |
| :---: | :---: | :---: |
| <img src="https://freedomintelligence.github.io/OmniDentBench/images/team/team-059-junwen-wang.webp" alt="Junwen Wang" width="84"> | <img src="https://freedomintelligence.github.io/OmniDentBench/images/team/team-060-zuolin-jin.webp" alt="Zuolin Jin" width="84"> | <img src="https://freedomintelligence.github.io/OmniDentBench/images/team/team-061-benyou-wang.webp" alt="Benyou Wang" width="84"> |

<details>
<summary>View the full project team (74 listed members)</summary>

**Steering chairs (3)**

Junwen Wang · Zuolin Jin · Benyou Wang

**Steering committee members (8)**

Liangyi Chen · Walter Yu Hang Lam · Will Wei Qiao · John Adeoye · Shan Zhiyi · Teddy Weifa Yang · Xin Li · Zhongyuan Tang

**Steering committee student members (5)**

Junjie Zhao · Ziying Sheng · Jiajun You · Zhenyang Cai · Zhou Su

**Specialty chairs (12)**

Ming Zhong · Dayong Liu · Hui Zhang · Mingming Xu · Qing Liu · Weihua Cai · Xiaojing Wang · Yanning Ma · Shan Jiang · Feng Wang · Kun Qi · Yancheng Fang

**Specialty committee members (46)**

Bing Liu · Daheng Li · Dongfei Wang · Fangjie Zhou · Fen Liu · Forest Cheng · Fujia Kang · Hao Chunxiu · Jiamin Zhao · Jiaming Zhang · Jinwen Liu · Jinyan Chen · Junting Wang · Kuan Yang · Lei Shi · Lin Zhao · MAO Yilin · Menghong Li · Mengmeng Song · Min Huang · Minghui Wei · Mingxin Zhang · Patricia Ho · Peijuan Wang · Peng Chen · Rui Lu · Shiduo Sun · Shirong He · Shixin Zhang · Shuwei Huang · Siqi Qiu · Tai Pak Chuen Patrick · Wu Songying · XU Leyao · Xiangjie Jin · Xue Qiao · Yang Jiang · Yaqiu Zhang · Yefeng Wu · Yidan Guo · Yifan Zheng · Ying Wang · Yujia Wu · Zhenlai Zhu · Zhiqiang Deng · Zhuoying Li

</details>

## Quick start

Requires **Python 3.10+**. Run these commands from the repository root.

```sh
git clone https://github.com/FreedomIntelligence/OmniDentBench-Benchmark.git
cd OmniDentBench-Benchmark
python3 -m venv .venv
. .venv/bin/activate
python -m pip install -r requirements.txt
python -m unittest discover -s tests -v
```

Copy [`.env.example`](.env.example) to `.env` and configure the API bases and keys for the target model and judge. Both endpoints must support OpenAI-compatible Chat Completions with JSON output. The target model must accept images for multimodal items.

```sh
cp .env.example .env
# Set the API bases and keys in .env, then load it.
. ./.env
python -m evaluation --language en --model YOUR_MODEL_ID --judge deepseek-flash \
  --limit 3 --output runs/smoke
```

Set `--judge` to the model ID at your judge endpoint. Remove `--limit 3` for a full run and use a new output directory for each run. Use `--text-only` to evaluate the 79 items without figures, or pass `--model-options options.json` for model-specific settings such as `{"reasoning_effort":"medium"}`.

<details>
<summary>Supported languages and CLI values</summary>

| Language | CLI value | Language | CLI value |
|---|---|---|---|
| English | `en` | Simplified Chinese | `zh-CN` |
| Traditional Chinese (Hong Kong) | `zh-HK` | Spanish | `es` |
| French | `fr` | German | `de` |
| Japanese | `ja` | Modern Standard Arabic | `ar` |

</details>

## Dataset and scoring

Each `data/<language>/items.json` contains questions, answer options, reference answers, scoring rubrics and image references. Experts reviewed translations for a shared sample of 118 items.

The repository includes all figures for the 1,099 image-supported items. The figure manifest maps images to source articles and lists licences where available. Consult the original article for figure-specific credits and reuse terms. Some images retain their original embedded metadata. [Figure manifest](data/figures.csv) · [Source articles](data/sources.csv)

<details>
<summary>Scoring, failure handling, and run outputs</summary>

The judge grades both objective formats as 0 or 100. The objective mean on this scale is percentage accuracy. For open-ended items the evaluator combines the judge's criterion scores using the item-specific rubric weights. A triggered safety red flag sets the final item score to zero.

`scores.jsonl` contains one record per selected item. `summary.json` reports separate objective and open-ended means, selected denominators, valid answer counts, successfully judged counts and failure counts. Invalid or blocked target-model answers receive zero and stay in the selected denominator. Missing or corrupt figures and failed judgments leave the item score unresolved and the affected group mean unavailable. Unassessed red flags remain unknown. Authentication or service configuration failures stop the run. A run that stops before completion has no final summary.

`manifest.json` records the language, item selection, and model and judge settings. Include these details and the item denominator when reporting scores.

</details>

<details>
<summary>Repository layout</summary>

```text
OmniDentBench-Benchmark/
├── data/
│   ├── <language>/items.json   # Benchmark items for each language
│   ├── images/                # Shared figures
│   ├── figures.csv            # Figure sources and licences
│   └── sources.csv            # Source articles and attribution
├── evaluation/                # Model inference, judging and scoring
└── tests/                     # Offline tests
```

</details>

## Citation and licensing

The evaluation code is available under the [MIT License](LICENSE). Original benchmark content for which the OmniDentBench contributors hold licensing rights is available under [CC BY 4.0](data/LICENSE). Third-party figures and other source material retain their applicable terms. Use the figure manifest and the source article to verify attribution and reuse rights.

Cite *OmniDentBench (ODB)* with the release tag or Git commit you used.

If OmniDentBench helps your research or model evaluation, [star the repository](https://github.com/FreedomIntelligence/OmniDentBench-Benchmark) to follow updates and help others discover it. For questions, reproducibility reports, or feedback, [open a GitHub issue](https://github.com/FreedomIntelligence/OmniDentBench-Benchmark/issues).
