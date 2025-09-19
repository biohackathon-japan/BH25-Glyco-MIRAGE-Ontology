---
title: 'Translating and Formalizing the MIRAGE Guidelines to a Prototype MIRAGE Ontology and DCAT3 Extension Vocabulary for Glycomics Data Management'
title_short: 'BioHackJP25: First Implementation of Glyco MIRAGE Ontology and DCAT extension Vocab'
tags:
  - Semantic web
  - Ontologies
  - Glycomics
  - MIRAGE
  - FAIR data principles
  - DCAT3
  - Knowledge Base
  - Glycomics Data Integration
  - Metadata
authors:
  - name: Achille Zappa
    orcid: 0000-0003-4040-9620
    affiliation: 1
  - name: Achille Zappa
    orcid: 0000-0003-4040-9620
    affiliation: 1  
affiliations:
  - name: SOKA University, Glycan and Life Systems Integration Center (GaLSIC), Hachioji, Tokyo, Japan
    index: 1
  - name: SOKA University, Glycan and Life Systems Integration Center (GaLSIC), Hachioji, Tokyo, Japan
    index: 1
date: 19 September 2025
cito-bibliography: paper.bib
event: BH25JP
biohackathon_name: "DBCLS BioHackathon 2025"
biohackathon_url:   "https://2025.biohackathon.org/"
biohackathon_location: "Mie, Japan, 2025"
group: Glyco-MIRAGE-Ontology
git_url: https://github.com/biohackathon-japan/BH25-Glyco-MIRAGE-Ontology
authors_short: Zappa A.
---

# Abstract

The Minimum Information Required for A Glycomics Experiment (MIRAGE) guidelines have established comprehensive reporting standards for glycomics research, yet their implementation in semantic web technologies remains limited. We present the first comprehensive semantic formalization of MIRAGE guidelines through an integrated RDF ontology framework comprising the MIRAGE Ontology and MIRAGE-DCAT3 vocabulary.
The MIRAGE Ontology models glycan structures, biological specimens, analytical instruments, and experimental processes with formal OWL semantics and SHACL validation constraints. The complementary MIRAGE-DCAT3 vocabulary extends W3C DCAT3 with glycomics-specific metadata properties for dataset cataloging and discovery. Our implementation addresses critical challenges in glycomics data interoperability through comprehensive mappings to established ontologies including GlycoRDF, PSI-MS, and DCTERMS.
This semantic framework enables automated quality assessment, federated data querying, and enhanced reproducibility in glycomics research, supporting broader adoption of FAIR principles in the glycobiology community. The framework demonstrates comprehensive coverage of MIRAGE reporting requirements across multiple analytical platforms including mass spectrometry, liquid chromatography, capillary electrophoresis, NMR spectroscopy, and lectin microarray analysis.


## Author information

```yaml
authors:
  - name: Achille Zappa
    affiliation: 1
affiliations:
  - name: SOKA University, Glycan and Life Systems Integration Center (GaLSIC), Hachioji, Tokyo, Japan
    index: 1

```


# Introduction

As part of the DBCLS BioHackathon 2025, we here report on the work done toward Translating and Formalizing the MIRAGE Guidelines to a Prototype MIRAGE Ontology and DCAT3 Extension Vocabulary for Glycomics Data Management. 
The field of glycomics has experienced rapid growth in analytical capabilities and data generation, yet challenges persist in data standardization, integration, and reproducibility. The MIRAGE (Minimum Information Required for A Glycomics Experiment) project was initiated in 2011 to address these challenges by establishing comprehensive reporting guidelines for diverse glycomics analytical methods (York et al., 2014). Since its inception, MIRAGE has published specific guidelines for mass spectrometry (Kolarich et al., 2013), liquid chromatography (Campbell et al., 2019), sample preparation (Struwe et al., 2016), glycan microarrays (Liu et al., 2017), capillary electrophoresis (Campbell et al., 2014; Royle et al., 2022), and lectin microarrays (Tateno et al., 2025).
Despite the comprehensive nature of MIRAGE guidelines, their implementation in computational systems has been limited by the lack of machine-readable semantic representations. While tools like GlycoWorkbench and repositories such as UniCarb-DR and GlycoPOST have incorporated MIRAGE principles, no comprehensive semantic ontology exists to enable fully automated processing, validation, and integration of MIRAGE-compliant data.
The adoption of semantic web technologies in life sciences has demonstrated significant benefits for data integration, quality assessment, and knowledge discovery. Notable successes include the Gene Ontology, Human Phenotype Ontology, and domain-specific implementations such as GlycoRDF and GlycoCoO (Ranzinger et al., 2012). These ontologies enable sophisticated querying, automated reasoning, and cross-database integration through standardized RDF (Resource Description Framework) representations.
The FAIR (Findable, Accessible, Interoperable, Reusable) principles have emerged as fundamental guidelines for scientific data management, with growing recognition that semantic technologies are essential for achieving true data interoperability. In glycomics, the complexity of molecular structures, diverse analytical methodologies, and heterogeneous data formats present particular challenges for FAIR data implementation.
Recent developments in semantic web standards, particularly the W3C Data Catalog Vocabulary (DCAT) version 3 and the Shapes Constraint Language (SHACL) and SHEX, provide new opportunities for implementing domain-specific metadata schemas with validation capabilities. DCAT3 introduces enhanced support for dataset metadata descriptions, versioning, data quality information, and service descriptions, while SHACL enables formal validation of RDF data against defined schemas and constraints.
This paper presents the first semantic implementation of MIRAGE guidelines through an integrated ontology framework. Our approach addresses three critical requirements: (1) coverage of MIRAGE reporting requirements across all published guidelines, (2) integration with existing semantic web standards and glycomics ontologies, and (3) support for automated validation and quality assessment.

## The MIRAGE Ontology

The MIRAGE Ontology represents a foundational semantic infrastructure for glycomics research, providing the first formal ontological representation of the complete MIRAGE guidelines ecosystem. The MIRAGE Ontology Prototype aims towards a systematic semantic formalization of the complete MIRAGE (Minimum Information Required for A Glycomics Experiment) guidelines, implemented as a comprehensive OWL ontology that transforms years of community-developed reporting standards into machine-actionable knowledge structures. This prototype addresses a critical gap in glycomics informatics by providing formal semantic representations of experimental entities, analytical processes, and data relationships that enable automated reasoning, validation, and integration across heterogeneous glycomics research environments.
The ontology is structured around a hierarchical knowledge architecture that captures the essential conceptual domains of glycomics experimentation. At its core, it models five fundamental entity classes: compound hierarchies encompassing glycan structures from simple monosaccharides to complex glycoconjugates; specimen classifications covering biological samples across their complete experimental lifecycle from collection through analytical preparation; instrument taxonomies that represent analytical hardware configurations with detailed component-level modeling; method frameworks describing analytical techniques across multiple analytical platforms; and data structures that model experimental outputs from raw instrument signals through processed analytical results.
The ontological framework incorporates sophisticated semantic modeling capabilities that extend beyond traditional taxonomic classification. It defines annotation properties that encode MIRAGE requirement levels (required, conditional, optional) directly within the knowledge structure, enabling automated compliance checking and validation workflows. Integration with established glycomics resources occurs through formal semantic mappings to GlycoRDF entities, references to PSI-MS controlled vocabularies, and alignment with PROV-O provenance standards.

## The MIRAGE-DCAT3 Vocabulary

The MIRAGE-DCAT3 vocabulary serves as a semantic bridge between the rich domain knowledge captured in the MIRAGE Ontology and the practical requirements of modern data catalog infrastructure. This vocabulary provides a specialized extension of the W3C Data Catalog Vocabulary (DCAT3) standard, purpose-engineered to enable systematic cataloging, discovery, and access of glycomics datasets through knowledge-based data platforms while maintaining full compatibility with conventional repository systems.
The vocabulary extends core DCAT entities—including Catalog, Dataset, Distribution, and DataService—with domain-specific classes and properties that capture the unique characteristics of glycomics experimental data. Through integration with complementary standards including ODRL (Open Digital Rights Language) for usage policy expression and PROV-O (Provenance Ontology) for comprehensive provenance tracking, the vocabulary enables expression of complex data governance scenarios including usage restrictions, access terms, attribution requirements, and detailed provenance chains.
The vocabulary defines specialized properties for linking cataloged datasets to glycan structure identifiers, instrument configurations, methodological parameters, and quality metrics, creating a FAIR-compliant catalog environment where MIRAGE-annotated datasets can be automatically validated, cross-referenced, and integrated across institutional and disciplinary boundaries.
Together, these complementary semantic resources establish a two-layer architecture that addresses both the knowledge representation requirements of glycomics domain modeling and the practical infrastructure needs of modern data management systems. The MIRAGE Ontology provides the foundational domain knowledge and experimental modeling capabilities that enable semantic description of glycomics research outputs, while the MIRAGE-DCAT3 vocabulary provides the cataloging and data management layer that makes this knowledge discoverable and actionable within real-world research infrastructures. This architectural separation enables the ontology to evolve independently with MIRAGE guideline updates and community feedback while maintaining stable integration pathways for existing glycomics data repositories and emerging data sharing platforms like the GlyCosmos Portal and the work in progress for the HGA Human Glycome Atlas project and its core TOHSA-KB semantic knowledge base.
The semantic formalization enables transformative capabilities for glycomics research including automated quality control validation against MIRAGE requirements, federated querying across distributed datasets, and reproducibility assessment through formal experimental context representation. The ontology supports complex research scenarios such as comparative method development, cross-laboratory validation studies, and large-scale meta-analyses that require precise semantic understanding of experimental parameters and their relationships.
This prototype provides the foundational infrastructure for next-generation glycomics data management systems that fully realize FAIR principles while supporting the analytical complexity and methodological diversity that defines modern glycobiology research.


# Methods

## Ontology Design Framework

Our semantic implementation follows established ontology engineering methodologies and semantic web best practices. The framework adopts a modular architecture comprising two complementary vocabularies:
1.	MIRAGE Ontology: Core domain ontology modeling glycomics experimental entities, processes, and relationships
2.	MIRAGE-DCAT3 Vocabulary: Metadata vocabulary extending DCAT3 for glycomics-specific dataset and service descriptions
This separation enables flexible deployment scenarios where the core ontology can be used independently for knowledge representation, while the DCAT3 extension provides specialized metadata capabilities for data catalog applications.

## Requirements Analysis

We conducted comprehensive analysis of all published MIRAGE guidelines to extract ontology requirements:
1. Mass Spectrometry Guidelines: Instrument specifications, ion sources, data acquisition parameters
2. Sample Preparation Guidelines: Biological specimens, purification procedures, chemical modifications
3. Liquid Chromatography Guidelines: Column specifications, mobile phases, separation conditions
4. Glycan Microarray Guidelines: Array fabrication, binding assays, data analysis
5. Capillary Electrophoresis Guidelines: Separation mechanisms, detection methods, buffer systems
6. Lectin Microarray Guidelines: Lectin specifications, binding quantification, array layouts
For each guideline, we identified required and conditional metadata fields, their data types, validation constraints, and interdependencies.

## Class Hierarchy Design

The MIRAGE Ontology employs a hierarchical class structure organized around five primary branches:
1.	Compound Hierarchy: Glycans, glycoconjugates, and aglycons with detailed subclassing
2.	Specimen Hierarchy: Biological samples categorized by source and preparation method
3.	Instrument Hierarchy: Analytical instruments with component-based modeling
4.	Method Hierarchy: Experimental procedures and analytical techniques
5.	Data Hierarchy: Raw and processed data types with format specifications
Each hierarchy incorporates disjointness constraints to prevent logical inconsistencies and enable automated reasoning for data validation.

## External Ontology Integration

The framework incorporates mappings to established ontologies and controlled vocabularies:
1. GlycoRDF: Glycan structure and biological source mappings using owl:equivalentClass
2. PSI-MS Ontology: Mass spectrometry terminology via rdfs:seeAlso references
3. DCTERMS: Metadata elements through rdfs:subPropertyOf relationships
4. PROV-O: Provenance tracking using prov:Activity and prov:Entity superclasses
5. DCAT3: Dataset catalog integration via vocabulary extension


## Validation Framework

SHACL shapes provide formal validation constraints covering:
1. Cardinality Constraints: Required vs. optional properties based on MIRAGE requirements
2. Value Constraints: Enumerated lists, pattern matching, and cross-reference validation
3. Structural Constraints: Property chains and complex dependency rules
4. Quality Constraints: Data completeness and consistency checks


# Results

## Ontology Structure and Coverage

The MIRAGE Ontology comprises classes organized in a hierarchical structure with comprehensive coverage of glycomics experimental entities. The class distribution reflects the complexity of glycomics workflows:
1. Compound Classes: Glycan taxonomy including monosaccharides, oligosaccharides, polysaccharides, and glycoconjugates
2. Specimen Classes: Biological samples categorized by source type and preparation method
3. Instrument Classes: Analytical instruments with detailed component specifications
4. Method Classes: Experimental procedures covering all major analytical techniques
5. Data Classes: Experimental data types with format and quality metadata
6. Process Classes: Sample preparation and analytical workflows
The ontology defines datatype properties with explicit domain-range specifications and XSD datatype constraints. These properties capture quantitative measurements, categorical classifications, and textual descriptions required by MIRAGE guidelines. Additionally, object properties model relationships between experimental entities, enabling complex workflow representations and data provenance tracking.


## DCAT3 Integration

The MIRAGE-DCAT3 vocabulary extends the W3C DCAT3 specification with specialized properties for glycomics metadata. This extension provides comprehensive coverage of dataset-level metadata while maintaining full compatibility with DCAT3 core classes and properties.
Key extension areas include:
1. Experiment Metadata: Research context, personnel, institutional affiliations
2. Sample Metadata: Biological context, preparation protocols, quality measures
3. Method Metadata: Instrument configurations, analytical parameters, software versions
4. Quality Metadata: Validation status, confidence scores, compliance indicators
5. Provenance Metadata: Data generation workflows and processing histories
The vocabulary includes specialized classes for bioimaging experiments and plate-based assays, addressing specific requirements identified in recent MIRAGE guidelines.


## Semantic Validation Capabilities

The framework incorporates comprehensive SHACL validation shapes covering requirement levels specified in MIRAGE guidelines:
1. Required Properties: Mandatory fields for basic experiment description
2. Conditional Properties: Fields required under specific experimental conditions
3. Optional Properties: Fields for enhanced metadata quality
4. Cross-Validation Rules: Constraint sets ensuring logical consistency
Validation shapes incorporate sophisticated logic for handling conditional requirements, such as ion source-specific parameters in mass spectrometry experiments and separation mode-specific fields in liquid chromatography methods.

## Integration with Existing Resources

The ontology provides comprehensive mappings to established glycomics resources:
1. GlycoRDF Alignment: owl:equivalentClass mappings for core glycan entities
2. PSI-MS Integration: rdfs:seeAlso references to mass spectrometry terms
3. DCTERMS Extensions: rdfs:subPropertyOf relationships for metadata properties
4. PROV-O Integration: Systematic use of provenance classes for workflow modeling
These mappings enable seamless integration with existing glycomics databases and semantic web resources while maintaining compatibility with broader life sciences ontology frameworks.


# Discussion

## Advancing FAIR Glycomics Data Management

Our semantic implementation of MIRAGE guidelines represents a significant advancement in making glycomics data FAIR. The ontological framework directly addresses each FAIR principle:
Findability is enhanced through comprehensive metadata schemas that enable sophisticated querying across multiple experimental dimensions. The DCAT3 integration provides standardized catalog metadata supporting federated search capabilities and automated dataset discovery.
Accessibility is improved through semantic interoperability standards that eliminate vendor-specific data silos. The ontology's mapping to established standards ensures long-term accessibility regardless of changes in specific database implementations.
Interoperability is achieved through formal semantic definitions that enable automated data integration across heterogeneous sources. Comprehensive property mappings and controlled vocabularies provide a foundation for cross-database queries and comparative analyses.
Reusability is enhanced through explicit representation of experimental context, quality metrics, and provenance information. The validation framework ensures that reused data meets established quality standards and provides sufficient metadata for proper interpretation.


## Technical Innovation and Contributions

Several technical innovations distinguish our implementation from previous glycomics informatics approaches:
Comprehensive Coverage: Unlike previous partial implementations, our ontology covers all published MIRAGE guidelines with detailed property specifications and validation constraints. This comprehensive coverage eliminates gaps that have previously limited automated processing capabilities.
Modular Architecture: The separation between core ontology and metadata vocabulary enables flexible deployment scenarios. Organizations can implement the core ontology for internal knowledge representation while adopting the DCAT3 extension for external data sharing.
Advanced Validation: The SHACL-based validation framework goes beyond simple data type checking to include complex logical constraints and cross-field dependencies. This enables automated quality assessment that supports rigorous data standards.
Multi-Modal Integration: The framework's support for complex experimental workflows involving multiple analytical techniques addresses a critical gap in existing glycomics informatics infrastructure. This capability is essential for modern systems biology approaches to glycomics research.


## Impact on Glycomics Research Practices

The semantic implementation provides several immediate benefits for glycomics research:
Automated Quality Control: Researchers can validate their experimental metadata against MIRAGE requirements without manual checklist review. The validation framework identifies missing fields, inconsistent values, and logical contradictions, improving data quality before publication or database submission.
Enhanced Reproducibility: Semantic descriptions enable automated workflow reproduction and comparative analyses across laboratories. The explicit representation of experimental context reduces ambiguity and supports more reliable research synthesis.
Improved Data Integration: The common semantic framework enables seamless integration of data from multiple sources, supporting large-scale meta-analyses and comparative studies that were previously technically challenging.
Knowledge Discovery: Semantic querying capabilities enable novel research questions that span multiple experiments and analytical techniques. Researchers can identify patterns and relationships that emerge only at the meta-analytical level.


## Challenges and Future Directions

Several challenges remain in the broader adoption of semantic glycomics data management:
Implementation Complexity: The sophisticated nature of the ontology requires significant technical expertise for full implementation. Organizations may need specialized training or consultant support to realize the framework's full potential.
Cultural Adoption: Semantic web technologies remain unfamiliar to many experimental glycobiologists. Successful adoption requires user-friendly tools that abstract the underlying complexity while providing semantic benefits.
Evolution Management: As MIRAGE guidelines continue to evolve, maintaining semantic consistency across ontology versions presents ongoing challenges. Version control and backward compatibility strategies require careful planning.
Future developments will focus on tool integration, machine learning applications, and community building to accelerate adoption within the glycomics research community. The framework provides a solid foundation for next-generation glycomics informatics infrastructure that realizes the potential of FAIR data principles.


# Conclusion

We have developed the first comprehensive semantic implementation of MIRAGE guidelines, providing a robust foundation for FAIR glycomics data management. The integrated ontology framework comprises two complementary vocabularies that together address the full spectrum of glycomics experimental metadata requirements.
The MIRAGE Ontology provides detailed representations of experimental entities, processes, and relationships with formal semantic definitions that enable automated reasoning and validation. The complementary MIRAGE-DCAT3 Vocabulary extends established metadata standards with glycomics-specific capabilities while maintaining interoperability with broader semantic web infrastructure.
Our implementation demonstrates that comprehensive semantic frameworks can be developed for complex analytical domains without sacrificing usability or performance. The validation capabilities provide automated quality control, while the semantic querying capabilities enable novel research approaches that span multiple experiments and analytical techniques.
The framework's modular architecture and comprehensive external mappings ensure compatibility with existing glycomics resources while providing a migration pathway toward more sophisticated semantic data management. The framework provides essential infrastructure for next-generation glycomics informatics that truly realizes FAIR data principles.



## Acknowledgements

We thank the MIRAGE working groups for their foundational work in establishing glycomics reporting guidelines. We acknowledge the contributors to GlycoRDF, PSI-MS, and other ontology projects whose work provided essential foundations for this implementation. This research is supported by the HGA Project, championed by the Ministry of Education, Culture, Sports, Science and Technology (MEXT), the Joint Usage/Research Center Glycoscience Cooperative Network (J-GlycoNet), the Bioscience Database Center (NBDC) Life Science Database Integration Promotion Program, and Japan Science and Technology Agency (JST). Acknowledging Prof. Kiyoko F. Aoki-Kinoshita at GaLSIC, SOKA University, Hachioji Tokyo and Kinoshita-Lab for the work on MIRAGE, GlycoRDF, and semantic Knowledge-bases and resources for Glycoscience data formalization and integration like our GlyCosmos Portal and the work in progress with our HGA Human Glycome Atlas project based also on the semantic TOHSA-KB knowledge base. The BioHackathon 2025 in Japan, organized by the Database Center for Life Science (DBCLS).


## References

Aoki-Kinoshita, K.F., et al. (2024). The Human Glycome Atlas Project for cataloging all glycan-related omics data in human. Glycobiology, 34(11), cwae052.
Aoki-Kinoshita, K.F., Matsui, Y., Akune-Taylor, Y., Zappa, A. (2025). Knowledgebase TOHSA: Gateway to a new era in life sciences. Glycoforum, 28, A10.
Campbell, M.P., et al. (2014). Guidelines for reporting the use of capillary electrophoresis in glycomics. Electrophoresis, 35(19), 2756-2764.
Campbell, M.P., et al. (2019). The minimum information required for a glycomics experiment (MIRAGE) project: LC guidelines. Glycobiology, 29(5), 349-354.
Kolarich, D., et al. (2013). The minimum information required for a glycomics experiment (MIRAGE) project: Improving the standards for reporting mass spectrometry-based glycoanalytic data. Molecular & Cellular Proteomics, 12(4), 991-995.
Lee, S., Ono, T., Masaaki, S., Fujita, A., Matsubara, M., Zappa, A., Yamada, I., et al. (2025). Updates implemented in version 4 of the GlyCosmos Glycoscience Portal. Analytical and Bioanalytical Chemistry, 417(5), 907-919.
Liu, Y., et al. (2017). The minimum information required for a glycomics experiment (MIRAGE) project: improving the standards for reporting glycan microarray-based data. Glycobiology, 27(4), 280-284.
Ranzinger, R., et al. (2012). Glycan structure and its functional role in the biological process: semantic web approach. Current Bioinformatics, 7(2), 200-210.
Royle, L., et al. (2022). The minimum information required for a glycomics experiment (MIRAGE): reporting guidelines for capillary electrophoresis. Glycobiology, 32(7), 580-593.
Struwe, W.B., et al. (2016). The minimum information required for a glycomics experiment (MIRAGE) project: sample preparation guidelines for reliable reporting of glycomics datasets. Glycobiology, 26(9), 907-910.
Tateno, H., et al. (2025). The minimum information required for a glycomics experiment (MIRAGE) project: improving the standards for reporting lectin microarray data. Glycobiology, 35(2), cwaf006.
Varki, A., et al. (2015). Symbol nomenclature for graphical representations of glycans. Glycobiology, 25(12), 1323-1324.
York, W.S., et al. (2014). MIRAGE: The minimum information required for a glycomics experiment. Glycobiology, 24(5), 402-406.
Zappa, A., Aoki-Kinoshita, K.F., Akune-Taylor, Y. (2025). Semantic Web Integration in Life Science Data. Encyclopedia of Bioinformatics and Computational Biology (Second Edition), 4.
