# Review Guidelines

After reviewing individual files, perform a dedicated cross-file analysis pass:
1. For every function signature that changed, verify ALL callers in the diff still pass correct arguments.
2. For every new field/column/key added, verify all readers and writers are consistent.
3. For every error path modified, verify cleanup and rollback are correct across the call chain.
4. Check if any file uses a default value or constant that was changed in another file.
