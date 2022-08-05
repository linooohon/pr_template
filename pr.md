## Types of changes

- [ ] **Bugfix**
- [x] **New feature**
- [ ] **Refactoring**
- [ ] **Breaking change** (any change that would cause existing functionality to not work as expected)
- [ ] **Documentation Update**
- [ ] **Other (please describe)**

## Description
- Complete serverless deployment (dev) when only workflow `check` is successful and is on `main` branch.

## Steps to Test This Pull Request
- Try to merge something into `main` branch, and check for the logs in "Actions".

## Expected behavior
- "check" & "deploy_dev" workflow in  "Actions" section of GitHub work fine.

## Related Issue
- None
## Other:

1. In this PR, I also changed the confusing `.env` naming, here is my thought to separate local and dev clearly:
- when we develop locally which means the stage is `local`:
    
    ```
    - STAGE: local
    - env:  .env.local
    - root: `/`
    ```
- `Stage App` which means the stage is: `development`(sometimes will call it `stage`)

    ```
    - STAGE: development
    - env:  .env
    - root: `/development`
   ```

2. The `deploy_dev` job can only work after merged into `main` only.

3. This PR is a duplicate version of #11 which was merged into `main` but was being reset by git reset, additionally, this PR also adds `python3.9`, `.env`, and `aws-profile` when doing the deployment.
