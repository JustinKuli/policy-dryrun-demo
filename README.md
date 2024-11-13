# policy-dryrun-demo

This is a repository for demonstrating the ACM policy dryrun tool, currently in Dev Preview in ACM 2.12.

## 01

Command:
```bash
./policytools dryrun --policy ./01/configpolicy.yaml --status-path ./01/status.yaml ./01/input/ > 01/output.md
```

Notes:
- The tool can take directories or individual files for the current cluster state.
- The command's `stderr` and exit code indicate when the policy is NonCompliant.
- The output is loosely formatted, for human readability of the diff and compliance event(s).
- The status output (`--status-path`) is optional.

Experiment:
- Try changing the policy to `mustonlyhave`.
- Try "fixing" the cluster state manually.
