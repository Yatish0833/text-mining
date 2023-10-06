---

### **PubMed Abstract Fetcher Tool Summary**

The code is designed to fetch abstracts of scientific articles from PubMed using their PMID (PubMed Identifier). 

#### **PMIDFetcher Class**

The `PMIDFetcher` class is the heart of this tool:
- During its initialization, the class sets:
  - Local cache file for storing fetched abstracts.
  - User's email and API key for accessing the NCBI Entrez system.
  
- **Methods**:
  - `fetch_abstracts`: Fetches abstracts given a list of PMIDs.
  - `retrieve`: Responsible for fetching abstracts in batches for better efficiency.
  
Abstracts fetched are stored in a JSON file named `cached_abstracts.json`. In cases where an abstract is not available for a PMID, that PMID is recorded in a separate TSV file named `no_abstract.tsv`.

For the batched fetching process, a progress bar is displayed using the `tqdm` library, offering a visual representation of the retrieval's progress. The script also periodically saves the fetched abstracts to the cache, ensuring data is not lost in long retrieval processes.

#### **Utility Functions**

- `read_pmids_from_file`: Extracts and returns unique PMIDs from file snp_mutation_data.tsv (Contains all the PMID where SNP's context is present).

#### **Main Execution**

When the script is executed:
- It initializes the fetcher with a provided API key.
- Starts the abstract retrieval process using the list of PMIDs.
- Displays statistics post retrieval.

#### **Stats Reported**

- Total PMIDs in cache: 429,985
- PMIDs without abstracts: 78,364
- Cache file size: ~450.58 MB

---