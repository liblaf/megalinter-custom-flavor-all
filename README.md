# MegaLinter Custom Flavor: All

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
- [GIT_GIT_DIFF](https://megalinter.io/latest/descriptors/git_git_diff/)
- [JSON_ESLINT_PLUGIN_JSONC](https://megalinter.io/latest/descriptors/json_eslint_plugin_jsonc/)
- [JSON_JSONLINT](https://megalinter.io/latest/descriptors/json_jsonlint/)
- [JSON_NPM_PACKAGE_JSON_LINT](https://megalinter.io/latest/descriptors/json_npm_package_json_lint/)
- [JSON_PRETTIER](https://megalinter.io/latest/descriptors/json_prettier/)
- [JSON_V8R](https://megalinter.io/latest/descriptors/json_v8r/)
- [LATEX_CHKTEX](https://megalinter.io/latest/descriptors/latex_chktex/)
- [LUA_LUACHECK](https://megalinter.io/latest/descriptors/lua_luacheck/)
- [LUA_SELENE](https://megalinter.io/latest/descriptors/lua_selene/)
- [LUA_STYLUA](https://megalinter.io/latest/descriptors/lua_stylua/)
- [MARKDOWN_MARKDOWNLINT](https://megalinter.io/latest/descriptors/markdown_markdownlint/)
- [MARKDOWN_MARKDOWN_LINK_CHECK](https://megalinter.io/latest/descriptors/markdown_markdown_link_check/)
- [MARKDOWN_MARKDOWN_TABLE_FORMATTER](https://megalinter.io/latest/descriptors/markdown_markdown_table_formatter/)
- [MARKDOWN_REMARK_LINT](https://megalinter.io/latest/descriptors/markdown_remark_lint/)
- [PYTHON_PYRIGHT](https://megalinter.io/latest/descriptors/python_pyright/)
- [PYTHON_RUFF](https://megalinter.io/latest/descriptors/python_ruff/)
- [PYTHON_RUFF_FORMAT](https://megalinter.io/latest/descriptors/python_ruff_format/)
- [SPELL_CSPELL](https://megalinter.io/latest/descriptors/spell_cspell/)
- [XML_XMLLINT](https://megalinter.io/latest/descriptors/xml_xmllint/)
- [YAML_PRETTIER](https://megalinter.io/latest/descriptors/yaml_prettier/)
- [YAML_V8R](https://megalinter.io/latest/descriptors/yaml_v8r/)
- [YAML_YAMLLINT](https://megalinter.io/latest/descriptors/yaml_yamllint/)

## How to generate the flavor

Create a GitHub release on your repo, it will generate and publish your custom flavor using the MegaLinter custom Flavor Builder matching the tag name of your release (example: `9.0.0`)

You can also generate a custom flavor using MegaLinter Custom Flavor by pushing on any branch or manually run the workflow `megalinter-custom-flavor-builder.yml`.

See [full Custom Flavors documentation](https://megalinter.io/beta/custom-flavors/).

## How to use the custom flavor

Follow [MegaLinter installation guide](https://megalinter.io/latest/install-assisted/), and replace related elements in the workflow.

- GitHub Action: On MegaLinter step in .github/workflows/mega-linter.yml, define `uses: liblaf/megalinter-custom-flavor-all@main`
- Docker image: Replace official MegaLinter image by `ghcr.io/liblaf/megalinter-custom-flavor-all/megalinter-custom-flavor:latest`

[![MegaLinter is graciously provided by OX Security](https://raw.githubusercontent.com/oxsecurity/megalinter/main/docs/assets/images/ox-banner.png)](https://www.ox.security/?ref=megalinter)
