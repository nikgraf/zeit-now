# GitHub Action for ZEIT

This Action wraps the [Now CLI](https://github.com/zeit/now-cli) to enable common Now commands.

## Usage

```workflow
workflow "Deploy on Now" {
  on = "push"
  resolves = ["alias"]
}

action "deploy" {
  uses = "actions/zeit-now@master"
  secrets = [
    "NOW_TOKEN",
  ]
}

action "alias" {
  needs = ["deploy"]
  uses = "actions/zeit-now@master"
  args = "alias"
  secrets = [
    "NOW_TOKEN",
  ]
}
```

For more examples, visit: [actions/example-zeit-now](https://github.com/actions/example-zeit-now).

### Secrets

- `NOW_TOKEN` - **Required**. The token to use for authentication with the ZEIT Now API ([more info](https://zeit.co/blog/introducing-api-tokens-management))

## License

The Dockerfile and associated scripts and documentation in this project are released under the [MIT License](LICENSE).

Container images built with this project include third party materials. See [THIRD_PARTY_NOTICE.md](THIRD_PARTY_NOTICE.md) for details.
