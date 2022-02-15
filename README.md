# Backup Repository Action

_Description_: Action to perform a backup 
of any existing GitHub Action,
creating a new repository for internal usage.
This is in order for preventing that an action
outside from current organization could be
erased or be out of reach for any reason.

After checking that source respository exists
it will perform a backup based on SHA reference,
a copy of existing README or add a new one in case
where source repository doesn't have any README,
asign selected topics and finally
create a new repository defined in
target repository input with a branch named after
SHA reference.

In case where user tries to make a backup of an already
existing SHA reference in the same repository
it will result in a failed execution.
If is mandatory to replicate any SHA reference it can be
stored in a new backup repository with target repository 
input modificaction.

Actions can be retrieved, searched and viewed
from official 
[GitHub Official Marketplace](https://github.com/marketplace?type=actions)
and then, from direct link to its GitHub repository web,
we can obtain URL and SHA reference,
which it can be obtained from commit field on
top right right corner of files viewer.

## Table of content

* [Inputs](#inputs)
* [Usage](#usage)
* [Credits and references](#credits-and-references)

## Inputs

| Input                    | Required  | Default  | Description                                                                                                             |
|--------------------------|-----------|----------|-------------------------------------------------------------------------------------------------------------------------|
| `token`                  | **true**  |          | Personal access token used to manage this action.                                                                       |
| `source-repository`      | **true**  |          | Repository from where action will be retrieved to perform a backup.                                                     |
| `ref`                    | **true**  |          | Target commit SHA from action exact reference.                                                                          |
| `target-repository-name` | **true**  |          | New repository for upload copied source repository.                                                                     |
| `topics`                 | **false** | `backup` | Topics for repository management.                                                                                         |

## Usage

Action has to be used in this way.

```yaml
   backup-repository:
     name: Backup Repository
     runs-on: ubuntu-latest
     steps:
       - name: Backup Repository
         uses: santander-group/workflow-dispatch-action@main
         with:
           token: <token>
           source-repository: <source-repository>
           ref: <ref>
           target-repository-name: <target-repository-name>
           topics: <topics>
```          

## Credits and references

[ivanamat](https://github.com/ivanamat)\
[DanielSD89](https://github.com/DanielSD89)
