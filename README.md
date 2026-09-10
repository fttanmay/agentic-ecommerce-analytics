# Agentic E-commerce Analytics

A portfolio adaptation maintained by [fttanmay](https://github.com/fttanmay), focused on investigating revenue, cancellations and delivery performance.

## Portfolio scope and status

The inherited application provides natural-language SQL, charts and LLM summaries. This adaptation currently adds the business brief, metric definitions and evaluation checklist below; Olist ingestion and domain-specific functionality are planned, not yet implemented or validated.

## E-commerce analysis specification

- Revenue: sum item prices for delivered orders; report freight separately. Aggregate items before joining payments to avoid duplicate revenue.
- Cancellation rate: canceled orders divided by all orders in the same purchase-date cohort.
- Delivery SLA: delivered orders received after the estimated date divided by delivered orders with both dates populated.
- Retention: repeat purchasing by customer_unique_id, not order-specific customer_id.
- Compare complete calendar months and disclose the data cutoff; do not interpret an incomplete month as a business decline.
- Payment failure rates require attempted-payment events and cannot be inferred from successful-payment records alone.

## Evaluation checklist

Before presenting results: reconcile order counts and revenue with reference SQL; test joins for duplication; explain missing dates; use read-only database credentials; inspect generated SQL; distinguish observed associations from causal explanations. No business results or accuracy claims are asserted yet.

## Credits & license

Based on [Nicholas Tarazi / tnickster’s ai-analyst-agent](https://github.com/tnickster/ai-analyst-agent). The original MIT LICENSE and history are preserved. [Olist analytics](https://github.com/ali-0128/olist-ecommerce-analytics) is business-domain inspiration only; no dataset or code from that repository has been imported. Obtain the Olist dataset separately and follow its terms. Original documentation follows.

---

# Business Insights Agent

An intelligent business analytics platform powered by LLMs that translates natural language questions into SQL queries, creates visualizations, and provides actionable insights.

## 📸 Screenshots

### 1. Asking a question
![Agent input prompt](images/agent_input.png)

### 2. Employees per department
![Bar Graph](images/dept_numbers_split.png)

### 3. Overall gender distribution & Follow-up
![Overall gender pie](images/gender_pie.png)

## Features

- 💬 **Natural Language Interface**: Ask questions in plain English about your business data
- 📊 **Automatic Visualizations**: Generates appropriate charts based on query results
- 🔍 **Root Cause Analysis**: Identifies underlying factors contributing to business trends
- 📈 **Actionable Recommendations**: Suggests next steps based on data insights
- 🔄 **Follow-up Questions**: Recommends additional queries to deepen your analysis

## Tech Stack

- **Backend**: Python, MySQL, LangChain
- **LLM Integration**: OpenAI GPT-4
- **Data Processing**: Pandas
- **Visualization**: Plotly
- **Frontend**: Streamlit

## How It Works

1. User asks a business question in natural language
2. LLM agent interprets the question and generates appropriate SQL queries
3. Queries are executed against the MySQL database
4. Results are processed and visualized
5. LLM provides insights, analyses, and recommendations based on the data

## Getting Started

### Prerequisites

- Python 3.8+
- MySQL database with your business data
- OpenAI API key

### Installation

1. Clone this repository
   ```bash
   git clone https://github.com/tnickster/ai-analyst-agent.git
   cd ai-analyst-agent
   ```

2. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file with your configuration
   ```
   OPENAI_API_KEY=your_openai_api_key 
   DB_HOST=your_db_host
   DB_PORT=your_db_host
   DB_USER=your_db_user
   DB_PASSWORD=your_db_password
   DB_NAME=your_db_name
   ```

### Running the Application

#### Streamlit Web Interface
```bash
streamlit run app.py
```

#### Command Line Interface
```bash
python main.py
```

## Project Structure

```
├── app.py              # Streamlit web interface
├── main.py             # Command line interface
├── tools.py            # Core functionality, SQL processing, visualization
├── prompt.txt          # System prompt for the LLM agent
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

## Demo

Soon to be implemented

## Future Improvements

- Support for additional databases (PostgreSQL, SQLite, etc.)
- Custom visualization options
- Data export functionality
- User authentication and access controls
- Multi-tenant support for multiple databases

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

Nicholas Tarazi - Nicholas.Tarazi7@gmail.com

LinkedIn: https://www.linkedin.com/in/nicholas-tarazi/

Project Link: [https://github.com/tnickster/ai-analyst-agent](https://github.com/tnickster/ai-analyst-agent)
