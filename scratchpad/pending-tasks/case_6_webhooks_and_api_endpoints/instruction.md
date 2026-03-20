A frontend application requires a backend REST API to submit images and receive classification results. 

You need to write a FastAPI application with a POST endpoint `/classify` that accepts an image payload and returns a JSON classification response. Expose this FastAPI router as a scalable, serverless Modal web endpoint.

**Constraints:**
- Wrap the FastAPI application instance using Modal's `@app.asgi_app()` decorator.
- Ensure the function is deployed as a secure HTTP endpoint rather than a standard remote function.
- Do NOT use standard local server runners like `uvicorn.run()` within the Modal script to start the API.