---
pageType: source
id: source.eu-customs-source-portals
title: eu customs source portals
sourceType: local-file
sourcePath: /Users/xiaogong/Documents/Codex/2026-06-03/you-are-a-legal-regulatory-research/eu_customs_source_portals.csv
ingestedAt: 2026-06-07T03:30:02.308Z
updatedAt: 2026-06-07T03:30:02.308Z
status: active
---

# eu customs source portals

## Source
- Type: `local-file`
- Path: `/Users/xiaogong/Documents/Codex/2026-06-03/you-are-a-legal-regulatory-research/eu_customs_source_portals.csv`
- Bytes: 6323
- Updated: 2026-06-07T03:30:02.308Z

## Content
```text
"database_or_portal","official_entry_point","responsible_authority","queryable_content","login_required","useful_fields","limitations","recommended_collection_method"
"EUR-Lex / ELI","https://eur-lex.europa.eu/","Publications Office of the European Union","Legal acts, consolidated texts, OJ references, CELEX, ELI, document history","No","CELEX, ELI, act type, OJ reference, publication date, current version date, legal status, relationships","Interactive pages may be WAF-gated","Use ELI and CELEX-specific PDF/XML routes; supplement with CELLAR metadata"
"CELLAR SPARQL","https://publications.europa.eu/webapi/rdf/sparql","Publications Office of the European Union","Legal metadata, dates, ELI, legal status, relationships","No","resource_legal_id_celex, work_date_document, resource_legal_date_entry-into-force, resource_legal_eli, resource_legal_in-force","Ontology learning curve; literal matching quirks","Use FILTER(STR(?celex)=...) and VALUES for bulk pulls"
"TARIC consultation","https://ec.europa.eu/taxation_customs/dds2/taric/taric_consultation.jsp?Lang=en","DG TAXUD / European Commission","TARIC codes, measures, duties, quotas, ADD/CVD, licences, suspensions","No","commodity code, additional code, measure type, duty rate, origin country, legal basis, valid from/to","Dynamic, transaction-dependent","Run live per product/origin/date and preserve snapshot metadata"
"QUOTA consultation","https://ec.europa.eu/taxation_customs/dds2/taric/quota_consultation.jsp?Lang=en","DG TAXUD / European Commission","Quota balances, order numbers, periods, rates","No","order number, code, quota period, balance, legal basis, duty rate","Balance data changes over time","Store snapshots by order number and query date"
"CLASS","https://webgate.ec.europa.eu/class-public-ui-web/","DG TAXUD / European Commission","Classification regulations, CN notes, case law references, TARIC-linked classification materials","No","CN code, description, regulation reference, CN note, case-law reference","Support tool, not itself binding law","Use to enrich tariff-classification research"
"EBTI / BTI information","https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/ebti-european-binding-tariff-information_en","DG TAXUD / Member State customs authorities","Public BTI information and access path to BTI database","Public lookup no; applications yes","BTI reference, validity status, CN/TARIC code, issuing authority","Confidential data redacted; product-specific facts matter","Use as interpretive evidence, not as universal classification law"
"EU Customs Trader Portal","https://taxation-customs.ec.europa.eu/how-i-can-access-eu-customs-trader-portal_en","European Commission / Member State customs","AEO, BTI, INF, REX trader workflows","Yes","workflow path, role requirements, connected systems","Operational portal, not a public legal repository","Document access path only"
"Access2Markets","https://trade.ec.europa.eu/access-to-markets/en/home","DG TRADE / European Commission","Tariffs, rules of origin, procedures, taxes, requirements, statistics","No","product code, origin/destination, preferential duty, proof type, procedure, requirement, document","Guidance and operational lookup, not sole legal authority","Use for discovery and live lookup, then trace back to EUR-Lex"
"DG TAXUD UCC legislation page","https://taxation-customs.ec.europa.eu/customs/union-customs-code/ucc-legislation_en","DG TAXUD","Curated UCC legal package and amendment mapping","No","act links, amendment summaries, thematic relevance","Guidance page only","Use to maintain the CELEX seed list"
"EU AEO database","https://ec.europa.eu/taxation_customs/dds2/eos/aeo_home.jsp?Lang=en","DG TAXUD / Member States","Public AEO records","No","EORI, authorisation type, status, competent authority","Operational lookup only","Use to validate AEO status and competent authority"
"EORI validation","https://ec.europa.eu/taxation_customs/dds2/eos/eori_home.jsp?Lang=en","DG TAXUD / Member States","EORI validity","No","EORI number, validity","Not a legal source","Use only as operator-validation aid"
"REX system","https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/rex-registered-exporter-system_en","DG TAXUD / national competent authorities","REX framework, trader portal path, validation path, country usage","Public validation no; registration workflow yes","REX number, validity, revocation date","Agreement-specific use and national registration steps","Use as operational origin-proof source linked to treaty rules"
"EUCDM","https://taxation-customs.ec.europa.eu/customs-4/union-customs-code/eu-customs-data-model-eucdm_en","DG TAXUD","Structured customs data requirements derived from UCC annexes","No","annex mappings, data elements, codes, formats","Technical model, not a binding text by itself","Use to build machine-readable customs declaration schemas"
"DG TRADE trade defence","https://policy.trade.ec.europa.eu/enforcement-and-protection/trade-defence_en","DG TRADE / European Commission","Trade defence policy pages and case-navigation leads","No","case context, latest OJ publications, monitoring pages","Policy/guidance pages only","Use as case-discovery layer then pull implementing acts from EUR-Lex"
"EU Sanctions Map","https://www.sanctionsmap.eu/","EU sanctions portal","Restrictive measures by country/category with legal-act references","No","measure category, country, act reference, goods restrictions","Operational map; not the authoritative legal text","Use to identify relevant sanctions acts, then retrieve them from EUR-Lex"
"Ireland Revenue customs penalties","https://www.revenue.ie/en/tax-professionals/tdm/customs/customs-administrative-penalties/index.aspx","Irish Revenue","National customs administrative penalty guidance","No","rule reference, penalty amount, procedure","National-only; not EU-wide","Use as supplementary Member State implementation source"
"France DGDDI customs control and restrictions pages","https://www.douane.gouv.fr/","Direction Générale des Douanes et Droits Indirects","National customs controls, sanctions, and restrictions information","No","control powers, restrictions, sanction references","National-only; page coverage is topic-specific","Use as supplementary Member State implementation source"

```

## Notes
<!-- openclaw:human:start -->
<!-- openclaw:human:end -->

## Related
<!-- openclaw:wiki:related:start -->
### Referenced By

- [EU Customs Legal Knowledge Base](syntheses/eu-customs-legal-knowledge-base.md)
<!-- openclaw:wiki:related:end -->
