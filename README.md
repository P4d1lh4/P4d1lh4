<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,100:6a0dad&height=190&text=Arthur%20Padilha&fontColor=FFFFFF&fontSize=46&fontAlignY=36&desc=Front-end%20Developer%20%C2%B7%20Software%20for%20healthcare&descSize=17&descAlignY=57&animation=fadeIn" width="100%" alt="Arthur Padilha, Front-end Developer"/>
</p>

<p align="center">
  <b>Front-end Developer at Seaway</b> · B.Sc. in Computer Science, CESAR School (2026) · Recife, Brazil
</p>

<p align="center">
  <a href="https://p4d1lh4.github.io/portfolio-arthur"><img src="https://img.shields.io/badge/Portfolio-0f172a?style=for-the-badge&logo=github&logoColor=white" alt="Portfolio"/></a>
  <a href="https://www.linkedin.com/in/arthur-ppadilha/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:arthur.ppadilha09@gmail.com"><img src="https://img.shields.io/badge/Email-6a0dad?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

<p align="center">
  <a href="#-spotlight-health-project">Spotlight</a> ·
  <a href="#-more-projects">Projects</a> ·
  <a href="#-stack">Stack</a> ·
  <a href="#-experience">Experience</a> ·
  <a href="#-education">Education</a>
</p>

## 👋 About

- I build and maintain production web apps with **React, Next.js, TypeScript and Node.js**. At Seaway I own the front-end of the main product: routing refactor, code splitting and memoization cut the LCP from 4.1s to 2.4s.
- I care about **software for healthcare**. My thesis was a heuristic evaluation (Nielsen) of a public health app on Android and iOS, and I have been building the AI service of a digital death-certificate proposal for the Brazilian public health system (SUS).
- I like putting **LLMs to practical use**: structured outputs, multimodal analysis and agents wired into real back-ends (FastAPI, NestJS).

## ⭐ Spotlight: health-project

<table>
  <tr>
    <td width="58%" valign="top">
      <h3><a href="https://github.com/P4d1lh4/health-project">health-project</a></h3>
      <p><b>Predicting 30-day hospital readmission</b> for diabetic patients, from raw data to a decision a care team can act on. Built on the UCI <i>Diabetes 130-US hospitals</i> dataset.</p>
      <ul>
        <li><b>Pipeline</b>: cohort building, feature engineering and model selection (Logistic Regression, Random Forest, XGBoost) with cross-validation grouped by patient, so no patient appears in both train and test.</li>
        <li><b>API</b>: FastAPI <code>/predict</code> endpoint with input validation and a saved decision threshold.</li>
        <li><b>Dashboard</b>: Streamlit app with five views, from where readmission concentrates to how many cases a team finds per thousand discharges at a given follow-up capacity.</li>
        <li><b>Explainability</b>: calibration curve, threshold analysis and SHAP, in notebooks committed with their outputs.</li>
      </ul>
      <p>
        <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
        <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn"/>
        <img src="https://img.shields.io/badge/XGBoost-0f172a?style=flat-square" alt="XGBoost"/>
        <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
        <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
        <img src="https://img.shields.io/badge/SHAP-6a0dad?style=flat-square" alt="SHAP"/>
        <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest"/>
      </p>
      <p><a href="https://github.com/P4d1lh4/health-project"><b>View the repository →</b></a></p>
    </td>
    <td width="42%" valign="top">
      <h3>Results on the held-out test set</h3>
      <table>
        <tr><td>Encounters</td><td align="right"><b>99,343</b></td></tr>
        <tr><td>Patients</td><td align="right"><b>69,990</b></td></tr>
        <tr><td>Winning model</td><td align="right"><b>XGBoost</b></td></tr>
        <tr><td>ROC-AUC</td><td align="right"><b>0.680</b></td></tr>
        <tr><td>PR-AUC (prevalence 0.111)</td><td align="right"><b>0.238</b></td></tr>
        <tr><td>Brier score</td><td align="right"><b>0.093</b></td></tr>
        <tr><td>Recall at the chosen threshold</td><td align="right"><b>0.472</b></td></tr>
      </table>
      <p><sub>ROC-AUC between 0.64 and 0.68 is typical for this dataset. The model ranks risk better than chance but does not separate cases cleanly, and the README says so: a score well above 0.72 here would point to leakage.</sub></p>
    </td>
  </tr>
</table>

## 🚀 More projects

| Project | What it does | Stack | Links |
| --- | --- | --- | --- |
| **Nielsen Analytics** | CLI that drives a headless browser through a flow, captures screenshot + accessibility tree + DOM per step, and has a multimodal LLM produce a Nielsen / WCAG 2.1 audit with severity, element selector and suggested fix. | TypeScript, Playwright, Anthropic API, Zod | [repo](https://github.com/P4d1lh4/Nielsen-analytics) |
| **Portal Professor** | Academic portal for grades and attendance with three roles (admin, coordinator, teacher), Row Level Security on PostgreSQL, audit trail and CI-enforced test coverage. | React, TypeScript, FastAPI, Supabase, Docker, GitHub Actions | [repo](https://github.com/P4d1lh4/Portal-Professor) · [live](https://portalprofessor.vercel.app) |
| **e-DO AI Engine** | AI service for a digital death-certificate system for SUS: natural-language ICD-11 search, causal-chain validation with clinical rules, Gemini-powered assistant. Part of a public-health initiative with a small team. | Python, FastAPI, RapidFuzz, Gemini API, pytest | private |
| **Mirai** | Conversational personal shopper: LLM recommendations with real-time price lookup. | Next.js, FastAPI, Groq API, SerpApi, Docker | [repo](https://github.com/P4d1lh4/Mirai-Compra-Inteligente) |

## 🛠 Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=react,nextjs,typescript,js,html,css,tailwind,nodejs,python,fastapi,flask,sklearn,java,postgres,prisma,supabase,docker,githubactions,git,github&theme=dark&perline=10" alt="React, Next.js, TypeScript, JavaScript, HTML, CSS, Tailwind, Node.js, Python, FastAPI, Flask, scikit-learn, Java, PostgreSQL, Prisma, Supabase, Docker, GitHub Actions, Git, GitHub"/>
</p>

## 💼 Experience

| Period | Role |
| --- | --- |
| Jul 2025 – present | **Front-end Developer**, Seaway — sole owner of the main app's front-end; 58 releases, a 25-component UI library, performance work in React. |
| May – Jun 2025 | **Full Stack Intern**, WebStar — REST endpoints in Node.js over PostgreSQL, API contracts consumed by React. |
| Feb – Jun 2023 | **Teaching Assistant**, Porto Digital (NExT) — Python fundamentals for a class of 10. |

## 🎓 Education

**B.Sc. in Computer Science** — CESAR School, Recife. Graduated June 2026.
Thesis: heuristic evaluation of a public health app on Android and iOS, usability issues ranked by severity under Nielsen's heuristics. Grade 10/10.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:6a0dad,100:0f172a&height=100&section=footer" width="100%" alt=""/>
</p>
