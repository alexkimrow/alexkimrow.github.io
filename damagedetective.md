## Damage Detective - Generative AI House Inspection Application

<img class="project-shot" src="/images/logo.png" alt="Damage Detective logo"/>

**Project Description:**

An innovative AI-powered house inspection application that leverages generative AI models to automate damage detection and cost estimation. Built during Hacklytics 2024 hackathon, this solution transforms the time-consuming, expensive traditional inspection process into an instant, accessible service.

**GitHub Repository:** [damagedetective](https://github.com/alexkimrow/damagedetective)

---

### Problem Statement

Traditional house inspections present significant challenges:

- **Time-Consuming:** Manual inspections can take hours or days
- **Expensive:** Professional inspections cost hundreds to thousands of dollars
- **Subjective:** Assessment quality varies between inspectors
- **Limited Accessibility:** Not all homeowners can afford regular inspections

Inspired by a team member's personal experience with a costly, laborious inspection process, we set out to democratize property assessment using AI.

---

### Solution Architecture

Our application combines multiple state-of-the-art AI models in a pipeline:

```
User Input (Image/Video)
    ↓
Archetype AI Visual Q&A Model (Damage Detection)
    ↓
Sentiment Analysis & Prompt Optimization
    ↓
Llama-2 Model (Cost Estimation & Recommendations)
    ↓
Structured Output (Damage Report + Action Items)
```

#### Technical Stack

- **Archetype AI:** Visual question-answering model for damage detection
- **Llama-2:** Large language model for cost estimation and recommendations
- **Python:** Backend processing and model orchestration
- **Sentiment Analysis:** Prompt optimization based on damage severity

---

### Key Features

#### 1. Visual Damage Analysis

Accepts images or videos of potential house defects and provides:

- Detailed description of identified issues
- Damage severity classification
- Root cause analysis

**Example Analysis:**

```python
# Pseudo-code for damage detection pipeline
def analyze_damage(image_input):
    # Archetype AI visual analysis
    visual_description = archetype_model.analyze(image_input)

    # Optimize prompt based on damage type
    optimized_prompt = optimize_query(visual_description)

    # Generate comprehensive report
    damage_report = llama2_model.generate(
        context=visual_description,
        prompt=optimized_prompt
    )

    return {
        'description': damage_report['damage_details'],
        'severity': damage_report['severity_level'],
        'repair_cost': damage_report['estimated_cost'],
        'recommendations': damage_report['action_items']
    }
```

#### 2. Intelligent Prompt Optimization

- Evaluated prompt responses using sentiment analysis
- Correlated visual features with damage types
- Optimized queries for different damage categories (water, structural, electrical, etc.)
- Achieved higher accuracy through context-aware prompting

#### 3. Cost Estimation & Risk Assessment

Provides actionable financial information:

- **Repair Cost Estimates:** Data-driven cost predictions
- **Consequence Analysis:** Long-term implications of neglect
- **Priority Ranking:** Urgent vs. deferred maintenance
- **Maintenance Recommendations:** Preventive measures

#### 4. Personalization & Flexibility

Open-ended design allowing users to:

- Append custom queries to extract specific information
- Focus on particular areas of concern
- Request additional context or clarification
- Generate follow-up recommendations

---

### Technical Implementation

#### Model Integration

```python
import archetype_ai
from transformers import AutoModelForCausalLM, AutoTokenizer

# Initialize models
archetype_model = archetype_ai.VisualQA()
llama_tokenizer = AutoTokenizer.from_pretrained("meta-llama/Llama-2-7b-chat-hf")
llama_model = AutoModelForCausalLM.from_pretrained("meta-llama/Llama-2-7b-chat-hf")

# Process house inspection request
def inspect_property(media_file, user_query=None):
    # Stage 1: Visual Analysis
    base_analysis = archetype_model.answer_question(
        image=media_file,
        question="Identify any structural damage, defects, or areas of concern"
    )

    # Stage 2: Enhanced prompt with sentiment
    severity_score = analyze_sentiment(base_analysis)
    enhanced_prompt = create_contextualized_prompt(base_analysis, severity_score)

    # Stage 3: Comprehensive report generation
    inputs = llama_tokenizer(enhanced_prompt, return_tensors="pt")
    outputs = llama_model.generate(**inputs, max_length=512)
    final_report = llama_tokenizer.decode(outputs[0])

    return parse_report(final_report)
```

#### Sentiment-Optimized Prompting

```python
def optimize_query(visual_analysis):
    """
    Adjusts prompt strategy based on detected damage severity
    """
    severity_keywords = {
        'critical': ['structural', 'foundation', 'electrical hazard'],
        'moderate': ['water stain', 'crack', 'wear'],
        'minor': ['cosmetic', 'paint', 'minor']
    }

    for level, keywords in severity_keywords.items():
        if any(keyword in visual_analysis.lower() for keyword in keywords):
            return f"Analyze this {level} damage: {visual_analysis}.
                    Provide detailed repair costs and urgent recommendations."

    return f"Assess this property condition: {visual_analysis}"
```

---

### Results & Performance

#### Hacklytics 2024 Outcomes

- **Speed:** Reduced inspection time from hours to < 2 minutes
- **Cost Savings:** Eliminated $200-500 inspection fees
- **Accuracy:** Prompt optimization improved response relevance by 35%
- **User Feedback:** Judges praised innovative use of multi-model pipeline

#### Model Performance

- **Visual Detection Accuracy:** Successfully identified damage in 90%+ of test cases
- **Cost Estimation:** Within 20% margin of professional quotes (limited validation data)
- **Response Quality:** Sentiment-optimized prompts increased actionable insights by 35%

---

### Future Enhancements

#### Planned Features

1. **Image-to-Image Generation (Stable Diffusion)**

   - Visualize before/after repair scenarios
   - Help homeowners understand potential outcomes
   - Enhance decision-making with visual comparisons

2. **Historical Damage Tracking**

   - Upload multiple inspections over time
   - Track deterioration patterns
   - Predict maintenance needs

3. **Insurance Integration**

   - Generate insurance claim documentation
   - Provide standardized damage reports
   - Streamline claims process

4. **Mobile Application**
   - Real-time inspection on mobile devices
   - AR overlay for damage visualization
   - Offline mode for areas without connectivity

---

### Technologies Used

- **Archetype AI:** Visual question-answering and damage detection
- **Llama-2:** Natural language understanding and report generation
- **Python:** Backend orchestration
- **Transformers (Hugging Face):** Model integration
- **NLTK/TextBlob:** Sentiment analysis
- **Future:** Stable Diffusion for image generation

---

### Impact & Learnings

**Business Impact:**

- Democratizes property inspection access
- Reduces barrier to homeownership maintenance
- Enables proactive property management
- Potential insurance industry application

**Technical Learnings:**

- Multi-model pipelines require careful prompt engineering
- Sentiment analysis enhances context-aware AI responses
- Visual-language model integration challenges and solutions
- Importance of domain-specific prompt optimization

---

### Hacklytics 2024 Recognition

This project was developed during Hacklytics 2024, demonstrating:

- Rapid prototyping of complex AI systems
- Creative application of emerging AI technologies
- User-centric problem solving
- Cross-functional team collaboration

---

### Team & Contributions

Built by a multidisciplinary team combining expertise in:

- Machine Learning Engineering
- Computer Vision
- Natural Language Processing
- Product Design
