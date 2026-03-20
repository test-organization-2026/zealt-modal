A developer is migrating a simple workload to the cloud and needs to verify their Modal setup. 

You need to create a Python script `factorial_app.py` defining a Modal App named "factorial-app" and a remote function that calculates the factorial of a given integer. In the local entrypoint, execute this function remotely with the input `10` and print the result.

**Constraints:**
- Use `modal.App("factorial-app")` to instantiate the application.
- Decorate the calculation function with `@app.function()`.
- Invoke the function strictly using the `.remote()` method syntax.