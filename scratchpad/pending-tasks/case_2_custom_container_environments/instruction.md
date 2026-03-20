A data scientist is building an audio processing pipeline that requires specific OS-level and Python libraries. 

You need to define a custom `modal.Image` in Python that installs the `ffmpeg` system package and the `librosa` Python package. Attach this custom image to a Modal remote function `get_audio_duration` that imports `librosa` and returns a dummy duration integer.

**Constraints:**
- Construct the image using Modal's chaining syntax: `.apt_install("ffmpeg")` and `.pip_install("librosa")`.
- Pass the custom image object to the `image` argument of the `@app.function()` decorator.
- Do NOT install `librosa` globally on your local machine; it must only be imported and utilized within the remote container environment.