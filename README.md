# hydro
hydro dummy

AI Input Data Structure
To ensure the AI provides accurate financial insights, we use a Context-Augmented Schema. This structure categorizes data into three layers: User Identity, Financial State, and Transactional History.

Metadata: Information about the request (timestamp, user ID, session context).

User Profile: Risk tolerance, financial goals, and account tier.

Account Snapshots: Real-time balances across liquidity pools, wallets, or staked assets.

Market Context: Current token prices, APY rates, and gas fees.


Data Flow into AI Responses
The journey from raw data to a user-facing response follows a RAG (Retrieval-Augmented Generation) pipeline:

Data Ingestion: The system pulls the latest JSON snapshot (like the one above) when a user interacts with the AI.

Prompt Engineering: The raw JSON is injected into a "system prompt" that defines the AI’s persona (e.g., "You are a Hydro Finance Specialist").

Context Processing: The AI analyzes the user_context against market_data. It calculates if the transaction costs (gas) outweigh the potential yield.

Natural Language Generation: The AI converts the data into a readable format, such as: "Based on your moderate risk profile and the current 18.5% APY, moving your 500 USDC is advisable, especially since gas fees are currently low."

Output Guardrails: The response is filtered for compliance and accuracy before being displayed to the user.
