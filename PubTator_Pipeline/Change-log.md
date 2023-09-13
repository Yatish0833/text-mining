**Required input:** `PMID` (pubmed_Id's)

Now the PubTator pipeline is super stable and efficent with new improvemeents.
Has query mechanism to verify and skip if PubMed id already exist.
Stores every iteration in csv file.
Will perform parallel API request. Cutting down retriving annotations i.e., 30 mins for 1000 request to 100-120 seconds.

### Change Log (13/09/2023) ~SIVA

#### :rocket: 1. Shift to Asynchronous API Requests
Transitioned from a threaded approach to asynchronous programming with `asyncio` and `httpx` to boost data fetching efficiency. The `workers` parameter remains unused in this version and might be removed or repurposed in future iterations.

#### :zap: 2. Batch Processing in API Requests
Introduced batch processing to reduce the total number of HTTP requests made during data retrieval. This is facilitated by the new `fetch_data_batch_async` function, making data fetching quicker and smoother.

#### :shield: 3. Refined Error Handling and XML Parsing
Enhanced error handling with more robust management of potential XML parsing errors, maintained within the `process_response_batch` function. This enhancement safeguards the robustness of the data fetching process.

#### :hammer_and_wrench: 4. Data Storage and Aggregation Optimization
Continued using the `concept_data_dict`, a nested dictionary, for efficient data aggregation and streamlined its population process from batch responses, facilitating seamless data updating and extraction.

#### :memo: 5. Documentation and Code Readability
Updated docstrings and inline comments to reflect recent changes and enhance code readability, assisting in better maintenance and understanding of the code structure and functionalities.

#### :floppy_disk: 6. CSV Writing Logic Adjustment
Modified the CSV writing logic to append data in a single instance at the end of the function, reducing IO overhead and optimizing the data writing process.

#### :gear: 7. Incorporation of Nest Asyncio
Included `nest_asyncio.apply()` to ensure compatibility of the asyncio event loop with IPython environments, promoting a smoother development and runtime experience across different Python environments.

# Changelog (after Michael's code) V1

1. Merged test and train into one dataset.
2. Checked if we can give more than 100 through the GET method. I tried with 1000 and it worked for me, but it takes 3 minutes for every 100 requests. I did not time how long it took for 1000, but it's definitely less than 30 minutes.
3. Created a dictionary to store output (Key: Concept_name, Value: Pubmed_id's) - created a condition for the PubMed ID to be added to the list of values if it's not already present in the list for a given concept name.
4. Encapsulated the code in the "fetch_pubmed_concepts" function to be used recursively. It takes your DataFrame "df" and an optional parameter "max_pmid_count" to specify the maximum number of PMIDs you want to process. It returns the dictionary as the result.

## PubTator Pipeline V2 Change Log

Key functionalities of the PubTator pipeline version 2:

### Data Loading
- Loads Gene-Disease dataset from Figshare and combines test/train files.
- Reads data into a pandas DataFrame.

### PubTator API
- Queries PubTator API to fetch gene annotations for PMIDs.
- The API accepts a list of PMIDs and concepts like "gene".
- Makes requests in a loop for each PMID.
- Parses XML response to extract gene info.

Key highlights are:

- Loading and combining external dataset.
- Interacting with PubTator API to annotate entities.
- Storing annotations in a DataFrame structure.
- Analyzing annotations to find interactions.
- Outputting results to a file.
- Includes improvements like progress tracking and error handling.

### Change Log after V1 to V2

### Data Storage
- Stores gene annotations in a DataFrame.
- Contains columns for gene ID, name, PMID, and type.
- Handles multiple annotations per PMID.

### Post-Processing
- Finds gene-gene interactions by mapping PMIDs to concepts.
- Outputs interactions to a text file.

### Visualization
- Exploring suitable tools to visualize large network maps (underway...).

### Enhancements
- Added a progress bar to track API requests.
- Handles API errors and failures.
- Improved data structures for faster lookups.
- Added file output for analysis.
