# 🧠 AI-Powered Procurement Assistant using CrewAI

This project demonstrates an intelligent multi-agent workflow built with [CrewAI](https://docs.crewai.com/) to automate product search, information extraction, and report generation for procurement purposes. The system simulates a real-world scenario where an organization wants to identify the best products online while considering country-specific regulations and business requirements.

## 📌 Features

- 🔍 **Smart Search Query Suggestions**  
  AI generates tailored search queries for better product discovery.

- 🌐 **Real-time Product Search**  
  Uses Tavily API to search for products online with filtering by confidence score and source credibility.

- 🕸 **Product Details Extraction**  
  Uses ScrapeGraph to extract essential product information and specifications from ecommerce sites.

- 📊 **Procurement Report Generation**  
  A final HTML report is automatically generated using Bootstrap to summarize the top products and make informed recommendations.

---

## 🧩 Workflow Overview

This project uses 4 agents and 4 tasks in a sequential pipeline:

1. **Query Generator Agent**  
   Suggests specific product search queries based on the user input.

2. **Search Agent**  
   Searches the web using the generated queries and filters low-confidence or suspicious links.

3. **Scraping Agent**  
   Extracts structured product data including title, pricing, image URL, and specs from e-commerce pages.

4. **Procurement Report Agent**  
   Creates a polished HTML procurement report summarizing and comparing the products.

---

## 📦 Installation

```bash
pip install -qU crewai[tools,agentops]==0.95.0 tavily-python scrapegraph-py
```

> Ensure you have the following API keys set as environment variables:
- `AGENTOPS_API_KEY`
- `COHERE_API_KEY`
- `tvly_API_KEY`
- `scrape_API_KEY`

---

## 🔧 How to Use

Run the notebook or script with inputs like:

```python
crew_result = crew.kickoff(
    inputs = {
        "product_name" : "laptop",
        "number_of_queries" : 2,
        "website_list" : ["amazon.com", "jumia.com"],
        "country" : "Egypt",
        "score" : 0.1,
        "top_recommendation_number" : 2
    }
)
```

### 🗂 Output Files (saved in `./ai-agent-output/`)
- `step_1_suggested_search_queries.json`  
- `step_2_search_results.json`  
- `step_3_search_results.json`  
- `step_4_procurement_report.html`

---

## 📄 Technologies Used

- [CrewAI](https://github.com/joaomdmoura/crewAI)
- [Cohere](https://cohere.com/)
- [Tavily](https://tavily.com/)
- [Scrapegraph-Py](https://pypi.org/project/scrapegraph-py/)
- [AgentOps](https://www.agentops.ai/)
- [Bootstrap](https://getbootstrap.com/) (for HTML report UI)

---

## 🧠 Example Use Cases

- AI-powered procurement for e-commerce businesses
- Competitive price & feature analysis
- Market research automation
- Dynamic sourcing assistant for different regions

---

## 📬 Contact

For any questions or improvements, feel free to reach out or contribute to the project!
