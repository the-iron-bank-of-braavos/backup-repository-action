# Backup Repository Action

Description: Action to perform a backup of any existing GitHub repository, creating a new repository for internal usage. In order to prevent that the action outside of the current organization could be erased or be out of reach for any reason.

After checking that the source repository exists it will perform a backup based on SHA reference, a copy of existing README, or add a new one in case of the repository hasn't any README, assign selected topics, and finally create a new repository defined in target repository input with a branch named after SHA reference.

In case of the user tries to make a backup of an already existing SHA reference in the same repository it will result in a failed execution.

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
