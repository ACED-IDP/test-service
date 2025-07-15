# About

Brain dump for tests you already run, manually, triggered locally, etc. This will be our launching pad for formalizing our tests in a more unified way...

Suggestions on info to include...
- Type of test (unit, integration, e2e)
- Description
- Link to it 
- List of tests
- Future work / ideal state

See the **UI/UX** header for an example.

# UI/UX
## Release Testing
**Type:** mostly manual e2e tests

**Links:**
- [Internal Release Coordination Notes](https://wiki.ohsu.edu/display/KEDTW/CALYPR+Internal+Release+Coordination+Notes)
- [initial work for e2e load testing](https://github.com/ohsu-comp-bio/load-testing)

**Description:** A lot of manual e2e testing done for release, ie new features that are being released. No existing testing that existing features haven't broken, ie formatting has been changed, etc. Also heavily coupled with the data that exists on the site (eg SMMART views for specific data). Would be hard to automate some of this, particularly because we have made project-specific views that don't generalize without upload very specific project metadata / data. Also likely requires some sort of service account for login, as everything is gated by login.

**Testing Examples:**
- Test that subject-level pie charts populate in the subject viewer
- Ensure that specimen viewer populates as expected with the right specimen tree.
- Check all links still route to the correct place
- Response based on facet subsetting
- Validate patient-specimen specimen counts
- Able to upload to ETL and see results populate on Explorer

# Data Ingest
## Git DRS
**Type:** manual CLI tests

**Links:**
- [Git DRS](https://github.com/bmeg/git-drs)

**Description:** Manual testing done to check pull/push git workflow. Even more usability errors that aren't tested based on (eg when I git push with an expired token it fails).

**Testing Examples:**
- LFS: `git push` workflow for a...
  -  file that already exists (copy of a file)
  -  new file / edited file
  -  (to focus on git DRS over testing vanilla git / git LFS, ensure pre-commit can properly store indexd objects)
- Git push of a regular file
- `git lfs pull -I /path/to/file` where path is...
  - wildcard or directory (multiple files)
  - single file path
  - (here, making sure the transfer client is properly invoked and can generate and download from a signed url)
- ensuring `git drs init` generates an gen3 auth token and initializes directories as expected