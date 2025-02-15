# Dockerfile Bug: Missing Application File

This repository demonstrates a common error in Dockerfiles: forgetting to copy the main application file into the image before attempting to run it.

## Bug

The original `Dockerfile` attempts to run `app.py` but fails to copy it into the image.  This leads to a runtime error when Docker tries to execute a non-existent file.

## Solution

The `Dockerfile_fixed` corrects the error by adding a `COPY` instruction to copy `app.py` into the image.

## Steps to Reproduce

1. Clone this repository.
2. Attempt to build the original `Dockerfile` using `docker build -t missing-app .`
3. Observe the build failure.
4. Build the corrected `Dockerfile_fixed` using `docker build -t fixed-app .`
5. Observe that the build succeeds.