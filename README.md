<br>

<samp>NW &nbsp;/&nbsp; ENGINEERING NOTEBOOK &nbsp;/&nbsp; 2026</samp>

# Nikhil Wakode

<samp>AI ENGINEER &nbsp;·&nbsp; FULL-STACK BUILDER &nbsp;·&nbsp; PRODUCT ENGINEER</samp>

<br>

> I build AI systems, the backends they run on,
> and the products that make them worth using.

<br>

<sub><samp><a href="https://github.com/NikhilNWakode">GITHUB</a> &nbsp;&nbsp;/&nbsp;&nbsp; <a href="mailto:wakode333nikhil@gmail.com">EMAIL</a> &nbsp;&nbsp;/&nbsp;&nbsp; <a href="YOUR_LINKEDIN_URL">LINKEDIN</a></samp></sub>

<br>
<br>

---

<sub><samp>01 / IDENTITY</samp></sub>

### Most ideas arrive half-formed. I like that stage.

I start where the problem is still vague and work toward something that runs.
Along the way I try to understand each layer I touch — the retrieval step,
the database, the API, the part the user actually sees.

My work sits between AI engineering and backend systems. Calling a model is
the easy part. The hard part is everything around it: what gets retrieved,
how results get ranked, what gets cached, what breaks with real data, and
how you'd know.

I learn by building. Most of what I know came from a system that didn't work
the first time.

<br>

---

<sub><samp>02 / CURRENT FOCUS</samp></sub>

### What happens when AI leaves the demo.

```text
RETRIEVAL      hybrid search, fusion, reranking
MULTIMODAL     image + text in one retrieval space
AGENTS         tool use, control flow, failure modes
EVALUATION     measuring whether any of it is right
SYSTEMS        APIs, caching, async work, data models
```

<br>

---

<sub><samp>03 / SELECTED WORK</samp></sub>

<br>

## MedVisionAI

<samp>MULTIMODAL AI &nbsp;·&nbsp; HYBRID RAG &nbsp;·&nbsp; MEDICAL IMAGING</samp>

A full-stack system that takes medical images and clinical questions and
answers them with grounded, cited context. Images are embedded with
BiomedCLIP; text is searched two ways — dense and lexical — then fused,
reranked by an LLM, and turned into chat responses or structured reports
that export as HL7 FHIR R4. I built it to understand what happens beyond
simply calling an LLM API.

```text
 DICOM / IMAGE                QUESTION
      │                          │
      ▼                  ┌───────┴───────┐
  BiomedCLIP             ▼               ▼
      │              BGE dense       BM25 sparse
      │                  │               │
      └──────┬───────────┘               │
             ▼                           │
          QDRANT                         │
             │                           │
             └────────────┬──────────────┘
                          ▼
               RECIPROCAL RANK FUSION
                          │
                          ▼
                     LLM RERANK
                          │
                          ▼
                GROUNDED GENERATION
                          │
            ┌─────────────┼─────────────┐
            ▼             ▼             ▼
          CHAT         REPORT        FHIR R4

 PostgreSQL · records          Redis · cache
```

<samp>BUILT WITH</samp>

<samp>BiomedCLIP · BGE · BM25 · RRF · Qdrant · PostgreSQL · Redis · FastAPI · DICOM · HL7 FHIR R4 · Docker</samp>

<samp>WHAT I EXPLORED</samp>

- Why dense retrieval alone misses exact clinical terms, and where BM25 recovers them.
- Fusing ranked lists with RRF instead of tuning fragile score weights.
- Spending an LLM call on reranking only after cheap retrieval has narrowed the field.
- Putting image and text embeddings behind a single retrieval interface.
- Emitting output in a real interoperability standard, not just prose.

<samp><a href="https://github.com/NikhilNWakode/MedVisionAI">→ VIEW PROJECT</a></samp>

<br>
<br>

## GitWorth

<samp>FICTIONAL APPRAISAL ENGINE &nbsp;·&nbsp; GITHUB PROFILES</samp>

A financial appraisal for your GitHub profile — valuation, rank, a written
assessment, and a roast. It is a joke with a serious spine: the number comes
from a deterministic model, not from an LLM's mood. Language models only
write about a valuation that has already been decided.

```text
 GITHUB PROFILE
      │
      ▼
 SIGNAL EXTRACTION
      │
      ▼
 DETERMINISTIC VALUATION   same input, same number
      │
      ▼
 RANK
      │
      ├──────────────┐
      ▼              ▼
 APPRAISAL         ROAST
      │              │
      └──────┬───────┘
             ▼
     SHAREABLE RESULT
```

<samp>WHAT I EXPLORED</samp>

- Turning noisy public activity into signals that can be scored.
- Keeping the score reproducible, and the LLM downstream of it.
- Writing one result in two voices: the appraiser and the critic.
- Designing an output people actually want to share.

<samp><a href="https://github.com/NikhilNWakode/GitWorth">→ VIEW PROJECT</a></samp>

<br>

---

<sub><samp>04 / HOW I BUILD</samp></sub>

### Problem first. Tools last.

```text
 problem → understand → prototype → build → measure
    ▲                                         │
    └──────────────── iterate ◄───────────────┘
```

I pick the technology after I know what the system has to do.
I prototype early because the first version is mostly a way to find the real
questions. And I measure before I believe anything — a retrieval pipeline
that feels right is not the same as one that is.

<br>

---

<sub><samp>05 / ENGINEERING STACK</samp></sub>

```text
AI / ML
  Python · LLMs · RAG · embeddings · BM25
  reranking · BiomedCLIP · Groq

BACKEND / DATA
  FastAPI · Node.js · Java · Spring Boot
  PostgreSQL · Redis · Qdrant

FRONTEND
  React · Next.js · TypeScript · Tailwind

INFRASTRUCTURE
  Docker · GitHub Actions · Git
```

<br>

---

<sub><samp>06 / EXPERIENCE</samp></sub>

<br>

**Software Developer Intern**<br>
<samp>TRIPFACTORY &nbsp;·&nbsp; JAN 2026 — APR 2026</samp>

- Built an LLM classification pipeline for support tickets across 46 issue categories.
- Compared Groq-hosted models with Qwen2.5 and Phi-3-mini for accuracy, speed and cost.
- Added PII anonymization before any ticket text reached a model.
- Built semantic issue analysis to group recurring problems.
- Wrote supplier risk scoring and the escalation workflows that act on it.
- Built JWT authentication and authorization in Java / Spring Boot, and debugged legacy enterprise APIs.

> Real data is where AI systems stop being clean. Most of the work was there.

<br>

---

<sub><samp>07 / PRINCIPLES</samp></sub>

<samp>i.</samp> &nbsp; Build before you overthink.<br>
<samp>ii.</samp> &nbsp; Understand the abstraction before depending on it.<br>
<samp>iii.</samp> &nbsp; A working system teaches more than a perfect plan.<br>
<samp>iv.</samp> &nbsp; If you can't explain the architecture, you don't own it.<br>
<samp>v.</samp> &nbsp; The model is one component. Treat it like one.

<br>

---

<sub><samp>08 / ACTIVITY</samp></sub>

<br>

<img src="https://github-readme-stats.vercel.app/api?username=NikhilNWakode&show_icons=true&hide_border=true&hide_rank=true&hide_title=true&bg_color=0A0A0A&text_color=A8A8A8&icon_color=B8A47A&title_color=F3F0E8" height="140" alt="GitHub stats" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=NikhilNWakode&bg_color=0A0A0A&color=A8A8A8&line=B8A47A&point=F3F0E8&area=false&hide_border=true&hide_title=true&custom_title=%20" width="100%" alt="Contribution graph" />

<br>

---

<sub><samp>09 / CONTACT</samp></sub>

### If you're working on retrieval, agents, or AI products that need real engineering underneath — write to me.

<samp><a href="mailto:wakode333nikhil@gmail.com">wakode333nikhil@gmail.com</a></samp>

<br>

<sub><samp>NW &nbsp;—&nbsp; END OF FILE</samp></sub>
