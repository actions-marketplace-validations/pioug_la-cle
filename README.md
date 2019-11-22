> Setup GitHub credentials to install private dependencies

### Input parameters

- `GH_SSH_KEY`: Private SSH key. Use [encrypted secrets](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets) to store such information.

### Example of workflow

```yml
on: push
name: Deploy something
jobs:
  build:
    name: Run scripts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: pioug/add-ssh-key@v1.0.0
        with:
          GH_SSH_KEY: ${{ secrets.GH_SSH_KEY }}
      - run: npm ci
```
