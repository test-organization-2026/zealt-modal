An AI engineer wants to deploy a Hugging Face text-generation model without incurring massive cold-start penalties on expensive hardware. 

You need to create a Modal class-based function `TextGenerator` that provisions an A10G GPU and exposes a `generate(prompt: str)` method. Load the model into memory exactly once per container lifecycle, rather than loading it on every single invocation or at the global scope.

**Constraints:**
- Use the `@modal.enter()` lifecycle hook method to initialize and load the model weights.
- Explicitly request an A10G GPU using the `gpu="a10g"` parameter in the `@app.function()` decorator.
- Ensure global imports of heavy ML libraries (like `torch`) are avoided at the top level of the script to optimize parsing time.