# Delete Old Branches
This script will delete all merged branches more than on month old except for following branches :
- `master`
- `develop`
- `releases`

## How to use
Just run this bash script **inside** of your repository:
```bash
./delete-old-branches.sh
```

## Automatize
You can automatically trigger this script with any automated pipelines.

### Bitbucket pipelines
To add this script into your Bitbucket pipelines, open/create your bitbucket-pipelines.yml file from the root of your repository and add a custom step :

```yaml
custom: # defines that this can only be triggered manually or by a schedule
    delete-old-branches:
      - step:
          script:
            - chmod +x delete-old-branches.sh # Bitbucket pipelines needs permission to execute this script
            - ./delete-old-branches.sh
```

Then you can create a schedule inside of Bitbucket pipelines for `delete-old-branches`.
