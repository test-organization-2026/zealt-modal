A data engineering team must fetch and parse data from 1,000 URLs as quickly as possible. 

You need to write a Modal script `batch_fetch.py` containing a function `fetch_url(url: str)` that returns an HTTP status code. In the local entrypoint, take a mock list of 1,000 URLs and process them concurrently across multiple cloud containers, then aggregate the results.

**Constraints:**
- Use Modal's built-in `.map()` method on the remote function to trigger distributed fan-out execution.
- Do NOT use standard Python multiprocessing, `asyncio.gather()`, or sequential `for` loops to execute the network requests.
- Ensure the script collects and prints the finalized list of returned status codes.