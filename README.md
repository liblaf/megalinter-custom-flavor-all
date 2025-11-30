# MegaLinter Custom Flavor: All

[![Docker Image Size](https://ghcr-badge.egpl.dev/liblaf/megalinter-custom-flavor-all/megalinter-custom-flavor/size)](https://github.com/liblaf/megalinter-custom-flavor-all/pkgs/container/megalinter-custom-flavor-all%2Fmegalinter-custom-flavor)

This custom MegaLinter aims to have an optimized Docker image size.

It is built from official MegaLinter images, but is maintained on https://github.com/liblaf/megalinter-custom-flavor-all by liblaf

## Embedded linters

- [ACTION_ACTIONLINT](https://megalinter.io/latest/descriptors/action_actionlint/)
- [BASH_SHELLCHECK](https://megalinter.io/latest/descriptors/bash_shellcheck/)
- [BASH_SHFMT](https://megalinter.io/latest/descriptors/bash_shfmt/)
- [COPYPASTE_JSCPD](https://megalinter.io/latest/descriptors/copypaste_jscpd/)
- [CPP_CLANG_FORMAT](https://megalinter.io/latest/descriptors/cpp_clang_format/)
- [CPP_CPPCHECK](https://megalinter.io/latest/descriptors/cpp_cppcheck/)
- [CPP_CPPLINT](https://megalinter.io/latest/descriptors/cpp_cpplint/)
- [CREDENTIALS_SECRETLINT](https://megalinter.io/latest/descriptors/credentials_secretlint/)
- [ENV_DOTENV_LINTER](https://megalinter.io/latest/descriptors/env_dotenv_linter/)
- [GO_GOLANGCI_LINT](https://megalinter.io/latest/descriptors/go_golangci_lint/)
- [GO_REVIVE](https://megalinter.io/latest/descriptors/go_revive/)
- [JSON_ESLINT_PLUGIN_JSONC](https://megalinter.io/latest/descriptors/json_eslint_plugin_jsonc/)
- [JSON_NPM_PACKAGE_JSON_LINT](https://megalinter.io/latest/descriptors/json_npm_package_json_lint/)
- [JSON_PRETTIER](https://megalinter.io/latest/descriptors/json_prettier/)
- [JSON_V8R](https://megalinter.io/latest/descriptors/json_v8r/)
- [LATEX_CHKTEX](https://megalinter.io/latest/descriptors/latex_chktex/)
- [MARKDOWN_MARKDOWNLINT](https://megalinter.io/latest/descriptors/markdown_markdownlint/)
- [MARKDOWN_MARKDOWN_LINK_CHECK](https://megalinter.io/latest/descriptors/markdown_markdown_link_check/)
- [MARKDOWN_MARKDOWN_TABLE_FORMATTER](https://megalinter.io/latest/descriptors/markdown_markdown_table_formatter/)
- [MARKDOWN_REMARK_LINT](https://megalinter.io/latest/descriptors/markdown_remark_lint/)
- [PYTHON_RUFF](https://megalinter.io/latest/descriptors/python_ruff/)
- [PYTHON_RUFF_FORMAT](https://megalinter.io/latest/descriptors/python_ruff_format/)
- [REPOSITORY_GIT_DIFF](https://megalinter.io/latest/descriptors/repository_git_diff/)
- [SPELL_CSPELL](https://megalinter.io/latest/descriptors/spell_cspell/)
- [YAML_PRETTIER](https://megalinter.io/latest/descriptors/yaml_prettier/)
- [YAML_V8R](https://megalinter.io/latest/descriptors/yaml_v8r/)
- [YAML_YAMLLINT](https://megalinter.io/latest/descriptors/yaml_yamllint/)

## How to use the custom flavor

Follow [MegaLinter installation guide](https://megalinter.io/latest/install-assisted/), and replace related elements in the workflow.

- GitHub Action: On MegaLinter step in .github/workflows/mega-linter.yml, define `uses: liblaf/megalinter-custom-flavor-all@main`
- Docker image: Replace official MegaLinter image with `ghcr.io/liblaf/megalinter-custom-flavor-all/megalinter-custom-flavor:latest`

## How the flavor is generated and updated

This custom flavor is automatically kept up to date with MegaLinter releases:

1. **Automatic version sync**: The `check-new-megalinter-version` workflow runs daily, checks for new MegaLinter releases, and automatically creates matching releases in this repository.

2. **Automated builds**: Each release triggers the `megalinter-custom-flavor-builder` workflow, which:

   - Builds a Docker image with only the selected linters
   - Publishes to GitHub Container Registry (ghcr.io)
   - Optionally publishes to Docker Hub (if credentials are configured)

3. **Available image tags**:
   - Release tags (e.g., `v9.0.0`): Built from MegaLinter releases
   - `beta` tag: Built from non-main branch pushes for testing
   - `latest` tag: Points to the most recent release

## Configuration requirements

### Required: Personal Access Token

For automatic version checking to work, a `PAT_TOKEN` secret must be configured as a **repository-scoped fine-grained token** with:

- **Repository access**: Only select repositories (select this repository)
- **Repository permissions**:
  - Contents: Read and write
  - Actions: Read and write

See the [Custom Flavors documentation](https://megalinter.io/beta/custom-flavors/) for detailed setup instructions.

### Optional: Docker Hub publishing

To publish to Docker Hub in addition to ghcr.io, configure:

- `DOCKERHUB_REPO` variable (e.g., your Docker Hub username)
- `DOCKERHUB_USERNAME` secret
- `DOCKERHUB_PASSWORD` secret

## How to generate the flavor manually

If you need to manually trigger a build:

1. **Create a GitHub release**: Creates a versioned build matching the tag name (e.g., `v9.0.0`)
2. **Push to any branch** (except main): Builds a `beta` tagged image for testing
3. **Manually run the workflow**: Go to Actions > Build & Push MegaLinter Custom Flavor > Run workflow

See [full Custom Flavors documentation](https://megalinter.io/beta/custom-flavors/).

## How to use the custom flavor

Follow [MegaLinter installation guide](https://megalinter.io/latest/install-assisted/), and replace related elements in the workflow.

- **GitHub Action**: On MegaLinter step in `.github/workflows/mega-linter.yml`, define `uses: liblaf/megalinter-custom-flavor-all@main`
- **Docker image**: Replace official MegaLinter image with `ghcr.io/liblaf/megalinter-custom-flavor-all/megalinter-custom-flavor:latest`

[![MegaLinter is graciously provided by OX Security](https://raw.githubusercontent.com/oxsecurity/megalinter/main/docs/assets/images/ox-banner.png)](https://www.ox.security/?ref=megalinter)
