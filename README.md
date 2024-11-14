# policy-dryrun-demo

This is a repository for demonstrating the ACM policy dryrun tool, currently in Dev Preview in ACM 2.12.

## 01

A basic example using Pods.

Command:
```bash
./policytools dryrun --policy ./01/configpolicy.yaml --status-path ./01/status.yaml ./01/input/ > ./01/output.md
```

Notes:
- The tool can take directories or individual files for the current cluster state.
- The command's `stderr` and exit code indicate when the policy is NonCompliant.
- The output is loosely formatted, for human readability of the diff and compliance event(s).
- The status output (`--status-path`) is optional.

Experiment:
- Try changing the policy to `mustonlyhave`.
- Try "fixing" the cluster state manually.

## 02

An example with `object-templates-raw`.

Command:
```bash
./dryrun --policy ./02/configpolicy.yaml --status-path ./02/status.yaml ./02/input.yaml > ./02/output.md
```

Notes:
- There is a (dryrun only) bug in the released version where it does not always evaluate all of the objects.
- Some lookups won't necessarily work in `object-templates-raw` templates. This example uses a pre-built list instead.

Experiment:
- Try changing more things in each object, to see different diffs.
