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