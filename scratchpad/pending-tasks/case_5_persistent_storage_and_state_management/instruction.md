A machine learning training pipeline requires multiple worker functions to read from the same multi-gigabyte dataset simultaneously without re-downloading it from the internet. 

You need to provision a `modal.Volume` to persist data across function invocations. Write a Modal script containing a setup function that writes a dummy 1GB file to the volume, and a worker function that reads the file size from the mounted volume to verify its existence.

**Constraints:**
- Initialize the volume using `modal.Volume.from_name("dataset-vol", create_if_missing=True)`.
- Mount the volume to the worker function at the `/data` directory using the `volumes` parameter in the `@app.function()` decorator.
- Do NOT use ephemeral local storage (`/tmp`) to share the file between the two functions; all data passing must rely on the Modal Volume.