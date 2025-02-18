# Unspecified Working Directory in Dockerfile

This example demonstrates a common error in Dockerfiles: not setting a working directory. This can lead to unexpected behavior, especially when copying files and running commands. 

**bug.dockerfile:** The original Dockerfile with the error.
**bugSolution.dockerfile:** The corrected Dockerfile with the working directory set.

The bug is that the Dockerfile does not set a working directory. The COPY and CMD instructions are executed in the root directory. If the files to be copied are not in that directory then they may not be available to be copied. 

The solution is to add a `WORKDIR` instruction to the Dockerfile to set the working directory to a specific directory.  This ensures that all subsequent instructions will operate within that directory. 