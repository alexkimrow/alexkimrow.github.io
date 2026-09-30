# About Me

Software engineer and M.S. Computer Science student at Georgia Tech. I focus on AI agents that use the Model Context Protocol (MCP), and on the AWS systems those agents depend on.

An agent decides what to do next. MCP is how it discovers tools, passes context, and calls the systems it is allowed to use. The cloud side is AWS: queues, scheduled functions, object storage, and queryable datasets.

<div class="focus-grid">
<div class="focus-card">
<h3>AI agents and MCP</h3>
<p>Tool-using agents. The agent plans the step, MCP exposes the tool, and the call carries only the context that tool needs. That is the interface between the model and the systems it acts on.</p>
</div>
<div class="focus-card">
<h3>AWS</h3>
<p>Serverless and event-driven cloud. Lambda, EventBridge, SQS, Kinesis Firehose, S3, Glue, Athena, Step Functions, and CloudWatch. The weather pipeline below is the full path from ingest to dashboard.</p>
</div>
</div>

I am an engineer on [Reltio](https://www.reltio.com/)’s Cloud Data & AI Platform, a cloud system that supplies real-time enterprise data and business context for AI agents. Before that I was a data engineer on Divergent’s machine learning additive-manufacturing team, a machine learning engineer at Intext AI, and a graduate teaching assistant for Georgia Tech’s Machine Learning course, CS 7641.

---

## Technical Skills

**AI agents and MCP**  
Model Context Protocol (MCP) | Tool-using agents | LLMs | Context and tool design

**AWS**  
Lambda | EventBridge | SQS | Kinesis Firehose | S3 | Glue | Athena | Step Functions | CloudWatch

**Machine learning**  
Python | PyTorch | scikit-learn | Pandas | NumPy | Matplotlib | Seaborn | OpenCV

**Languages**  
Python | SQL | Java | JavaScript | C++

**Other cloud and data**  
Apache Spark | Azure | Microsoft Fabric | Power BI | Docker | FastAPI | REST | GraphQL | Node.js | MongoDB | MySQL

**Also**  
Master data management | MLOps | NLP | Computer vision

---

## Education

**Master of Science in Computer Science**  
Georgia Institute of Technology | Specialization: AI / Machine Learning

---

## Experience

Roles and dates follow my [LinkedIn](https://www.linkedin.com/in/alexkimro/).

**Engineer**  
[Reltio](https://www.reltio.com/) · Cloud Data & AI Platform | Jan 2025 – Present

- Engineer on the Cloud Data & AI Platform. The product is cloud infrastructure for real-time master data and business context that enterprise AI agents use.

**Graduate Teaching Assistant**  
[Georgia Institute of Technology](https://www.gatech.edu/) · Machine Learning, CS 7641 | Jan 2025 – Apr 2026 · Remote

- Teaching assistant for the graduate Machine Learning course, CS 7641.

**Machine Learning Engineer**  
[Intext AI](https://www.linkedin.com/company/intext-ai) | Jun 2025 – Aug 2025

- Machine learning engineering role at an early-stage AI company.

**Data Engineer**  
[Divergent](https://www.linkedin.com/company/divergenttechnologies) · Machine Learning Additive Manufacturing, Software | Jul 2024 – Nov 2024 · Los Angeles, California

- Data engineer on the machine learning additive-manufacturing software team at Divergent, a digital manufacturing company.

**Engineer**  
[FutureSoft, Inc.](https://www.linkedin.com/company/futuresoft-inc.) | Apr 2022 – Jun 2024 · Houston, Texas

- Software engineer at FutureSoft in Houston. The company builds terminal-emulation software.

**Junior Software Engineer**  
Things Above Apparel | Jan 2021 – Jan 2022

- Junior software engineer at Things Above Apparel.

---

# Projects

AWS is the cloud project. The other write-ups are applied machine learning, including a multi-model inspection pipeline. Each one links to the public repository.

---

[AWS Data Engineering Pipeline - Real-Time Weather Analytics](/awsdatapipeline)

Serverless analytics on AWS. EventBridge triggers Lambda, Kinesis Firehose lands records in S3, Glue catalogs and transforms them, Athena queries the result, and Step Functions runs the jobs. Grafana is the dashboard. CloudWatch holds the logs.

<img class="project-shot" src="/images/aws-pipeline.png" alt="AWS architecture diagram for the weather pipeline: Lambda, Kinesis Firehose, S3, Glue, Athena, and Grafana"/>

---

[Guaconomics - Avocado Price Predictor](/guaconomics)

Full-stack machine learning app. A Random Forest model trained on Hass Avocado Board data serves price predictions through a Flask API and a Next.js interface.

<img class="project-shot" src="/images/guaconomics.png" alt="Guaconomics screen for predicting avocado prices"/>

---

[Damage Detective - Generative AI House Inspection](/damagedetective)

Hacklytics 2024 project. A visual question-answering model describes the damage, then Llama-2 turns that context into a repair estimate. Two models, one handoff.

<img class="project-shot" src="/images/logo.png" alt="Damage Detective logo"/>

---

[Customer Segmentation - Online Retail K-Means](/customersegmentation)

Unsupervised segmentation of online retail customers with monetary value, recency, and frequency features.

<img class="project-shot" src="/images/customer-segments.png" alt="3D scatter plot of customer clusters by monetary value, frequency, and recency"/>

---

[Jireh - Family Budget Tracker](/jireh)

Expo and React Native app for logging family income and expenses, with running totals for income, spending, and balance.

<img class="project-shot" src="/images/jireh.jpg" alt="Jireh app icon"/>

---

### Earlier web apps

- [Minimalist E-commerce](https://github.com/alexkimrow/Minimalist-E-commerce) — React storefront. [Live demo](https://minimalist-e-commerce-ashen.vercel.app/)
- [Car Rental](https://github.com/alexkimrow/car-rental) — React and SCSS rental site. [Live demo](https://car-rental-sage.vercel.app/)
- [Netflix clone](https://github.com/alexkimrow/Netflix-clone) — React, Redux, Firestore, Google auth, and Stripe checkout
