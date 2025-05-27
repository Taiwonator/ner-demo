## Prerequisites
- `Python >= v3`
- `pip >= v25.1.1`

## Getting Started
1. Install spaCy here - https://spacy.io/usage
2. Run `python index.py` or `python3 index.py`

### 1. spaCy
**Example Output:** 
The US Plastic Pact ORG
Nestlé, Mars WORK_OF_ART
Mondelēz GPE
the US Plastics Pact ORG
2030 CARDINAL
The US Plastics Pact ORG

### 2. Gemini
**Example Prompt:** 
It is your role to extract named entities from articles. So for example

"PepsiCo has announced a major update to its PepsiCo Positive (pep+) strategy, refining key climate, packaging, agriculture and water goals to be “more resilient”.

Overall, the company’s update to its pep+ strategy will lead to a “more sustainable food system” according to Ramon Laguarta, Chairman and Chief Executive Officer at PepsiCo.

The huge update is set to further align with core business priorities and accelerate the company’s progress towards long-term sustainability. "

You would extract PepsiCo and Ramon Laguarta

I will send an article and you give me the extracted entities

**Example Output:** 
Walmart, Nestlé, Mars, Mondelēz, L'Oréal USA, PepsiCo, James Darley, Ellen MacArthur Foundation, Robert Little, Google, Heidi Sanborn, National Stewardship Action Council, Aldi, Kraft Heinz, Eric Downing.
