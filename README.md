# Named Entity Recognition (NER)
Learn about it [here](https://en.wikipedia.org/wiki/Named-entity_recognition)

This demo was inspired by a suggested feature from an executive stakeholder to introduce 'smarter' entity recognition which can have specific system side-effects.

## Prerequisites
- `Python >= v3`
- `pip >= v25.1.1`

## Getting Started
1. Install spaCy here - https://spacy.io/usage
2. Run `python index.py` or `python3 index.py`

## Different Approaches
Test Article - https://sustainabilitymag.com/articles/why-walmart-nestle-mars-more-have-left-us-plastics-pact

### 1. spaCy
**Output:** 
- The US Plastic Pact `ORG`
- Nestlé `ORG`
- Mars `ORG`
- Mondelēz `GPE`
- the US Plastics Pact `ORG`
- 2030 `DATE`
- The US Plastics Pact `ORG`
- Walmart `ORG`
- Mondelēz `GPE`
- Mars `LOC`
- L'Oréal USA `ORG`
- the US Plastics Pact `ORG`
- 2025 `DATE`
- 2030 `DATE`
- PepsiCo `ORG`
- 2020 `DATE`
- the Ellen MacArthur Foundation's `ORG`
- 60 `CARDINAL`
- more than 125 `CARDINAL`
- 2023 `DATE`
- Half `CARDINAL`
- 11% `PERCENT`
- Mars `LOC`
- 2024 `DATE`
- the Ellen MacArthur Foundation's `ORG`
- the end of 2025 `DATE`
- the US Plastics Pact `ORG`
- 2025 `DATE`
- 100% `PERCENT`
- 30% `PERCENT`
- Robert Little `PERSON`
- Google `ORG`
- LinkedIn `ORG`
- PepsiCo `ORG`
- Robert Little `PERSON`
- 2025 `DATE`
- 2025 `DATE`
- February 2025 `DATE`
- Plastics Pact `ORG`
- Heidi Sanborn `PERSON`
- the National Stewardship Action Council `ORG`
- NSAC `ORG`
- Heidi `PERSON`
- Heidi Sanborn `PERSON`
- the National Stewardship Action Council `ORG`
- Aldi `ORG`
- Kraft Heinz `ORG`
- more than a dozen `CARDINAL`
- 2030 `DATE`
- The Plastics Pact's `ORG`
- 2030 `DATE`
- 30% `PERCENT`
- 30% `PERCENT`
- Eric Downing `PERSON`
- Director of Marketing & Communications `ORG`
- annually `DATE`
- Eric Downing `PERSON`
- the US Plastic Pact's `ORG`
- Marketing & Communications Industry `ORG`
- The Ellen MacArthur Foundation `ORG`
- 2024 `DATE`
- 44% `PERCENT`
- six years `DATE`
- 360,000 tonnes `QUANTITY`
- 2030 `DATE`
- 1st January 2026 `DATE`
- the Global Plastics Treaty `ORG`
- Robert `PERSON`
- one `CARDINAL`

### 2. Gemini
#### 2.1 Simply assigning Gemini the task of identifying entities.
**Prompt:** 
```
It is your role to extract named entities from articles. So for example

"PepsiCo has announced a major update to its PepsiCo Positive (pep+) strategy, refining key climate, packaging, agriculture and water goals to be “more resilient”.

Overall, the company’s update to its pep+ strategy will lead to a “more sustainable food system” according to Ramon Laguarta, Chairman and Chief Executive Officer at PepsiCo.

The huge update is set to further align with core business priorities and accelerate the company’s progress towards long-term sustainability. "

You would extract PepsiCo and Ramon Laguarta

I will send an article and you give me the extracted entities
```

**Output:** 
Walmart, Nestlé, Mars, Mondelēz, L'Oréal USA, PepsiCo, James Darley, Ellen MacArthur Foundation, Robert Little, Google, Heidi Sanborn, National Stewardship Action Council, Aldi, Kraft Heinz, Eric Downing.

#### 2.2 Asking Gemini to copy spaCy (with no prior examples)
**Prompt:** 
```
Okay with that previous article, pretend you're SPACY
```

**Output:** 
- The US Plastic Pact `ORG`
- Walmart `ORG`
- Nestlé `ORG`
- Mars `ORG`
- Mondelēz `ORG`
- US Plastics Pact `ORG`
- Walmart `ORG`
- Mondelēz `ORG`
- Mars `ORG`
- Nestlé `ORG`
- L'Oréal USA `ORG`
- US Plastics Pact `ORG`
- 2030 `DATE`
- PepsiCo `ORG`
- 2020 `DATE`
- Ellen MacArthur Foundation `ORG`
- 60 `CARDINAL`
- 125 `CARDINAL`
- 2023 `DATE`
- Half `CARDINAL`
- 11% `PERCENT`
- Mars `ORG`
- 2024 `DATE`
- Ellen MacArthur Foundation `ORG`
- 2025 `DATE`
- US Plastics Pact `ORG`
- 2025 `DATE`
- 100% `PERCENT`
- 30% `PERCENT`
- Robert Little `PERSON`
- Google `ORG`
- LinkedIn `ORG`
- PepsiCo `ORG`
- Walmart `ORG`
- 2025 `DATE`
- February 2025 `DATE`
- EPR Leadership Forum `ORG`
- Plastics Pact `ORG`
- Heidi Sanborn `PERSON`
- National Stewardship Action Council `ORG`
- NSAC `ORG`
- Heidi `PERSON`
- Aldi `ORG`
- Kraft Heinz `ORG`
- a dozen `CARDINAL`
- 2030 `DATE`
- Plastics Pact `ORG`
- 2030 `DATE`
- 30% `PERCENT`
- 30% `PERCENT`
- Eric Downing `PERSON`
- US Plastic Pact `ORG`
- Ellen MacArthur Foundation `ORG`
- 2024 `DATE`
- 44% `PERCENT`
- six years `DATE`
- 360,000 tonnes `QUANTITY`
- 2030 `DATE`
- 1st January 2026 `DATE`
- US Plastics Pact `ORG`
- Global Plastics Treaty `ORG`
- Robert `PERSON`

## Conclusion
When doing further testing (on [this article](https://supplychaindigital.com/sustainability/ecovadis-firms-overrun-by-new-supply-chain-esg-laws)), both approaches seem to have plenty false positives. For example `ESG ORG`, `GHG ORG` or even `Carbon PERSON`. This however is a non-issue by my estimation as simple validation steps can be taken afterward to confirm these. What stands out with the simplicity of modern AI workflows however is how simple these validation steps have now become - especially thanks to reasoning models.

<img width="1282" alt="Screenshot 2025-05-27 at 09 50 00" src="https://github.com/user-attachments/assets/d0200287-7a48-409d-bc8e-e475babf404a" />




