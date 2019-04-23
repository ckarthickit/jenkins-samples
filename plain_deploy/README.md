# Repository that maintains the thrid-party libraries to be deployed to a maven repository

## Setting up a new Third Party Folder

- Create a sub-folder under `artifacts` folder with appropriate name (corresponding to the specific third-party library).
- Create an `artifact.gradle` that does the following
  - Initializes `project.ext.artifactsToPublish` with full paths of appropriate artifacts that needs to be published.
  - Create / Modify `artifact.properties` file specifying `artifactGroup`, `artifactName`, `artifactVersion`.
  - Create a task `composeArtifacts` inside `artifact.gradle` that takes care of creating the artifacts in the relative file paths specified in `project.ext.artifactsToPublish`
