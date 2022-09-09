# actions-auto-approve

Approve Pull Requests automatically in Hamster organisation

## Usage

```yaml
name: Auto approve
on:
  issue_comment:
    types: [created]

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      pull-requests: write
    steps:
      - uses: AwesomeHamster/actions-auto-approve@master
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Options

### `github-token`

The GitHub token to use for the API calls. Default `${{ github.token }}`.

### `pr-number`

The pull request number to approve. Default `${{ github.event.issue.number }}`.

### `trigger`

The trigger string to approve the pull request. Default `approve it`.

### `reaction`

The reaction to add to the comment. Default `hooray` :hooray: .

### `review-message`

The message to add to the review. Default `Auto approved by @${{ github.actor }}`.

## License

The project are released under the [MIT License](LICENSE).
