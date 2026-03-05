# Video Understanding AI Hackathon at Northeastern - April 3, 2026

Repo and Resources for the Video Understanding AI Hackathon at Northeastern. If you haven't already, you can register [here](https://voxel51.com/events/video-understanding-ai-hackathon-at-northeastern-april-3-2026).

![image](ne_hackathon.avif)

[![Join us on Discord](https://img.shields.io/badge/Discord-Join%20Community-7289da?style=flat&logo=discord&logoColor=white)](https://discord.com/invite/fiftyone-community)


## What This Hackathon Is About

This hackathon is inspired by the [CV4Smalls](https://coe.northeastern.edu/event/3rd-cv4smalls-workshop-computer-vision-with-small-data-beyond-scale-toward-data-efficient-dynamically-aware-video-intelligence/) workshop series. 

This workshop is where computer vision meets small data in domains that matter: elderly care, infant monitoring, wildlife conservation, clinical settings, and beyond. 

The recurring lesson from CV4Smalls is that **data curation beats model complexity**. 

The [winning submission](https://arxiv.org/abs/2503.07821) in the 2025 Elderly Action Recognition Challenge didn't use a novel architecture, it used a 2019-era efficient model (TSM) and won by carefully selecting which training data to include. 

Synthetic dog renders from GTA V [outperformed real-data methods](https://github.com/mshooter/DigiDogs_release) for 3D pose estimation. 

A [drone-to-behavior pipeline](https://github.com/dirtmaxim/kabr) turned raw Kenyan wildlife footage into usable action recognition data through smart preprocessing alone.

#### Your job today

Build a [FiftyOne plugin](https://docs.voxel51.com/plugins/index.html) that leverages [Twelve Labs](https://docs.twelvelabs.io/) video understanding models (Marengo embeddings and/or Pegasus video-language generation) to solve a real problem in video understanding.

*Especially in domains where labeled data is scarce and the stakes are high.*

## Schedule

| Time | Activity |
|---|---|
| 10:00 AM | Welcome |
| 10:15 AM | Find teammates |
| 10:30 AM | Introduction to the hackathon |
| 10:45 AM | Introduction to FiftyOne |
| 11:00 AM | Using Twelve Labs Models |
| 11:15 AM | Hands-on with Twelve Labs + FiftyOne |
| 11:45 AM | Define your use case |
| 12:00 PM | Catered Lunch 🍕 |
| 12:30 PM | Hacking! |
| | *By ~1:00 PM* — Dataset loaded in FiftyOne, Twelve Labs API calls working in a notebook |
| | *By ~2:00 PM* — Core logic working (embeddings computed, Pegasus calls returning results, etc.) |
| | *By ~2:30 PM* — Start wrapping your logic into a plugin (`fiftyone.yml` + `__init__.py`) |
| 3:00 PM | **First push to GitHub** — repo with working plugin, even if rough |
| | *3:00–4:30 PM* — Polish: handle edge cases, add progress bars, clean up the UI |
| | *4:30–5:00 PM* — Write your README, record a quick demo GIF if you can |
| 5:00 PM | **Final push to GitHub** — judging begins |


## What Success Looks Like

You don't need to train a model. 

You don't need a perfect system. 

You need a working FiftyOne plugin that demonstrates a thoughtful approach to video understanding using Twelve Labs' APIs. 

Concretely, a strong submission:

- **Solves a real problem.** It addresses a genuine challenge in video understanding. Whether that's curating training data, annotating behavior, finding anomalies, bridging domain gaps, or something we haven't thought of.

- **Uses data intentionally.** Inspired by CV4Smalls, the best plugins will show that *how* you work with data matters more than how much of it you have. Filtering, clustering, comparing, summarizing, use better data to win.

- **Ships as a plugin.** At minimum: a `fiftyone.yml`, an `__init__.py` with at least one working operator, and a README that explains what it does and how to use it. Pushed to GitHub by 5 PM.

- **Leans on Twelve Labs.** Uses Marengo embeddings for semantic search/clustering/similarity, Pegasus for video-language generation/summarization/temporal grounding, or both.

- **Could actually be used.** The best plugins are ones a researcher or practitioner in an underserved CV domain could install and get value from without writing code.


## Awards

Each category winner receives a **$100 Amazon gift card**.

| Award | What it means |
|---|---|
| 🏆 **Grand Prize — Overall Champion** | Best plugin across the board: idea, execution, and presentation. |
| 🧹 **Best Data Curation Plugin** | In the spirit of CV4Smalls: the plugin that best demonstrates that *how* you work with data matters more than how much of it you have. |
| 🚀 **Most Deployable** | A plugin someone could actually `fiftyone plugins download`, install, and get value from today. Clean code, clear README, real utility. |
| 🤡 **Least Useful (But Hilarious)** | Does it work? Technically. Should it exist? Debatable. Did it make the judges laugh? Absolutely. |


## Installation

You'll need **Python 3.9–3.12** and a **Twelve Labs API key** ([sign up free here](https://docs.twelvelabs.io/docs/advanced/organizations/users-guide#create-api-keys)).

```bash
pip install fiftyone twelvelabs
```

If you plan to work with video datasets (you will), install [FFmpeg](https://ffmpeg.org/) as well.

To verify everything works:

```python
import fiftyone as fo
import fiftyone.zoo as foz

dataset = foz.load_zoo_dataset("quickstart-video")
session = fo.launch_app(dataset)
```

Set your Twelve Labs API key as an environment variable:

```bash
export TWELVELABS_API_KEY="<YOUR_API_KEY>"   # Mac/Linux
set TWELVELABS_API_KEY=<YOUR_API_KEY>        # Windows cmd
```

### Windows users

- Install Python from [python.org](https://www.python.org/downloads/) (64-bit), **not** from the Microsoft Store. Check "Add Python to PATH" during installation.

- If you get a `psutil.NoSuchProcessExists` error when importing FiftyOne, install the [64-bit Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist).

### Full docs and troubleshooting

For the complete installation guide, see the [FiftyOne installation docs](https://docs.voxel51.com/installation/index.html#fiftyone-installation). For Twelve Labs, see the [Python SDK quickstart](https://docs.twelvelabs.io/docs/quickstart).

If you run into any issues, just ask one of us. We'll get you sorted out.

## FiftyOne Crash Course

Work through these notebooks to get up to speed with FiftyOne and Twelve Labs:

[![](https://img.shields.io/badge/GitHub-FiftyOne_Video_Workshop-181717?logo=github)](https://github.com/harpreetsahota204/fiftyone_video_workshop) — Hands-on walkthrough of FiftyOne with video datasets

[![](https://img.shields.io/badge/GitHub-Visual_AI_Worker_Safety_Kit-181717?logo=github)](https://github.com/nathanchess/visual-ai-worker-safety-kit) — End-to-end example of FiftyOne + Twelve Labs on the Safe & Unsafe Behaviours dataset

The full FiftyOne docs are at [docs.voxel51.com](https://docs.voxel51.com).

The [User Guide](https://docs.voxel51.com/user_guide/index.html) and [Video Datasets](https://docs.voxel51.com/user_guide/using_datasets.html#video-datasets) sections are particularly relevant for today.


# Datasets

### Bring your own

You're welcome to use any dataset you like. It can be something you find online, something you record yourself, whatever fits your plugin idea. To get it into FiftyOne, see the [Importing Datasets guide](https://docs.voxel51.com/user_guide/import_datasets.html). For video specifically, check out these importers:

- [`VideoDirectory`](https://docs.voxel51.com/user_guide/import_datasets.html#videodirectory) — a folder of video files, no labels

- [`FiftyOneVideoLabelsDataset`](https://docs.voxel51.com/user_guide/import_datasets.html#fiftyonevideolabelsdataset) — video + per-frame JSON labels

- [`VideoClassificationDirectoryTree`](https://docs.voxel51.com/user_guide/import_datasets.html#videoclassificationdirectorytree) — videos organized into class folders

### Pre-parsed datasets on Hugging Face

We've prepared several video datasets that are already in FiftyOne format and can be loaded with a single command. To avoid download rate limits, we encourage you to [create a Hugging Face access token](https://huggingface.co/docs/hub/en/security-tokens) and log in:

```bash
pip install huggingface_hub
huggingface-cli login
```

Then load any dataset:

```python
import fiftyone as fo
from fiftyone.utils.huggingface import load_from_hub

dataset = load_from_hub("Voxel51/<dataset-name>")
session = fo.launch_app(dataset)
```

Here's what's available:

| Preview | Dataset | Samples | Description |
|---|---|---|---|
| <img src="assets/meva.gif" width="350"> | [![](https://img.shields.io/badge/🤗-MEVA_Drop_4-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/extended_video_activities_drop_4) | 201 | Multi-view surveillance clips (~5 min each, 1080p) from the MEVA dataset with MeVID person re-identification tracklets. 19 fixed cameras, scripted scenarios at a training facility. |
| <img src="assets/sav.gif" width="350"> | [![](https://img.shields.io/badge/🤗-SAM_Video_Subset51-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/segment_anything_video_subset51) | 51 | Subset of the Segment Anything Video (SA-V) dataset with per-frame object segmentation masks. Diverse real-world video scenes. |
| <img src="assets/action100m.gif" width="350"> | [![](https://img.shields.io/badge/🤗-Action100M_Tiny-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/action100m_tiny_subset) | 1K+ | Tiny subset of Action100M, a large-scale action recognition dataset with hierarchical Tree-of-Captions annotations describing activities at multiple granularity levels. |
| <img src="assets/qivd.gif" width="350"> | [![](https://img.shields.io/badge/🤗-QIVD-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/qualcomm-interactive-video-dataset) | 2,900 | Qualcomm Interactive Video Dataset for video QA. Each sample has a question, detailed answer, short answer, and timestamp. Covers 13 categories including action detection, object counting, OCR, and audio-visual reasoning. |
| <img src="assets/qevd.gif" width="350"> | [![](https://img.shields.io/badge/🤗-QEVD_Benchmark-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/qualcomm-exercise-video-dataset-benchmark) | 74 | Qualcomm Exercise Video Dataset — workout sessions (~2.5–3 min each) with temporal annotations for AI fitness coaching feedback: form corrections, exercise transitions, rep counting. |
| <img src="assets/egocentric.gif" width="350"> | [![](https://img.shields.io/badge/🤗-Egocentric_10K_Subset-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/Egocentric_10K_subset) | 51 clips/worker | Subset of Egocentric-10K: first-person video from head-mounted cameras worn by factory workers. Real manufacturing environments with hand-object interactions. |
| <img src="assets/safe_unsafe.gif" width="350"> | [![](https://img.shields.io/badge/🤗-Safe_Unsafe_Behaviours-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/Safe_and_Unsafe_Behaviours) | 691 | Workplace safety surveillance from a Turkish manufacturing facility. 8 behavior classes (4 safe, 4 unsafe): walkway violations, unauthorized interventions, forklift overloads, etc. 1080p, 24 FPS. |
| <img src="assets/webuot.gif" width="350"> | [![](https://img.shields.io/badge/🤗-WebUOT_238_Test-yellow?style=for-the-badge)](https://huggingface.co/datasets/Voxel51/WebUOT-238-Test) | 238 | Subset of WebUOT-1M, the largest underwater object tracking benchmark. 192K+ frames across 408 categories, 12 superclasses. Includes bounding boxes, language prompts, and 23 tracking attributes. |
## Twelve Labs

[Twelve Labs](https://www.twelvelabs.io/) builds video-native AI models trained to see, hear, and reason about video as a unified whole. You have access to two foundation models via the [Twelve Labs API](https://docs.twelvelabs.io):

**[Marengo 3.0](https://docs.twelvelabs.io/docs/guides/create-embeddings)** — Multimodal embedding model. Generates 512-d vectors in a shared space across video, audio, images, and text. Use it for semantic search, zero-shot classification, clustering, anomaly detection, and cross-modal retrieval. Videos up to 4 hours.

**[Pegasus 1.2](https://docs.twelvelabs.io/docs/concepts/models/pegasus)** — Video language model. Takes video in, produces text out. Use it for open-ended QA, summarization, timestamped chapter generation, temporal grounding ("when does X happen?"), and gist extraction (titles, topics, hashtags). Videos up to 1 hour.

```python
from twelvelabs import TwelveLabs

client = TwelveLabs(api_key="<YOUR_API_KEY>")
```

| Resource | Link |
|---|---|
| Quickstart | [docs.twelvelabs.io/docs/quickstart](https://docs.twelvelabs.io/docs/quickstart) |
| Python SDK | [github.com/twelvelabs-io/twelvelabs-python](https://github.com/twelvelabs-io/twelvelabs-python) |
| SDK Reference | [docs.twelvelabs.io/sdk-reference/python](https://docs.twelvelabs.io/sdk-reference/python) |
| Rate Limits | [docs.twelvelabs.io/docs/get-started/rate-limits](https://docs.twelvelabs.io/docs/get-started/rate-limits) |

# FiftyOne Plugins

Your hackathon submission is a FiftyOne plugin. 

A plugin is a Python package (at minimum a `fiftyone.yml` and `__init__.py`) that adds custom functionality to the FiftyOne App which are operators that users can invoke, panels that display interactive UI, or both.

To see what plugins look like in practice, browse the [plugin overview and gallery](https://docs.voxel51.com/plugins/index.html#). For a full walkthrough of the development process, see the [Developing Plugins guide](https://docs.voxel51.com/plugins/developing_plugins.html).

### Examples

These repos contain working examples you can reference (and steal from):

[![](https://img.shields.io/badge/GitHub-Operator_Examples-181717?logo=github)](https://github.com/voxel51/fiftyone-plugins/tree/main/plugins/operator-examples) — operators that add buttons, forms, and batch processing to the App

[![](https://img.shields.io/badge/GitHub-Panel_Examples-181717?logo=github)](https://github.com/voxel51/fiftyone-plugins/tree/main/plugins/panel-examples) — panels that render custom UI (Plotly charts, dashboards, media players, etc.)

[![](https://img.shields.io/badge/GitHub-Metric_Examples-181717?logo=github)](https://github.com/voxel51/fiftyone-plugins/tree/main/plugins/metric-examples) — custom evaluation metrics

[![](https://img.shields.io/badge/GitHub-Semantic_Video_Search-181717?logo=github)](https://github.com/danielgural/semantic_video_search) — a FiftyOne plugin for searching across any modality in your videos using Twelve Labs

[![](https://img.shields.io/badge/GitHub-Twelve_Labs_Databricks_Demo-181717?logo=github)](https://github.com/danielgural/fiftyone_twelvelabs_databricks_demo) — end-to-end demo of FiftyOne + Twelve Labs integration with Databricks

# Use AI to speed up development

You're encouraged to use AI coding tools. This is a hackathon, not a purity test. We have resources specifically for this:

[![](https://img.shields.io/badge/GitHub-FiftyOne_Skills-181717?logo=github)](https://github.com/voxel51/fiftyone-skills) — prompt-ready skill files that give AI assistants deep context on FiftyOne's codebase. 

The [![](https://img.shields.io/badge/GitHub-fiftyone--develop--plugin_Skill-181717?logo=github)](https://github.com/voxel51/fiftyone-skills/tree/main/skills/fiftyone-develop-plugin) skill is particularly useful — it teaches your AI assistant the plugin development patterns, file structure, and API conventions.

For a hands-on walkthrough of using Claude to build FiftyOne plugins from scratch, check out the [Vibe Coding Production-Ready CV Pipelines workshop recording](https://voxel51.com/events/vibe-coding-production-ready-computer-vision-pipelines-hands-on-workshop-march-18-2026).

## Additional resources

For a talk on how plugins bridge research and real-world deployment, watch Adonai Vera's talk *"Plugins as Products: Bringing Visual AI Research into Real-World Workflows with FiftyOne"* from our [March 5 meetup](https://voxel51.com/events/ai-ml-and-computer-vision-meetup-march-5-2026).

# Plugin Ideas

These are starting points, not assignments. Mix, remix, or ignore them entirely. 

The best hackathon projects are the ones that solve a problem *you* care about.

### 🔍 Smart Data Curator

**Problem:** You have a large pool of source videos and a small target dataset. Which source videos are most useful for training?

**Approach:** Use Twelve Labs Marengo embeddings to compute vector representations of both source and target videos. Cluster them, visualize the embedding space, and automatically rank/filter source samples by similarity to the target domain. Display results in a FiftyOne panel with an interactive plot.

**Why it matters:** The winning EAR challenge submission at CV4Smalls proved that *which* data you train on matters more than *how much* — a curated subset beat the full dataset by 5+ points.

**Try it with:** QIVD, Action100M Tiny, or any two datasets you want to compare.

---

### 🏷️ Zero-Shot Video Annotator

**Problem:** You have unlabeled video clips and a taxonomy of categories, but no time (or budget) to annotate by hand.

**Approach:** Feed each clip through Twelve Labs Pegasus to generate a natural-language description of what's happening. Then use Marengo text embeddings to compute similarity between the description and each category in your taxonomy. Assign the closest match as a label. Write the results back to FiftyOne as classification labels.

**Try it with:** Safe & Unsafe Behaviours (8 classes), QEVD Benchmark (exercise types), or your own unlabeled videos.

---

### 🔎 Natural Language Video Search

**Problem:** You want to find specific moments across a video dataset using plain English queries (no labels required).

**Approach:** Index your dataset with Twelve Labs Marengo, then build an operator that accepts a text query and returns the most relevant video segments ranked by cosine similarity. Display matched clips in the FiftyOne App with similarity scores.

**Try it with:** MEVA Drop 4 (multi-camera surveillance), Egocentric 10K (factory floor), or QIVD.

---

### ⏱️ Temporal Activity Summarizer

**Problem:** Long videos are hard to browse. You want an automatic chapter breakdown with descriptions.

**Approach:** Use Twelve Labs Pegasus to generate timestamped chapters and summaries for each video. Write the chapter boundaries back to FiftyOne as temporal detection labels, and display the full summary as sample-level metadata. Build a panel that shows a clickable timeline alongside the video player.

**Try it with:** MEVA Drop 4 (~5 min clips), QEVD Benchmark (workout sessions), or Egocentric 10K.

---

### 🚨 Anomaly Detector

**Problem:** You have hours of "normal" video and need to flag unusual events (without labeled examples of anomalies).

**Approach:** Compute Marengo embeddings for temporal segments of your videos. Build a baseline distribution from known-normal clips. Flag segments whose embeddings are far from the baseline (by cosine distance or z-score). Visualize flagged segments on a timeline in a FiftyOne panel.

**Try it with:** Safe & Unsafe Behaviours (safe clips as baseline, detect unsafe), Egocentric 10K (routine factory work), or MEVA Drop 4.

---

### 🐠 Embedding-Powered Re-Identification

**Problem:** You want to find the same object/animal/person across different video clips without a trained re-ID model.

**Approach:** Crop regions of interest (from existing bounding box annotations or a detector), embed each crop with Marengo, and find nearest neighbors across clips. Build an operator that takes a selected sample/frame and retrieves the most visually similar instances from the rest of the dataset.

**Try it with:** WebUOT-238 (underwater animals with bounding boxes + language prompts), MEVA Drop 4 (person tracklets across cameras).

---

### 📊 Video QA Evaluator

**Problem:** You want to evaluate how well a video-language model answers questions about video content.

**Approach:** Take a dataset with ground-truth question-answer pairs (like QIVD). Run each video + question through Twelve Labs Pegasus to generate a predicted answer. Use Marengo text embeddings to compute semantic similarity between predicted and ground-truth answers. Surface results in a FiftyOne panel — browse by question category, sort by similarity score, find failure modes.

**Try it with:** QIVD (2,900 samples with questions, answers, and 13 categories).

---

### 💡 General Tips

- **Start small.** Get a single operator working on 5 videos before scaling up.
- **Use `max_samples` when loading.** `load_from_hub("Voxel51/...", max_samples=20)` saves time while prototyping.
- **Lean on the Twelve Labs free tier.** 600 minutes of indexing is plenty for a demo-sized dataset.
- **A working demo beats a perfect architecture.** Ship something by 3 PM, polish until 5 PM.