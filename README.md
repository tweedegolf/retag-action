# Retag action

Add a tag to a docker image

## Usage

```
# ...
jobs:

  # ...

  docker:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    steps:
      # ...
      - name: Retag the docker image
        uses: tweedegolf/retag-action@main
        with:
          image: ${{ github.repository }}
          tag: ${{ env.tag }}
          new-tag: ${{ input.env }}-${{ env.tag }}
          token: ${{ secrets.GITHUB_TOKEN }}

      # ...

  # ...
```
