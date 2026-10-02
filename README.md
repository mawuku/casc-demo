# CloudBees CI CasC bundles (demo)

Push the contents of this folder to the root of your Git repository.

| Folder | Used by | How it is loaded |
|---|---|---|
| `oc-bundle/` | Operations center | CasC Bundle Retriever (Helm `OperationsCenter.CasC.Retriever`, `scmBundlePath: oc-bundle`) |
| `base/` | Parent of every controller bundle | OC bundle location (`bundleStorageService`, Git) |
| `demo-controller/` | `demo-controller` managed controller | OC bundle location, assigned in `oc-bundle/items.yaml` |

Rules:
- Bump `version` in a bundle's `bundle.yaml` on every change.
- Keep the bundles on the repository's default branch (the controller bundle location uses it).
- This repository is public: no passwords, tokens or license data. Secrets are injected as `${variables}` from Kubernetes.
- The OC may also list `oc-bundle` as a controller bundle. That is expected; don't assign it to a controller.
