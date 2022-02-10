# Backup Repository Action

_Description_: Action which use consists in 
making a copy of any existing GitHub Action 
and create a new repository for its internal usage

## Table of content

* [Inputs](#inputs)
* [Usage](#usage)
* [Credits and references](#credits-and-references)

## Inputs

| Input                    | Required  | Default  | Description                                                                                                             |
|--------------------------|-----------|----------|-------------------------------------------------------------------------------------------------------------------------|
| `token`                  | **true**  |          | Personal access token used to fetch the repository. This field is optional, required if app credentials are not defined.|
| `source-repository`      | **true**  |          | Repository from where action will be retrieved to perform a copy.                                                       |
| `target-repository-name` | **true**  |          | New repository for upload copied source repository.                                                                     |
| `topics`                 | **false** | `backup` | Tags for repository management.                                                                                         |

## Usage

This action has to be used in this way.

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
           target-repository-name: <target-repository-name>
           topics: <topics>
```          

## Credits and references

[ivanamat](https://github.com/ivanamat)\
[DanielSD89](https://github.com/DanielSD89)
