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
  <a href="#-spotlight-readmissao-sus">Spotlight</a> ·
  <a href="#-more-projects">Projects</a> ·
  <a href="#-stack">Stack</a> ·
  <a href="#-experience">Experience</a> ·
  <a href="#-education">Education</a>
</p>

## 👋 About

- I build and maintain production web apps with **React, Next.js, TypeScript and Node.js**. At Seaway I own the front-end of the main product: routing refactor, code splitting and memoization cut the LCP from 4.1s to 2.4s.
- I care about **software for healthcare**. My thesis was a heuristic evaluation (Nielsen) of a public health app on Android and iOS, and my recent projects work with public health data: readmission prediction on SUS records with FHIR output, and drug-safety signal detection on FDA reports.
- I like putting **LLMs to practical use**: structured outputs, multimodal analysis and agents wired into real back-ends (FastAPI, NestJS).

## ⭐ Spotlight: readmissao-sus

<table>
  <tr>
    <td width="58%" valign="top">
      <h3><a href="https://github.com/P4d1lh4/readmissao-sus">readmissao-sus</a></h3>
      <p><b>Predicting unplanned 30-day hospital readmission</b> with public data from the Brazilian public health system (SIH/SUS, Pernambuco, 2023–2024), and turning each discharge into a FHIR document following the national (RNDS) profiles.</p>
      <ul>
        <li><b>Data</b>: hospital records downloaded from the DATASUS FTP, stored as Parquet and assembled in DuckDB with versioned SQL. The same person is linked across admissions without any national ID, through a key stored only as a salted hash.</li>
        <li><b>Model</b>: Logistic Regression, Random Forest and XGBoost, trained on 2023 and tested on 2024, with cross-validation grouped by person and a leakage investigation on every run.</li>
        <li><b>Hospitals</b>: observed/expected readmission ratio per hospital from a risk-adjustment model, with exact 95% Poisson intervals.</li>
        <li><b>Interoperability</b>: each discharge becomes a FHIR R4 discharge summary, checked locally with the official HL7 validator in Docker and served with the risk by a FastAPI endpoint.</li>
      </ul>
      <p>
        <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
        <img src="https://img.shields.io/badge/DuckDB-FFF000?style=flat-square&logo=duckdb&logoColor=black" alt="DuckDB"/>
        <img src="https://img.shields.io/badge/XGBoost-0f172a?style=flat-square" alt="XGBoost"/>
        <img src="https://img.shields.io/badge/FHIR_R4-E34F26?style=flat-square" alt="FHIR R4"/>
        <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
        <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
        <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
        <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest"/>
      </p>
      <p><a href="https://github.com/P4d1lh4/readmissao-sus"><b>View the repository →</b></a></p>
    </td>
    <td width="42%" valign="top">
      <h3>Results on 2024, a year the model never saw</h3>
      <table>
        <tr><td>Discharges (2023–2024)</td><td align="right"><b>940,139</b></td></tr>
        <tr><td>Unplanned 30-day readmission</td><td align="right"><b>5.5%</b></td></tr>
        <tr><td>Test discharges</td><td align="right"><b>420,746</b></td></tr>
        <tr><td>ROC-AUC</td><td align="right"><b>0.79</b></td></tr>
        <tr><td>Mean calibration error</td><td align="right"><b>0.4 pp</b></td></tr>
        <tr><td>Hospitals compared</td><td align="right"><b>193</b></td></tr>
        <tr><td>FHIR bundles valid</td><td align="right"><b>20 / 20</b></td></tr>
      </table>
      <p><sub>The first model scored 0.84, which was too good. The excess came from scheduled returns and administrative records from the same hospital; removing them from the target gave the honest 0.79.</sub></p>
    </td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <a href="https://github.com/P4d1lh4/readmissao-sus#hospitais-razão-observadoesperado"><img src="https://raw.githubusercontent.com/P4d1lh4/readmissao-sus/main/docs/img/dashboard-hospitais.jpg" width="100%" alt="readmissao-sus dashboard: observed/expected readmission ratio per hospital with 95% confidence intervals"/></a>
      <br/>
      <sub>Observed/expected readmission ratio per hospital, with 95% CI: orange above expected, blue below, grey compatible.</sub>
    </td>
  </tr>
</table>

## 🚀 More projects

| Project | What it does | Stack | Links |
| --- | --- | --- | --- |
| **farmacovigilancia** | Adverse-event signal detection for GLP-1 agonists (semaglutide, tirzepatide and others) in 1.5 million deduplicated FDA FAERS reports: free-text drug names normalized (0.0019% unmapped), PRR, ROR and χ² computed in SQL and checked against SciPy, and a Streamlit dashboard with a forest plot. Recovers known signals such as pancreatitis and GI events. | Python, DuckDB, RapidFuzz, RxNav API, Streamlit, pytest | [repo](https://github.com/P4d1lh4/farmacovigilancia) |
| **health-project** | First version of the readmission work, on the UCI *Diabetes 130-US hospitals* dataset: model selection with cross-validation grouped by patient, calibrated XGBoost (ROC-AUC 0.68), FastAPI `/predict`, a five-tab Streamlit dashboard and SHAP notebooks. | Python, scikit-learn, XGBoost, SHAP, FastAPI, Streamlit | [repo](https://github.com/P4d1lh4/health-project) |
| **Nielsen Analytics** | CLI that drives a headless browser through a flow, captures screenshot + accessibility tree + DOM per step, and has a multimodal LLM produce a Nielsen / WCAG 2.1 audit with severity, element selector and suggested fix. | TypeScript, Playwright, Anthropic API, Zod | [repo](https://github.com/P4d1lh4/Nielsen-analytics) |

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
