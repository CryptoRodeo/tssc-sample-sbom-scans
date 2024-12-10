# tssc-sample-sbom-scans

This repository has sample output for the SBOM and ACS scans which are output into the logs of a tssc RHTAP pipeline run (all CIs). This repo contains multiple-sample logs from demos. 

### Extracting from raw logs

RHTAP CI (Jenkins, Github and Gitlab) produce output marked with EYECATCHER_BEGIN and EYECATCHER_END for each type of output (ACS scans and SBOMs).

See  `demo-logs` for a raw log downloaded from a pipeline run.

To extract these, you can use `hack/rhtap-process-logs` for the utility script which extracts the files into `extracted` directry for any log.

To extract a log you can use the `hack/util-eyecatcher` to grab the data from the logs in JSON format. 

SBOMs extracted here can be uploaded into TPA directly. 

```
bash hack/util-eyecatcher demo-logs SBOM         >extracted/sbom.json
bash hack/util-eyecatcher demo-logs ACS_DEPLOY   >extracted/acs-deploy.json
bash hack/util-eyecatcher demo-logs ACS_IMAGE_CHECK  >extracted/acs-image-check.json
bash hack/util-eyecatcher demo-logs ACS_IMAGE_SCAN   >extracted/acs-image-scan.json
```

### Testing TPA

The directory `known-sboms` have a set of extracted SBOMs from various test scenarios. They have been put here to enable testing of TPA. The sbom names should have a pattern like

    `template-name-ciType-ok.sbom` or  `template-name-ciType-fail.sbom` if the SBOM was produces by RHTAP but doesn't seem to work in TPA.
    Examples like `go-tekton-ok.sbom` or `python-tekton-ok.sbom`. If you get duplicates just number them.
    You can manually upload to TPA using the UI. 
