# SNP Mutation Data 

## Code Description (Retrive-Mutation-Data.ipynb)

This Jupyter Notebook connects to the National Library of Medicine's FTP server to download 'mutation2pubtatorcentral.gz'. It retrieves the last modified date of the file and checks if it already exists locally. If the local file is older, it downloads the updated file. After download, it displays the last modified date and the file size. Finally, it gracefully exits the FTP session.

This script ensures that the local copy of the file is always up-to-date by comparing timestamps. It successfully downloaded 'mutation2pubtatorcentral.gz' from the FTP server, confirming the completion of the process.

## Code Summary (filter-SNPs.ipynb)

This Jupyter Notebook processes genetic mutation information. It extracts rows with RSID (SNP) annotations, excluding the "Type" column, and stores the filtered data in a TSV file.

The code also conducts analysis on the filtered data, counting the total RSID annotations, unique PMID identifiers, and unique SNPs (Concept IDs). The results indicate 3,069,248 RSID annotations, 507,356 unique PMIDs, and 1,118,528 unique SNPs. This code efficiently filters and analyzes genetic mutation data.

## Data Description (snp_mutation_data.tsv)

This TSV file contains genetic mutation data with the following columns:

i. PMID: PubMed abstract identifier.
ii. Concept ID: Corresponding database identifier (RSID).
iii. Mentions: Bio-concept mentions corresponding to the PubMed abstract.
iv. Resource: Various manually annotated resources are included in the files (e.g., tmVar, dbSNP, ClinVar, or a combination).

This data will be used in further assosiation model build.
