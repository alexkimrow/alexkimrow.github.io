# About Me

Software engineer and M.S. Computer Science student at Georgia Tech. I build AI agents that use the Model Context Protocol (MCP), and the AWS systems those agents run on.

An agent chooses the next step. MCP is how it finds a tool, passes only the context that tool needs, and calls it. AWS holds the queues, scheduled jobs, files, and datasets behind that work.

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

I am an engineer on [Reltio](https://www.reltio.com/)’s Cloud Data & AI Platform. The product supplies real-time enterprise data and business context for AI agents.

Before that I was a data engineer on Divergent’s machine-learning manufacturing team, a machine learning engineer at Intext AI, and a teaching assistant for Georgia Tech’s Machine Learning course, CS 7641.

---

## Technical Skills

<div class="skill-group">
<h3>AI agents and MCP</h3>
<ul class="tags">
<li>Model Context Protocol (MCP)</li>
<li>Tool-using agents</li>
<li>LLMs</li>
<li>Context and tool design</li>
</ul>
</div>

<div class="skill-group">
<h3>AWS</h3>
<ul class="tags">
<li>Lambda</li>
<li>EventBridge</li>
<li>SQS</li>
<li>Kinesis Firehose</li>
<li>S3</li>
<li>Glue</li>
<li>Athena</li>
<li>Step Functions</li>
<li>CloudWatch</li>
</ul>
</div>

<div class="skill-group">
<h3>Machine learning</h3>
<ul class="tags">
<li>Python</li>
<li>PyTorch</li>
<li>scikit-learn</li>
<li>Pandas</li>
<li>NumPy</li>
<li>Matplotlib</li>
<li>Seaborn</li>
<li>OpenCV</li>
</ul>
</div>

<div class="skill-group">
<h3>Languages</h3>
<ul class="tags">
<li>Python</li>
<li>SQL</li>
<li>Java</li>
<li>JavaScript</li>
<li>C++</li>
</ul>
</div>

<div class="skill-group">
<h3>Other cloud and data</h3>
<ul class="tags">
<li>Apache Spark</li>
<li>Azure</li>
<li>Microsoft Fabric</li>
<li>Power BI</li>
<li>Docker</li>
<li>FastAPI</li>
<li>REST</li>
<li>GraphQL</li>
<li>Node.js</li>
<li>MongoDB</li>
<li>MySQL</li>
<li>Master data management</li>
<li>MLOps</li>
<li>NLP</li>
<li>Computer vision</li>
</ul>
</div>

---

## Education

**Master of Science in Computer Science**  
Georgia Institute of Technology | Specialization: AI / Machine Learning

---

## Experience

Roles and dates follow my [LinkedIn](https://www.linkedin.com/in/alexkimro/).

<div class="role">
<h3>Engineer</h3>
<p class="role-meta"><a href="https://www.reltio.com/">Reltio</a> · Cloud Data &amp; AI Platform<br>Jan 2025 – Present</p>
<ul>
<li>Engineer on the Cloud Data &amp; AI Platform. The product is cloud infrastructure for real-time master data and business context that enterprise AI agents use.</li>
</ul>
</div>

<div class="role">
<h3>Graduate Teaching Assistant</h3>
<p class="role-meta"><a href="https://www.gatech.edu/">Georgia Institute of Technology</a> · Machine Learning, CS 7641<br>Jan 2025 – Apr 2026 · Remote</p>
<ul>
<li>Teaching assistant for the graduate Machine Learning course, CS 7641.</li>
</ul>
</div>

<div class="role">
<h3>Machine Learning Engineer</h3>
<p class="role-meta"><a href="https://www.linkedin.com/company/intext-ai">Intext AI</a><br>Jun 2025 – Aug 2025</p>
<ul>
<li>Machine learning engineering role at an early-stage AI company.</li>
</ul>
</div>

<div class="role">
<h3>Data Engineer</h3>
<p class="role-meta"><a href="https://www.linkedin.com/company/divergenttechnologies">Divergent</a> · Machine Learning Additive Manufacturing, Software<br>Jul 2024 – Nov 2024 · Los Angeles, California</p>
<ul>
<li>Data engineer on the machine learning additive-manufacturing software team at Divergent, a digital manufacturing company.</li>
</ul>
</div>

<div class="role">
<h3>Engineer</h3>
<p class="role-meta"><a href="https://www.linkedin.com/company/futuresoft-inc.">FutureSoft, Inc.</a><br>Apr 2022 – Jun 2024 · Houston, Texas</p>
<ul>
<li>Software engineer at FutureSoft in Houston. The company builds terminal-emulation software.</li>
</ul>
</div>

<div class="role">
<h3>Junior Software Engineer</h3>
<p class="role-meta">Things Above Apparel<br>Jan 2021 – Jan 2022</p>
<ul>
<li>Junior software engineer at Things Above Apparel.</li>
</ul>
</div>

---

# Projects

The AWS pipeline is the cloud project. The other write-ups are applied machine learning. Each title links to the full page.

<div class="project">
<h3><a href="/awsdatapipeline">AWS Data Engineering Pipeline</a></h3>
<p>Real-time weather analytics. EventBridge starts Lambda, Kinesis Firehose lands records in S3, and Glue, Athena, and Step Functions feed a Grafana dashboard.</p>
<img class="project-shot" src="/images/aws-pipeline.png" alt="AWS architecture diagram for the weather pipeline: Lambda, Kinesis Firehose, S3, Glue, Athena, and Grafana"/>
</div>

<div class="project">
<h3><a href="/guaconomics">Guaconomics</a></h3>
<p>Avocado price predictor. A Random Forest model, trained on Hass Avocado Board data, serves predictions through Flask and Next.js.</p>
<img class="project-shot" src="/images/guaconomics.png" alt="Guaconomics screen for predicting avocado prices"/>
</div>

<div class="project">
<h3><a href="/damagedetective">Damage Detective</a></h3>
<p>Hacklytics 2024. A visual question-answering model describes the damage, then Llama-2 turns that context into a repair estimate.</p>
<img class="project-shot" src="/images/logo.png" alt="Damage Detective logo"/>
</div>

<div class="project">
<h3><a href="/customersegmentation">Customer Segmentation</a></h3>
<p>K-Means clusters of online retail customers, using monetary value, recency, and frequency.</p>
<img class="project-shot" src="/images/customer-segments.png" alt="3D scatter plot of customer clusters by monetary value, frequency, and recency"/>
</div>

<div class="project">
<h3><a href="/jireh">Jireh</a></h3>
<p>Family budget tracker in Expo and React Native. It logs income and expenses and shows the running balance.</p>
<img class="project-shot" src="/images/jireh.jpg" alt="Jireh app icon"/>
</div>

---

### Earlier web apps

- [Minimalist E-commerce](https://github.com/alexkimrow/Minimalist-E-commerce) — React storefront. [Live demo](https://minimalist-e-commerce-ashen.vercel.app/)
- [Car Rental](https://github.com/alexkimrow/car-rental) — React and SCSS rental site. [Live demo](https://car-rental-sage.vercel.app/)
- [Netflix clone](https://github.com/alexkimrow/Netflix-clone) — React, Redux, Firestore, Google auth, and Stripe checkout
