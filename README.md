# slides-dl-for-cv-primer

## Prerequisites

You only need to do these once locally. 
* Install [Quarto](https://quarto.org/docs/get-started/)
* Install the [VS Code Quarto extension](https://quarto.org/docs/get-started/hello/vscode.html)

## Build the presentation locally

These slides use include directives to split the content into smaller files.

To render the presentation locally and update any changes live, run the following command from the root folder of the repository:

```sh
quarto preview --to revealjs
```

In subsequent runs, remember to remove the generated `_site` folder.
```
rm -r _site/ && quarto preview --to revealjs
```


## Deploy the presentation on GitHub Pages
For the first deployment:
* Create an empty `gh-pages` branch:
  ```sh
  git checkout --orphan gh-pages
  git reset --hard
  git commit --allow-empty -m "fresh and empty gh-pages branch"
  git push origin gh-pages
  ```
* Review the repository Settings/Pages to ensure that deployment is enabled from the `gh-pages` branch.
* Make the first release on GitHub, tagged with a version number (see below for versioning schemes).

For all subsequent deployments:
* Simply make a new release tagged with the appropriate version number. For presentations, we prefer a date-based versioning scheme, e.g. `YY.MM` or `YY.MM.DD`. You are encouraged to include some additional information on location, event, etc. in the release notes. If the release is a work-in-progress, append `dev` to the version tag (`YY.MM.dev`) and tick the "Set as a pre-release" checkbox.
* GitHub actions will take care of the rest (see example deployment [here](https://neuroinformatics-unit.github.io/quarto-presentation-template/#/title-slide))
* Deployed presentations can be found at `https://{USER}.github.io/{REPOSITORY-NAME}/#/title-slide`. For repositories of the neuroinformatics-unit organisation, this redirects to `https://neuroinformatics.dev/{REPOSITORY-NAME}/#/title-slide`
