help: ## Show this help
	@grep -E '^[.a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

setup: ## Setup development environment
	git init
	pre-commit install
	poetry install
	pre-commit run --all-files --hook-stage manual
	git add poetry.lock

format: ## Run pre-commit hooks to format code
	pre-commit run --all-files

args ?= -vvv
test: ## Run tests
	pytest $(args)

shell: ## Run poetry shell
	poetry shell
