---
pageType: source
id: source.eu-customs-research-report
title: eu customs research report
sourceType: local-file
sourcePath: /Users/xiaogong/Documents/Codex/2026-06-03/you-are-a-legal-regulatory-research/eu_customs_research_report.md
ingestedAt: 2026-06-07T03:29:52.424Z
updatedAt: 2026-06-07T03:29:52.424Z
status: active
---

# eu customs research report

## Source
- Type: `local-file`
- Path: `/Users/xiaogong/Documents/Codex/2026-06-03/you-are-a-legal-regulatory-research/eu_customs_research_report.md`
- Bytes: 54405
- Updated: 2026-06-07T03:29:52.424Z

## Content
````text
# EU Import and Customs Source Base

Query date for dynamic databases and live pages: 2026-06-03

Method note:
- Priority sources used: EUR-Lex / ELI, CELLAR SPARQL, DG TAXUD, Access2Markets, DG TRADE, WTO, and selected Member State customs sources.
- Dynamic results such as TARIC measures, tariff quotas, safeguards, sanctions, and product regulatory restrictions are date-sensitive and should be treated as live-query outputs rather than static law.
- EUR-Lex interactive pages were intermittently WAF-gated. Stable retrieval paths used were ELI URLs, CELEX PDF links, and the official CELLAR SPARQL endpoint.
- SPARQL pattern that worked reliably for CELEX lookups:

```sparql
PREFIX cdm: <http://publications.europa.eu/ontology/cdm#>
SELECT ?s ?date ?entry ?eli ?force WHERE {
  ?s cdm:resource_legal_id_celex ?celex .
  FILTER(STR(?celex) = "32013R0952")
  OPTIONAL { ?s cdm:work_date_document ?date }
  OPTIONAL { ?s cdm:resource_legal_date_entry-into-force ?entry }
  OPTIONAL { ?s cdm:resource_legal_eli ?eli }
  OPTIONAL { ?s cdm:resource_legal_in-force ?force }
}
```

Bulk retrieval also worked with `VALUES ?target { "32013R0952" ... }` plus `FILTER(STR(?celex)=STR(?target))`.

## A. Overview Table

| Topic | Core legal act / database | CELEX / link | Purpose | Priority | Full-text download needed |
|---|---|---|---|---|---|
| UCC framework | Regulation (EU) No 952/2013 | 32013R0952 | Core EU customs code | Highest | Yes |
| UCC delegated rules | Commission Delegated Regulation (EU) 2015/2446 | 32015R2446 | Detailed supplementary customs rules | Highest | Yes |
| UCC implementing rules | Commission Implementing Regulation (EU) 2015/2447 | 32015R2447 | Detailed implementing rules, codes, Annexes | Highest | Yes |
| Customs electronic systems | Commission Implementing Regulation (EU) 2025/512 | 32025R0512 | Technical arrangements for UCC electronic systems incl. ICS2 context | High | Yes |
| ENS / ICS2 updates | Commission Delegated Regulation (EU) 2023/398; Commission Implementing Regulation (EU) 2023/403 | 32023R0398; 32023R0403 | Entry summary declaration and security risk analysis updates | High | Yes |
| HS / CN / TARIC | Council Regulation (EEC) No 2658/87 | 31987R2658 | Legal basis for CN and Common Customs Tariff | Highest | Yes |
| Current CN | Commission Implementing Regulation (EU) 2025/1926 | 32025R1926 | 2026 Combined Nomenclature in force from 2026-01-01 | Highest | Yes |
| TARIC database | TARIC consultation | https://ec.europa.eu/taxation_customs/dds2/taric/taric_consultation.jsp?Lang=en | Live duty rates, measures, quotas, ADD/CVD, licences | Highest | No, live query |
| Tariff quotas | QUOTA consultation | https://ec.europa.eu/taxation_customs/dds2/taric/quota_consultation.jsp?Lang=en | Live balances and quota periods | Highest | No, live query |
| Classification support | CLASS | https://webgate.ec.europa.eu/class-public-ui-web/ | CN notes, classification regulations, case law, TARIC links | High | No, live query |
| BTI | UCC + EBTI database | 32013R0952 plus DG TAXUD EBTI page | Binding tariff classification decisions | High | Mixed |
| Rules of origin base | UCC origin provisions + UCC DA/IA | 32013R0952; 32015R2446; 32015R2447 | Preferential and non-preferential origin framework | Highest | Yes |
| PEM convention layer | Council Decision 2013/94/EU; Decision No 1/2023 [2024/390]; Decision No 2/2024 [2025/17] | 32013D0094; 22024D0390; 22025D0017 | Cumulation and modernised PEM origin rules | High | Yes |
| Origin operational tools | Access2Markets + REX | https://trade.ec.europa.eu/access-to-markets/en/home ; DG TAXUD REX page | Preferential treatment, PSRs, proof of origin, REX validation | Highest | No, live query |
| Anti-dumping basic act | Regulation (EU) 2016/1036 | 32016R1036 | EU anti-dumping framework | Highest | Yes |
| Anti-subsidy basic act | Regulation (EU) 2016/1037 | 32016R1037 | EU countervailing framework | Highest | Yes |
| Safeguards base | Regulation (EU) 2015/478; Regulation (EU) 2015/755; Regulation (EU) 2019/287 | 32015R0478; 32015R0755; 32019R0287 | Safeguard and bilateral safeguard framework | High | Yes |
| Trade defence cases | TARIC + DG TRADE trade defence pages + OJ implementing regs | various | Product/country-specific ADD/CVD/safeguards | Highest | Live query plus OJ texts |
| Customs valuation | UCC arts. 69-76; IA arts. 127-146; DG TAXUD valuation page | 32013R0952; 32015R2447 | Customs value, additions, related parties, fallback methods | Highest | Yes |
| Agricultural licences | Commission Delegated Regulation (EU) 2016/1237 | 32016R1237 | Import/export licences in CAP sectors | High | Yes |
| Autonomous suspensions / quotas | Council Regulations (EU) 2021/2278 and 2021/2283 | 32021R2278; 32021R2283 | Autonomous tariff suspensions and quotas | High | Yes |
| Dual-use restrictions | Regulation (EU) 2021/821 | 32021R0821 | Import/export control relevance for dual-use goods | High | Yes |
| AEO | UCC arts. 38-41 + DG TAXUD AEO materials | 32013R0952 | AEO criteria, benefits, suspension/revocation relevance | Highest | Yes |
| Penalties / audits | UCC art. 42 + Member State law | 32013R0952 + national sources | Penalties, audits, post-clearance control | Highest | Mixed |

## B. Detailed Legal Act List

### 1. UCC core

Topic:
Market access, declarations, origin, valuation, AEO, controls, penalties

Legal act name:
Regulation (EU) No 952/2013 of the European Parliament and of the Council of 9 October 2013 laying down the Union Customs Code (recast)

CELEX:
32013R0952

Legal type:
Regulation

Publication date:
2013-10-10 in OJ L 269/1

Entry into force:
2013-10-30; major operative provisions apply from 2016-05-01

Current status:
In force; amended; EUR-Lex page accessed showed current consolidated version dated 2022-12-12

Official link:
https://eur-lex.europa.eu/eli/reg/2013/952/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2013/952/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2013/952/oj/eng/pdf
XML route: https://eur-lex.europa.eu/legal-content/EN/TXT/XML/?uri=CELEX:32013R0952

Key articles:
Arts. 5, 6, 15, 18, 22-37, 38-42, 46-48, 56-58, 59-67, 69-76, 77-80, 127-149, 158-187, 201

Summary:
This is the foundational EU customs act. It establishes the core legal framework for declarations, release for free circulation, temporary storage, customs debt, customs controls, tariff classification, origin, valuation, authorisations, BTI/BOI, AEO, and penalties.

Practical application:
Everything in actual import clearance maps back to the UCC. It is the starting point for importer/declarant responsibilities, declarations, ENS, temporary storage, tariff/origin/valuation analysis, and AEO/compliance assessment.

Relationship with other legal acts:
Implemented and supplemented primarily by 2015/2446 and 2015/2447. Live customs system operation depends increasingly on 2025/512 and topic-specific amendments.

Knowledge base ingestion suggestion:
Download full text and split by article clusters: definitions; decisions/authorisations; tariff/origin/valuation; entry and temporary storage; declarations; release for free circulation; controls/AEO/penalties.

### 2. UCC delegated rules

Topic:
Detailed customs rules supplementing the UCC

Legal act name:
Commission Delegated Regulation (EU) 2015/2446 of 28 July 2015 supplementing Regulation (EU) No 952/2013 as regards detailed rules concerning certain provisions of the Union Customs Code

CELEX:
32015R2446

Legal type:
Delegated regulation

Publication date:
2015-12-29 in OJ L 343/1

Entry into force:
2016-01-18; main application from 2016-05-01

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg_del/2015/2446/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_del/2015/2446/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_del/2015/2446/oj/eng/pdf

Key articles:
Topic-specific. Verified examples: Arts. 11-22 for BTI/BOI; Art. 71 for valuation support; provisions on ENS, oral declarations, and Annexes A/B data structures are central operationally.

Summary:
This act supplies the detailed legal rules that supplement the UCC, including decisions, BTI/BOI, detailed declaration rules, origin support rules, valuation support rules, and operational customs formalities.

Practical application:
Critical for mapping UCC principle-level rules into operational customs filings and authorisations.

Relationship with other legal acts:
Paired with Implementing Regulation 2015/2447. Amended by 2020/877 and 2023/398 for ENS / declaration updates.

Knowledge base ingestion suggestion:
Store full text and tag article chunks by subject rather than linear order because operational use is topic-driven.

### 3. UCC implementing rules

Topic:
Detailed implementing rules and data/code architecture

Legal act name:
Commission Implementing Regulation (EU) 2015/2447 of 24 November 2015 laying down detailed rules for implementing certain provisions of Regulation (EU) No 952/2013 laying down the Union Customs Code

CELEX:
32015R2447

Legal type:
Implementing regulation

Publication date:
2015-12-29 in OJ L 343/558

Entry into force:
2016-01-18; main application from 2016-05-01

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2015/2447/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2015/2447/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2015/2447/oj/eng/pdf

Key articles:
Arts. 8-23 for BTI/BOI; Arts. 49-54 for tariff quota management; Arts. 127-146 and 347 plus Annexes 23-01 and 23-02 for valuation; Annexes A and B for applications, decisions, declarations, and notifications

Summary:
This act operationalises the UCC in customs processing terms. It is especially important for code lists, structured data, valuation detail, quota mechanics, and procedural execution.

Practical application:
Essential for customs software mapping, declaration data models, quota claims, and valuation substantiation.

Relationship with other legal acts:
Paired with 2015/2446 and further updated by 2023/403, 2025/1728, and other topic-specific implementing acts.

Knowledge base ingestion suggestion:
Download full text and Annexes. Keep Annexes A/B and valuation annexes as separate ingestion units.

### 4. UCC electronic systems

Topic:
Customs electronic systems, including ICS2 infrastructure

Legal act name:
Commission Implementing Regulation (EU) 2025/512 of 13 March 2025 on technical arrangements for developing, maintaining and employing electronic systems for the exchange and storage of information under Regulation (EU) No 952/2013 of the European Parliament and of the Council

CELEX:
32025R0512

Legal type:
Implementing regulation

Publication date:
2025-03-20 in OJ L 2025/512

Entry into force:
2025-04-09

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2025/512/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2025/512/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2025/512/oj/eng/pdf

Key articles:
System-specific articles including ICS2 architecture; see search-confirmed Article 42 on objective and structure of ICS2

Summary:
This is the current technical framework for UCC electronic systems and is now the better operational anchor for customs system architecture than the earlier, narrower ICS2 system regulation.

Practical application:
Important for system builders, data exchanges, trader interfaces, and EU/national customs IT interoperability.

Relationship with other legal acts:
Works alongside the UCC, UCC DA/IA, and Implementing Decision (EU) 2023/2879 work-programme timelines.

Knowledge base ingestion suggestion:
Store as a systems-law layer separate from substantive customs law.

### 5. ENS / ICS2 delegated update

Topic:
Entry Summary Declarations, declarant data exchange

Legal act name:
Commission Delegated Regulation (EU) 2023/398 of 14 December 2022 amending Delegated Regulation (EU) 2015/2446 as regards extending the possibilities for making customs declarations orally or by any other act deemed to be a customs declaration, the invalidation of declarations in specific cases, and specifying the exchange of information for entry summary declarations

CELEX:
32023R0398

Legal type:
Delegated regulation

Publication date:
2023-02-22 in OJ L 56

Entry into force:
2023-03-14

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_del/2023/398/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_del/2023/398/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_del/2023/398/oj/eng/pdf

Key articles:
Amending provisions focused on ENS information-sharing and declaration mechanics

Summary:
Important update for ENS information exchange, especially where actors other than the carrier provide portions of the data.

Practical application:
Relevant to ICS2 data-splitting models and carrier / house bill / postal workflows.

Relationship with other legal acts:
Paired with Implementing Regulation 2023/403.

Knowledge base ingestion suggestion:
Store as amendment layer linked to 2015/2446 ENS and declaration provisions.

### 6. ENS / ICS2 implementing update

Topic:
Entry Summary Declarations and security risk analysis

Legal act name:
Commission Implementing Regulation (EU) 2023/403 of 8 February 2023 amending Implementing Regulation (EU) 2015/2447 as regards the provision of information for entry summary declarations and risk analysis for security and safety purposes at entry of goods, and adding Ukraine to the list of countries in the guarantor’s undertakings for transit

CELEX:
32023R0403

Legal type:
Implementing regulation

Publication date:
2023-02-22 in OJ L 56

Entry into force:
2023-03-15

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2023/403/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2023/403/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2023/403/oj/eng/pdf

Key articles:
Amending provisions affecting arts. 184-186 IA in practice

Summary:
Operational update for the information that must be supplied for ENS and for risk analysis on entry of goods.

Practical application:
Use this when mapping the legal data obligations of ICS2 filings.

Relationship with other legal acts:
Paired with 2023/398 and implemented through ICS2 releases.

Knowledge base ingestion suggestion:
Store with an article-level relationship map to 2015/2447 articles 184-186 and Annex B data elements.

### 7. Common Customs Tariff and CN legal basis

Topic:
Tariffs, tariff classification, CN, TARIC

Legal act name:
Council Regulation (EEC) No 2658/87 of 23 July 1987 on the tariff and statistical nomenclature and on the Common Customs Tariff

CELEX:
31987R2658

Legal type:
Regulation

Publication date:
1987-09-07 in OJ L 256

Entry into force:
1987-09-10; main application from 1988-01-01

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg/1987/2658/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/1987/2658/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/1987/2658/oj/eng/pdf

Key articles:
Art. 1 and Art. 9 are the most operationally important; Annex I is the nomenclature itself

Summary:
This is the base act for the Combined Nomenclature and the Common Customs Tariff.

Practical application:
The HS is the WCO six-digit layer; the CN adds EU eight-digit detail; TARIC adds further EU measures on top of CN.

Relationship with other legal acts:
Updated annually through a Commission Implementing Regulation amending Annex I.

Knowledge base ingestion suggestion:
Treat as a framework act. Store Annex I references separately from the base text.

### 8. Current Combined Nomenclature for 2026

Topic:
Current CN in force

Legal act name:
Commission Implementing Regulation (EU) 2025/1926 of 22 September 2025 amending Annex I to Council Regulation (EEC) No 2658/87 on the tariff and statistical nomenclature and on the Common Customs Tariff

CELEX:
32025R1926

Legal type:
Implementing regulation

Publication date:
2025-10-31 in OJ L 2025/1926

Entry into force:
2025-11-01; applies from 2026-01-01

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2025/1926/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2025/1926/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2025/1926/oj/eng/pdf

Key articles:
Annex I is the operational content

Summary:
This is the current annual CN update governing 2026 tariff classification at CN level.

Practical application:
Use this for 8-digit CN coding and as the legal backbone for TARIC extensions in 2026.

Relationship with other legal acts:
Implements the 2658/87 framework. Current from 2026-01-01.

Knowledge base ingestion suggestion:
Store the act metadata plus Annex I as a versioned classification corpus.

### 9. Anti-dumping framework

Topic:
Trade remedies

Legal act name:
Regulation (EU) 2016/1036 of the European Parliament and of the Council of 8 June 2016 on protection against dumped imports from countries not members of the European Union (codification)

CELEX:
32016R1036

Legal type:
Regulation

Publication date:
2016-06-30 in OJ L 176

Entry into force:
2016-07-20

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg/2016/1036/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2016/1036/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2016/1036/oj/eng/pdf

Key articles:
Arts. 1-3, 5, 7, 9, 11, 13

Summary:
This is the EU basic anti-dumping regulation.

Practical application:
Every product-specific anti-dumping implementing regulation will cite this as the legal base.

Relationship with other legal acts:
Implemented case-by-case through Commission implementing regulations and reflected in TARIC.

Knowledge base ingestion suggestion:
Store as a framework act with article-level tags for initiation, provisional measures, definitive duties, reviews, and anti-circumvention.

### 10. Anti-subsidy / countervailing framework

Topic:
Trade remedies

Legal act name:
Regulation (EU) 2016/1037 of the European Parliament and of the Council of 8 June 2016 on protection against subsidised imports from countries not members of the European Union (codification)

CELEX:
32016R1037

Legal type:
Regulation

Publication date:
2016-06-30 in OJ L 176

Entry into force:
2016-07-20

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg/2016/1037/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2016/1037/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2016/1037/oj/eng/pdf

Key articles:
Arts. 1-4, 7, 10, 12, 15, 19, 24

Summary:
This is the EU basic countervailing-duty regulation.

Practical application:
Every product-specific anti-subsidy measure will rest on this act and then appear in TARIC by code and origin.

Relationship with other legal acts:
Implemented through Commission case regulations such as the BEV China measure.

Knowledge base ingestion suggestion:
Store with the same framework schema as anti-dumping, but separate subsidy-specific injury/benefit logic.

### 11. Safeguards framework

Topic:
Trade remedies / safeguards

Legal act name:
Regulation (EU) 2015/478 of the European Parliament and of the Council of 11 March 2015 on common rules for imports (codification)

CELEX:
32015R0478

Legal type:
Regulation

Publication date:
2015-03-27 in OJ L 83

Entry into force:
2015-04-16

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg/2015/478/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2015/478/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2015/478/oj/eng/pdf

Key articles:
Arts. 1-3, 9-16, 20

Summary:
Framework for common import rules and WTO-style safeguards.

Practical application:
Used for safeguard investigations and measures, including steel safeguard administration.

Relationship with other legal acts:
Works alongside 2015/755 for certain third countries and 2019/287 for bilateral safeguard clauses in FTAs.

Knowledge base ingestion suggestion:
Store as safeguard framework; attach product-specific measures by CN code and country scope.

### 12. Common import rules for certain third countries

Topic:
Safeguards / surveillance / imports from certain third countries

Legal act name:
Regulation (EU) 2015/755 of the European Parliament and of the Council of 29 April 2015 on common rules for imports from certain third countries (recast)

CELEX:
32015R0755

Legal type:
Regulation

Publication date:
2015-05-19 in OJ L 123

Entry into force:
2015-06-08

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg/2015/755/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2015/755/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2015/755/oj/eng/pdf

Key articles:
Arts. 1-3, 10-16

Summary:
Parallel common import rules applying to specified third-country contexts.

Practical application:
Relevant where safeguard or surveillance measures rely on this specific import-rule framework.

Relationship with other legal acts:
Cited alongside 2015/478 in steel safeguard amendments.

Knowledge base ingestion suggestion:
Keep linked to safeguard case records and surveillance measures.

### 13. Bilateral safeguard clauses in FTAs

Topic:
Trade remedies / preferential trade agreements

Legal act name:
Regulation (EU) 2019/287 of the European Parliament and of the Council of 13 February 2019 implementing bilateral safeguard clauses and other mechanisms allowing for the temporary withdrawal of preferences in certain trade agreements concluded between the European Union and third countries

CELEX:
32019R0287

Legal type:
Regulation

Publication date:
2019-02-25 in OJ L 53

Entry into force:
2019-03-14

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg/2019/287/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2019/287/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2019/287/oj/eng/pdf

Key articles:
Framework articles on bilateral safeguards and temporary withdrawal of preferences

Summary:
This is the umbrella act for safeguard clauses and preference withdrawal mechanisms across listed EU trade agreements.

Practical application:
Important when preferential access under an FTA is later constrained.

Relationship with other legal acts:
Sits between FTA-specific treaty text and product-specific implementing actions.

Knowledge base ingestion suggestion:
Store by agreement and mechanism.

### 14. Specific CVD example: battery electric vehicles from China

Topic:
Trade remedies / product-specific measures

Legal act name:
Commission Implementing Regulation (EU) 2024/2754 of 29 October 2024 imposing a definitive countervailing duty on imports of new battery electric vehicles designed for the transport of persons originating in the People’s Republic of China

CELEX:
32024R2754

Legal type:
Implementing regulation

Publication date:
2024-10-29 in OJ L 2024/2754

Entry into force:
2024-10-30

Current status:
In force; current EUR-Lex version accessed was 2026-02-11 after amendment by 2026/330

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2024/2754/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2024/2754/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2024/2754/oj/eng/pdf

Key articles:
Art. 1

Summary:
Definitive countervailing duties on BEVs originating in China.

Practical application:
Direct import-cost impact. Product scope identified in the act and mirrored in TARIC.

Relationship with other legal acts:
Based on Regulation 2016/1037; amended by 2026/330; associated undertaking decision 2026/328.

Knowledge base ingestion suggestion:
Store as a live trade-defence measure object keyed by CN/TARIC code, origin, producer, duty rate, effective date.

### 15. Specific BEV amendment

Topic:
Trade remedies / product-specific measures

Legal act name:
Commission Implementing Regulation (EU) 2026/330 of 9 February 2026 amending Implementing Regulation (EU) 2024/2754 imposing a definitive countervailing duty on imports of new battery electric vehicles designed for the transport of persons originating in the People’s Republic of China following a partial interim review pursuant to Article 19(2) of Regulation (EU) 2016/1037

CELEX:
32026R0330

Legal type:
Implementing regulation

Publication date:
2026-02-10 in OJ L 2026/330

Entry into force:
2026-02-11

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2026/330/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2026/330/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2026/330/oj/eng/pdf

Key articles:
Amending text to Art. 1(2) and annexes of 2024/2754

Summary:
Shows why trade-defence ingestion must preserve amendment chains, not just base measures.

Practical application:
Importer cost and producer-specific rates can change after interim review.

Relationship with other legal acts:
Direct amendment to 2024/2754.

Knowledge base ingestion suggestion:
Version-control product-specific trade remedies and never overwrite the prior state.

### 16. Specific ADD example: stainless steel cold-rolled flat products, India/Indonesia

Topic:
Trade remedies / product-specific measures

Legal act name:
Commission Implementing Regulation (EU) 2021/2012 of 17 November 2021 imposing a definitive anti-dumping duty and definitively collecting the provisional duty imposed on imports of stainless steel cold-rolled flat products originating in India and Indonesia

CELEX:
32021R2012

Legal type:
Implementing regulation

Publication date:
2021-11-18 in OJ L 410/153

Entry into force:
2021-11-19

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2021/2012/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2021/2012/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2021/2012/oj/eng/pdf

Key articles:
Art. 1

Summary:
Representative anti-dumping case with identifiable product scope and country coverage.

Practical application:
Directly affects landed duty cost and is reflected in TARIC.

Relationship with other legal acts:
Paired with 2022/433 countervailing duties.

Knowledge base ingestion suggestion:
Maintain separate ADD and CVD records even where products overlap.

### 17. Specific CVD example: stainless steel cold-rolled flat products, India/Indonesia

Topic:
Trade remedies / product-specific measures

Legal act name:
Commission Implementing Regulation (EU) 2022/433 of 15 March 2022 imposing definitive countervailing duties on imports of stainless steel cold-rolled flat products originating in India and Indonesia and amending Implementing Regulation (EU) 2021/2012

CELEX:
32022R0433

Legal type:
Implementing regulation

Publication date:
2022-03-16 in OJ L 88

Entry into force:
2022-03-17

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2022/433/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2022/433/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2022/433/oj/eng/pdf

Key articles:
Arts. 1-3

Summary:
Illustrates cumulative trade-defence layering on the same product.

Practical application:
Necessary to avoid undercounting duty exposure where ADD and CVD both apply.

Relationship with other legal acts:
Amends 2021/2012 and is based on 2016/1037.

Knowledge base ingestion suggestion:
Flag as concurrent-measure record on same CN/TARIC scope.

### 18. Steel safeguard measure

Topic:
Trade remedies / product-specific safeguards

Legal act name:
Commission Implementing Regulation (EU) 2019/159 of 31 January 2019 imposing definitive safeguard measures against imports of certain steel products

CELEX:
32019R0159

Legal type:
Implementing regulation

Publication date:
2019-02-01 in OJ L 31

Entry into force:
2019-02-02

Current status:
In force; repeatedly amended. Search results confirmed later amendments including 2025/1581 and 2026/846.

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2019/159/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2019/159/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2019/159/oj/eng/pdf

Key articles:
Art. 1 and Annex product categories / quota mechanics

Summary:
Main live EU safeguard instrument for steel imports.

Practical application:
Highly dynamic. Must be checked in TARIC and against latest amending acts on the actual import date.

Relationship with other legal acts:
Based on 2015/478 and 2015/755; amended by measures such as 2025/1581 and 2026/846.

Knowledge base ingestion suggestion:
Treat as a rolling measure set, not a static single rule.

### 19. Non-preferential / preferential origin base

Topic:
Rules of origin

Legal act name:
2013/94/EU: Council Decision of 26 March 2012 on the conclusion of the Regional Convention on pan-Euro-Mediterranean preferential rules of origin

CELEX:
32013D0094

Legal type:
Council decision

Publication date:
2013-02-26 in OJ L 54

Entry into force:
2012-03-26

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/dec/2013/94(1)/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/dec/2013/94(1)/oj/eng
PDF: https://eur-lex.europa.eu/eli/dec/2013/94(1)/oj/eng/pdf

Key articles:
Convention appendices and origin protocol structure are the operational core

Summary:
This is the treaty-level origin framework for PEM cumulation used across a large network of agreements.

Practical application:
Important for cumulation and product-specific rules in PEM trade.

Relationship with other legal acts:
Updated by Decision 1/2023 [2024/390] and Decision 2/2024 [2025/17].

Knowledge base ingestion suggestion:
Store separately from UCC origin rules as treaty-origin layer.

### 20. PEM update

Topic:
Rules of origin / cumulation

Legal act name:
Decision No 1/2023 of the Joint Committee of the Regional Convention on Pan-Euro-Mediterranean Preferential Rules of Origin of 7 December 2023 on the amendment of the Regional Convention on pan-Euro-Mediterranean preferential rules of origin [2024/390]

CELEX:
22024D0390

Legal type:
Decision

Publication date:
2024-02-19 in OJ L 2024/390

Entry into force:
2025-01-01 for the amended convention text

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/dec/2024/390/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/dec/2024/390/oj/eng
PDF: https://eur-lex.europa.eu/eli/dec/2024/390/oj/eng/pdf

Key articles:
Appendices and Annex III declaration text

Summary:
Modernised PEM origin rules and declaration text, relevant for cumulation and proof of origin.

Practical application:
Important for live origin analysis from 2025 onward where PEM rules apply.

Relationship with other legal acts:
Supplemented by transitional Decision 2/2024 [2025/17].

Knowledge base ingestion suggestion:
Ingest appendices separately because operational users need rule tables, not just decision text.

### 21. PEM transitional provisions

Topic:
Rules of origin / cumulation transition

Legal act name:
Decision No 2/2024 of the Joint Committee of the Regional Convention on Pan-Euro-Mediterranean Preferential Rules of Origin of 12 December 2024 amending Decision No 1/2023 in order to include transitional provisions in the amendments of the Regional Convention on pan-Euro-Mediterranean preferential rules of origin applicable as of 1 January 2025 [2025/17]

CELEX:
22025D0017

Legal type:
Decision

Publication date:
2025-01-09 in OJ L 2025/17

Entry into force:
2025-01-01

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/dec/2025/17/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/dec/2025/17/oj/eng
PDF: https://eur-lex.europa.eu/eli/dec/2025/17/oj/eng/pdf

Key articles:
Transitional provisions

Summary:
Important for practical origin claims during the changeover to the modernised PEM rules.

Practical application:
Needed where supplier declarations, certificates, or declarations span old/new PEM rule sets.

Relationship with other legal acts:
Directly modifies 2024/390 transition mechanics.

Knowledge base ingestion suggestion:
Store as transition overlay linked to 2024/390 and 2025/1728.

### 22. Proofs of origin procedure update

Topic:
Rules of origin / proof of origin

Legal act name:
Commission Implementing Regulation (EU) 2025/1728 of 8 August 2025 amending Implementing Regulation (EU) 2015/2447 as regards the procedures for issuing of or making out proofs of origin

CELEX:
32025R1728

Legal type:
Implementing regulation

Publication date:
2025-08-11 in OJ L 2025/1728

Entry into force:
2025-08-31; contains 2025-01-01 relevance for transition mechanics

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg_impl/2025/1728/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_impl/2025/1728/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_impl/2025/1728/oj/eng/pdf

Key articles:
Amending provisions to IA proof-of-origin procedures

Summary:
Current implementing update for issuance and making out of proofs of origin, especially PEM transition handling.

Practical application:
Relevant to EUR.1, origin declarations, and supplier declaration support logic.

Relationship with other legal acts:
Operationally linked to the PEM decisions and the base IA.

Knowledge base ingestion suggestion:
Keep as current procedural overlay for proof-of-origin workflows.

### 23. Agricultural import/export licences

Topic:
Import licences

Legal act name:
Commission Delegated Regulation (EU) 2016/1237 of 18 May 2016 supplementing Regulation (EU) No 1308/2013 with regard to the rules for applying the system of import and export licences and supplementing Regulation (EU) No 1306/2013 with regard to the rules on the release and forfeit of securities lodged for such licences

CELEX:
32016R1237

Legal type:
Delegated regulation

Publication date:
2016-07-30 in OJ L 206

Entry into force:
2016-08-06; later staged application dates also appear in metadata

Current status:
In force; amended

Official link:
https://eur-lex.europa.eu/eli/reg_del/2016/1237/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg_del/2016/1237/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg_del/2016/1237/oj/eng/pdf

Key articles:
Licence scope, securities, validity, sectoral annexes

Summary:
Core CAP import/export licence framework for affected agricultural sectors.

Practical application:
Important where TARIC or Access2Markets indicates a licence requirement for agricultural goods.

Relationship with other legal acts:
Paired with Implementing Regulation (EU) 2016/1239 and later amendments.

Knowledge base ingestion suggestion:
Store by sector and licence requirement.

### 24. Autonomous tariff suspensions

Topic:
Tariff suspensions

Legal act name:
Council Regulation (EU) 2021/2278 of 20 December 2021 suspending the Common Customs Tariff duties referred to in Article 56(2), point (c), of Regulation (EU) No 952/2013 on certain agricultural and industrial products, and repealing Regulation (EU) No 1387/2013

CELEX:
32021R2278

Legal type:
Regulation

Publication date:
2021-12-29 in OJ L 466

Entry into force:
2021-12-30; applies from 2022-01-01

Current status:
In force; amended; search results showed current version 2025-07-01

Official link:
https://eur-lex.europa.eu/eli/reg/2021/2278/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2021/2278/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2021/2278/oj/eng/pdf

Key articles:
Arts. 1-2 and Annex

Summary:
Framework for autonomous tariff suspensions of specified products.

Practical application:
Affects base customs duty but not anti-dumping duties.

Relationship with other legal acts:
Closely related to autonomous tariff quotas under 2021/2283.

Knowledge base ingestion suggestion:
Ingest as versioned product list by CN/TARIC code and review date.

### 25. Autonomous tariff quotas

Topic:
Tariff quotas

Legal act name:
Council Regulation (EU) 2021/2283 of 20 December 2021 opening and providing for the management of autonomous tariff quotas of the Union for certain agricultural and industrial products, and repealing Regulation (EU) No 1388/2013

CELEX:
32021R2283

Legal type:
Regulation

Publication date:
2021-12-22 in OJ L 458/33

Entry into force:
2021-12-23; applies from 2022-01-01

Current status:
In force; act has been changed; search results showed current version 2026-01-01

Official link:
https://eur-lex.europa.eu/eli/reg/2021/2283/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2021/2283/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2021/2283/oj/eng/pdf

Key articles:
Art. 1 and Annex

Summary:
Framework for autonomous Union tariff quotas by product and quota volume.

Practical application:
Use together with the live QUOTA database because balances and period availability are dynamic.

Relationship with other legal acts:
Managed operationally under IA arts. 49-54 and updated by amending Council regulations.

Knowledge base ingestion suggestion:
Store legal base plus live quota snapshots separately.

### 26. Dual-use restrictions

Topic:
Import / export restrictions; sanctions-adjacent controls

Legal act name:
Regulation (EU) 2021/821 of the European Parliament and of the Council of 20 May 2021 setting up a Union regime for the control of exports, brokering, technical assistance, transit and transfer of dual-use items (recast)

CELEX:
32021R0821

Legal type:
Regulation

Publication date:
2021-06-11 in OJ L 206

Entry into force:
2021-09-09

Current status:
In force

Official link:
https://eur-lex.europa.eu/eli/reg/2021/821/oj/eng

Full-text formats:
HTML: https://eur-lex.europa.eu/eli/reg/2021/821/oj/eng
PDF: https://eur-lex.europa.eu/eli/reg/2021/821/oj/eng/pdf

Key articles:
Arts. 3-6, 11, 16, 23

Summary:
Not a general import-licensing regime, but highly relevant for dual-use controlled goods and for customs enforcement.

Practical application:
Check product scope and annex status dynamically; do not confuse with general customs licensing.

Relationship with other legal acts:
May overlap with sanctions and national competent authority procedures.

Knowledge base ingestion suggestion:
Keep in a separate restrictions layer from pure customs-tariff measures.

## C. Official Database / API / Source List

Database/source name:
EUR-Lex / ELI

Official entry point:
https://eur-lex.europa.eu/

Responsible authority:
Publications Office of the European Union

Queryable content:
Legal acts, consolidated texts, OJ references, CELEX, ELI, document history

Login/API key required:
No

Useful fields:
CELEX, ELI, document type, publication date, current version date, OJ reference, legal status, relationships

Limitations:
Interactive pages can be WAF-gated

Recommended collection method:
Use ELI as canonical link; if WAF blocks page automation, fall back to CELEX PDF URLs and CELLAR SPARQL metadata

Database/source name:
CELLAR SPARQL endpoint

Official entry point:
https://publications.europa.eu/webapi/rdf/sparql

Responsible authority:
Publications Office of the European Union

Queryable content:
Legal metadata, ELI, CELEX, dates, relationships, subject metadata

Login/API key required:
No

Useful fields:
`cdm:resource_legal_id_celex`, `cdm:work_date_document`, `cdm:resource_legal_date_entry-into-force`, `cdm:resource_legal_eli`, `cdm:resource_legal_in-force`, amendment/repeal relationships

Limitations:
Ontology is non-trivial; direct literal matching was unreliable in this research, while `FILTER(STR(?celex)=...)` worked

Recommended collection method:
Use for bulk CELEX/date/relationship harvest before downloading full text from EUR-Lex

Database/source name:
TARIC consultation

Official entry point:
https://ec.europa.eu/taxation_customs/dds2/taric/taric_consultation.jsp?Lang=en

Responsible authority:
DG TAXUD / European Commission

Queryable content:
TARIC codes, measures, duty rates, additional codes, ADD/CVD, quotas, licences, suspensions, origin-based measures

Login/API key required:
No

Useful fields:
Commodity code, additional code, measure type, origin country, start date, end date, legal basis, footnotes, duty amount

Limitations:
Dynamic database; results depend on date, origin, and sometimes destination/formality context

Recommended collection method:
Use live queries; preserve query date, code, origin, and legal basis references

Database/source name:
Tariff quota consultation database

Official entry point:
https://ec.europa.eu/taxation_customs/dds2/taric/quota_consultation.jsp?Lang=en

Responsible authority:
DG TAXUD / European Commission

Queryable content:
Quota order numbers, periods, balances, exhaustion status

Login/API key required:
No

Useful fields:
Order number, CN/TARIC code, quota period, balance, legal basis, duty rate

Limitations:
Live balance only; not a substitute for the legal base act

Recommended collection method:
Store snapshots by query date and order number

Database/source name:
CLASS - Classification Information System

Official entry point:
https://webgate.ec.europa.eu/class-public-ui-web/

Responsible authority:
DG TAXUD / European Commission

Queryable content:
Classification regulations, CN notes, case law references, TARIC-linked classification material

Login/API key required:
No

Useful fields:
CN code, description, classification regulation, CN note, committee conclusion, court ruling

Limitations:
Support tool, not itself a binding act

Recommended collection method:
Use to enrich classification research and connect CN codes to interpretive materials

Database/source name:
EBTI / public BTI database

Official entry point:
https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/ebti-european-binding-tariff-information_en

Responsible authority:
DG TAXUD / Member State customs authorities

Queryable content:
Published BTI decisions, validity status, product descriptions

Login/API key required:
Public viewing no; applying through trader portal yes

Useful fields:
BTI reference, validity status, CN/TARIC code, product description, issuing customs authority

Limitations:
Confidential data redacted; decisions are product-specific and fact-specific

Recommended collection method:
Use as interpretive classification evidence; do not treat one BTI as universally applicable beyond its factual scope

Database/source name:
EU Customs Trader Portal

Official entry point:
https://taxation-customs.ec.europa.eu/how-i-can-access-eu-customs-trader-portal_en

Responsible authority:
European Commission / Member State customs

Queryable content:
AEO, BTI, INF, REX workflows for traders

Login/API key required:
Yes

Useful fields:
Application status, trader submissions, portal role requirements

Limitations:
Operational system, not a public legal repository

Recommended collection method:
Use only for workflow documentation and access paths

Database/source name:
Access2Markets

Official entry point:
https://trade.ec.europa.eu/access-to-markets/en/home

Responsible authority:
DG TRADE / European Commission

Queryable content:
Tariffs, rules of origin, import procedures, taxes, product requirements, statistics

Login/API key required:
No

Useful fields:
Product code, origin/destination, preferential duty, proof of origin type, procedure, requirement, document

Limitations:
Operational guidance portal; always trace law back to EUR-Lex / OJ

Recommended collection method:
Use as discovery and live operational lookup layer, not as the sole legal authority

Database/source name:
DG TAXUD UCC legislation page

Official entry point:
https://taxation-customs.ec.europa.eu/customs/union-customs-code/ucc-legislation_en

Responsible authority:
DG TAXUD

Queryable content:
Curated list of UCC package acts and amendments

Login/API key required:
No

Useful fields:
Act links, amendment notes, thematic summaries

Limitations:
Guidance page only

Recommended collection method:
Use to map thematic guidance back to CELEX acts

Database/source name:
EU AEO database

Official entry point:
https://ec.europa.eu/taxation_customs/dds2/eos/aeo_home.jsp?Lang=en

Responsible authority:
DG TAXUD / Member States

Queryable content:
Authorised Economic Operator public data

Login/API key required:
No for public lookup

Useful fields:
EORI, authorisation type, status, competent customs authority

Limitations:
Operational lookup, not legal basis

Recommended collection method:
Use to validate status and competent authority

Database/source name:
REX system

Official entry point:
https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/rex-registered-exporter-system_en

Responsible authority:
DG TAXUD / national competent authorities

Queryable content:
REX framework, trader portal path, validation path, country usage

Login/API key required:
Public validation no; registration workflow yes

Useful fields:
REX number, validity / revocation, registered exporter status

Limitations:
Agreement-specific operational use

Recommended collection method:
Keep as an origin-proof operational source and pair it with treaty-specific legal rules

Database/source name:
EU Customs Data Model (EUCDM)

Official entry point:
https://taxation-customs.ec.europa.eu/customs-4/union-customs-code/eu-customs-data-model-eucdm_en

Responsible authority:
DG TAXUD

Queryable content:
Structured customs data requirements derived from UCC DA/IA annexes

Login/API key required:
No

Useful fields:
Annex A/B mappings, data elements, codes, formats

Limitations:
Technical model, not binding text by itself

Recommended collection method:
Use to build machine-actionable declaration schema references

Database/source name:
EU Sanctions Map

Official entry point:
https://www.sanctionsmap.eu/

Responsible authority:
EU sanctions portal

Queryable content:
Restrictive measures by country/category with legal-act references

Login/API key required:
No

Useful fields:
Measure category, act reference, country, goods restrictions

Limitations:
Operational map only; authoritative law remains the underlying Council regulations/decisions in EUR-Lex

Recommended collection method:
Use to identify relevant sanctions acts, then pull the legal texts from EUR-Lex

## D. Knowledge Base Construction Recommendations

Which sources should be downloaded as full text:
- UCC, UCC DA, UCC IA
- 2658/87 and the current annual CN regulation
- Basic trade remedy regulations 2016/1036 and 2016/1037
- Safeguard framework acts 2015/478, 2015/755, 2019/287
- Current origin-layer acts that materially affect procedures, such as 2024/390, 2025/17, and 2025/1728
- Key sectoral licence / restriction acts that recur often, such as 2016/1237 and 2021/821
- Selected product-specific measures only if they are commercially important to the business

Which sources should be stored only as metadata and links:
- DG TAXUD thematic guidance pages
- DG TRADE policy pages
- WTO background pages
- Member State supplementary pages

Which data must be dynamically queried by product, origin country, and date:
- TARIC duty rates and measure sets
- ADD / CVD / safeguard live applicability
- Tariff quota balances and exhaustion
- Access2Markets preferential treatment, proof-of-origin route, and product requirements
- Sanctions and other geo-specific restrictions
- Product regulatory regimes such as REACH, RoHS, food, toy, medical-device, veterinary, chemicals, textiles, and electronics controls

How to structure files by CELEX / CN code / TARIC code / Article / Annex:
- Store law by CELEX first
- Store machine-facing classification and measure layers by CN/TARIC second
- Keep article and annex chunks as child objects
- Keep amendments as relationship edges rather than overwriting the earlier act

How to split legal text into knowledge base chunks:
- Chunk base acts by chapter and operational subject
- Split annex-heavy acts into separate annex files
- For origin conventions and quotas, split rule tables and appendices separately from the adopting act
- For trade-defence measures, store the measure summary separately from the full recital text

How to preserve legal citations, amendment history, and relationships:
- For every chunk preserve CELEX, ELI, OJ citation, document date, effective date, and current-status note
- Keep `amends`, `repeals`, `implemented_by`, `supplemented_by`, `displayed_in_taric`, and `overlaps_with` relationship fields
- Preserve multiple effective dates where an act enters into force on one date but applies operationally later

Suggested folder structure:

```text
eu_customs_knowledge_base/
  market_access/
  customs_procedure/
  tariff_taric/
  origin_rules/
  trade_remedies/
  quota_licence/
  customs_valuation/
  aeo_compliance/
  sanctions_restrictions/
  product_specific_requirements/
```

Recommended internal file naming:
- `CELEX_32013R0952_ucc.md`
- `CELEX_32015R2447_ucc_ia.md`
- `CN_2026_32025R1926_annex.csv`
- `TARIC_query_YYYY-MM-DD_code_origin.json`
- `QUOTA_query_YYYY-MM-DD_order_no.json`
- `TRADE_DEFENCE_32024R2754_bev_china.md`

## E. Uncertainties and Required Follow-up Information

The following cannot be determined conclusively without transaction-specific facts:
- Product name and technical description
- HS / CN / TARIC code
- Country of non-preferential origin
- Country of preferential origin claim
- EU Member State of import
- Import date
- Whether the importer wants MFN treatment, FTA preference, quota claim, inward processing, end-use, or another customs treatment
- Whether the goods fall into special regimes such as food, feed, animals, chemicals, REACH, toys, medical devices, dual-use, CITES, waste, timber, cultural goods, or sanctioned goods
- Producer / exporter identity, where trade-defence rates vary by company
- Related-party pricing facts for valuation
- Royalty / licence arrangements, assists, transport, and insurance allocation for valuation

## Origin Classification Notes

Preferential origin:
- Used to claim reduced or zero customs duty under an FTA, GSP, or other preferential arrangement.
- Requires compliance with treaty-specific product-specific rules and acceptable proof of origin.

Non-preferential origin:
- Used for MFN treatment and for trade-policy measures such as anti-dumping, countervailing duties, safeguards, embargoes, and some quotas/restrictions.

Suggested operational method to determine preferential treatment:
1. Identify CN/TARIC code and import date.
2. Identify claimed partner country and agreement.
3. Check Access2Markets / ROSA for the relevant agreement and product rule.
4. Confirm whether cumulation is available and whether the inputs qualify.
5. Confirm wholly obtained / sufficient working / tolerance / transport rules.
6. Confirm proof of origin type and issuer status: EUR.1, statement on origin, importer’s knowledge, approved exporter, or REX.
7. Confirm any quota or safeguard interaction in TARIC on the actual import date.

Suggested knowledge base tags:
- `preferential_origin`
- `non_preferential_origin`
- `rex`
- `proof_of_origin`
- `statement_on_origin`
- `fta_origin`
- `cumulation`
- `product_specific_rules`

## Tariff Classification Notes

Structure:
- HS = international 6-digit WCO system
- CN = EU 8-digit extension
- TARIC = CN plus EU additional subdivisions and live measures

Useful live fields for database construction:
- code
- goods_description
- measure_type
- duty_rate
- origin_country
- additional_code
- valid_from
- valid_to
- legal_basis
- notes

TARIC can display:
- conventional duties
- preferential duties
- anti-dumping duties
- countervailing duties
- quota measures
- licence requirements
- suspensions
- surveillance measures
- prohibitions / restrictions flags

## Customs Valuation Notes

Basic principles:
- Main method is transaction value under UCC Art. 70.
- Additions are under Art. 71.
- Deductions are under Art. 72.
- Alternative methods follow in order under Art. 74.

Related-party warning:
- Customs valuation and tax transfer pricing are not the same analysis.
- A transfer-pricing study can be relevant evidence but does not itself determine customs value.

## AEO / Compliance Notes

Legal basis:
- UCC Arts. 38-41, especially Art. 39 criteria
- Penalties at EU level: UCC Art. 42 requires Member States to lay down effective, proportionate and dissuasive penalties

AEOC vs AEOS:
- AEOC = customs simplifications
- AEOS = security and safety
- combined authorisation exists in practice

Compliance record relevance:
- Serious or repeated infringements of customs or tax legislation can affect authorisations and AEO standing.
- Penalty substance and procedure remain largely national.

Supplementary Member State sources used:
- Ireland Revenue, Customs Administrative Penalties: https://www.revenue.ie/en/tax-professionals/tdm/customs/customs-administrative-penalties/index.aspx
- France DGDDI, customs control / sanctions materials: https://www.douane.gouv.fr/

## Automation Plan for Future Collection

Recommended source priority:
1. CELLAR SPARQL for metadata normalization
2. EUR-Lex full-text download by CELEX / ELI
3. TARIC live queries
4. Access2Markets live queries
5. DG TAXUD thematic guidance capture
6. Member State supplementary sources

Recommended pipeline:
1. Maintain a seed list of CELEX numbers by topic.
2. Use CELLAR SPARQL to refresh dates, ELI, in-force flags, amendment links.
3. Download full text from ELI / EUR-Lex for framework acts and annex-heavy acts.
4. Snapshot live TARIC and QUOTA outputs only when product / origin / date context is known.
5. Use Access2Markets only as an operational lookup layer and map each conclusion back to EUR-Lex law.
6. For sanctions and product restrictions, resolve the live portal result into the underlying legal act and annex.

Recommended refresh cadence:
- Framework legislation: monthly metadata refresh
- TARIC and QUOTA: query per transaction / daily for monitoring use cases
- Access2Markets: per transaction or per sourcing country change
- Trade-defence measures: daily or weekly monitoring for exposed products
- AEO / trader portal process pages: quarterly

Recommended exception handling:
- If an ELI or legal-content page is blocked, fall back to CELEX PDF or CELLAR metadata
- If SPARQL returns inconsistent literal handling, use `FILTER(STR(?celex)=...)`
- Preserve both document-date and application-date fields to avoid timeline errors

````

## Notes
<!-- openclaw:human:start -->
<!-- openclaw:human:end -->

## Related
<!-- openclaw:wiki:related:start -->
### Referenced By

- [EU Customs Legal Knowledge Base](syntheses/eu-customs-legal-knowledge-base.md)
<!-- openclaw:wiki:related:end -->
