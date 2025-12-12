# Repository Architecture Map — Full Detail

This document provides a comprehensive, file-level Mermaid diagram of the repository.
It expands the high-level map into all major subfolders, including deep-dives,
reproducibility configs, datasets, environment specs, experiments, and detailed
diagram categories.

This map is intended for reviewers who want a deeper understanding of the internal 
structure and documentation layout of the portfolio.

# Repository Architecture Map — Full Detail (Vertical)

This diagram expands the high-level architecture map into all major folders and files,
including deep dives, diagrams, reproducibility artifacts, metadata files, and supporting documents.

```mermaid
flowchart LR

    R[kishoredb-research]

    %% Top-level folders
    R --> assets
    R --> datasets
    R --> diagrams
    R --> docs
    R --> metadata
    R --> sampledata
    R --> whitepapers

    %% Top-level files
    R --> readme[README]
    R --> citation[CITATION]
    R --> selectedworks[selected-works]
    R --> supportingworks[supporting-works]
    R --> publications[publications]
    R --> patents[patents]
    R --> talks[talks]
    R --> techprojects[tech-projects]
    R --> researchstatement[research-statement]
    R --> domainexpertise[domain-expertise]

    %% ======================
    %% assets (image bucket)
    %% ======================
    assets --> assetnote[images]

    %% ======================
    %% datasets (empty placeholder)
    %% ======================
    datasets --> datasetreadme[README]

    %% ======================
    %% diagrams folder
    %% ======================
    diagrams --> d_aegis[aegis]
    diagrams --> d_credscore[credscore]
    diagrams --> d_fraud[fraud-engine]
    diagrams --> d_hai[human-ai]
    diagrams --> d_methodology[methodology]
    diagrams --> d_smartcare[smartcare]
    diagrams --> d_readme[README]

    %% aegis diagrams
    d_aegis --> a_architecture[architecture]
    d_aegis --> a_eval[eval]
    d_aegis --> a_queryflow[query-flow]
    d_aegis --> a_schema[schema]
    d_aegis --> a_overview[overview]
    d_aegis --> a_deploy[deployment]

    %% credscore diagrams
    d_credscore --> cs_architecture[architecture]
    d_credscore --> cs_qualityflow[quality-flow]
    d_credscore --> cs_pipeline[pipeline]
    d_credscore --> cs_overview[overview]

    %% fraud-engine diagrams
    d_fraud --> fe_architecture[architecture]
    d_fraud --> fe_explainability[explainability-flow]
    d_fraud --> fe_modelpipeline[modeling-pipeline]
    d_fraud --> fe_featurepipeline[feature-pipeline]
    d_fraud --> fe_overview[overview]

    %% human-ai diagrams
    d_hai --> hai_agency[agency-interaction-loop]
    d_hai --> hai_cogdiv[cognitive-diversity-map]
    d_hai --> hai_decisionflow[decision-flow]
    d_hai --> hai_metacognition[metacognition]
    d_hai --> hai_transparency[transparency-loop]
    d_hai --> hai_overview[overview]

    %% methodology diagrams
    d_methodology --> meth_reprocycle[reproducibility-cycle]
    d_methodology --> meth_transparency[transparency-pipeline]
    d_methodology --> meth_eval[evaluation-loop]
    d_methodology --> meth_overview[overview]

    %% smartcare diagrams
    d_smartcare --> sc_architecture[architecture]
    d_smartcare --> sc_pipeline[pipeline]
    d_smartcare --> sc_overview[overview]

    %% ======================
    %% docs folder
    %% ======================
    docs --> deepdives[deep-dives]
    docs --> reproducibility[reproducibility]
    docs --> hcaidoc[human-centered-ai]
    docs --> methoddoc[research-methodology]
    docs --> docsreadme[README]

    %% deep dives
    deepdives --> dd_aegis[aegis-deep-dive]
    deepdives --> dd_credscore[credscore-deep-dive]
    deepdives --> dd_fraud[fraud-engine-deep-dive]
    deepdives --> dd_smartcare[smartcare-deep-dive]
    deepdives --> dd_cogdiv[cognitive-diversity-deep-dive]
    deepdives --> dd_interpret[interpretability-agency-deep-dive]
    deepdives --> dd_metacog[metacognition-deep-dive]

    %% reproducibility root
    reproducibility --> r_configs[configs]
    reproducibility --> r_datasets[datasets]
    reproducibility --> r_environment[environment]
    reproducibility --> r_experiments[experiments]
    reproducibility --> r_guidelines[reproducibility-guidelines]
    reproducibility --> r_readme[README]

    %% reproducibility/configs
    r_configs --> cfg_sampleconfig[sample-config]
    r_configs --> cfg_seedcontrol[seed-control]

    %% reproducibility/datasets
    r_datasets --> ds_creditapp[sample-credit-application]
    r_datasets --> ds_schema[sample-schema]
    r_datasets --> ds_transaction[sample-transaction]
    r_datasets --> ds_transcript[sample-transcript]

    %% reproducibility/environment
    r_environment --> env_python[python-environment]

    %% reproducibility/experiments
    r_experiments --> ex_aegis[aegis-eval-steps]
    r_experiments --> ex_credscore[credscore-eval-steps]
    r_experiments --> ex_fraud[fraud-engine-eval-steps]
    r_experiments --> ex_smartcare[smartcare-eval-steps]

    %% ======================
    %% metadata folder (placeholder)
    %% ======================
    metadata --> metadatafile[info-placeholder]

    %% ======================
    %% sample-data folder
    %% ======================
    sampledata --> samples_placeholder[sample-data-placeholder]

    %% ======================
    %% whitepapers folder
    %% ======================
    whitepapers --> wp_readme[README]
