# passion-ssh

A Zsh function to interactively SSH into AWS ECS services across different environments (production, staging, development) and run commands inside containers.

## Prerequisites

- **Zsh** (the script uses Zsh-specific array and parameter expansion)
- **AWS CLI** (configured with appropriate credentials and permissions)
- **jq** (for JSON parsing)
- **awk** and **sed** (for text processing)
- **tput** (for terminal formatting)
- **ecs-session** (must be installed and available in your `$PATH`)

The Dependency Installation Guide is available in the [Homebrew formula repository](https://github.com/independenc3/homebrew-passion?tab=readme-ov-file#dependency-installation-guide).

## Installation

### Using Homebrew

- Follow the Installation guide from the [Homebrew formula repository](https://github.com/independenc3/homebrew-passion?tab=readme-ov-file#installation).

### Manual Installation 

1. Copy the `passion-ssh` file to a location of your choice.
2. Source it in your `.zshrc` or current shell session:

   ```sh
   source /path/to/passion-ssh
   ```

3. Ensure all prerequisites are installed and available in your `$PATH`.

## Usage

Simply run:

```sh
passion-ssh
```

Follow the interactive prompts to:

1. Select the environment (`production`, `staging`, or `development`).
2. Select the ECS service (filtered to exclude certain services).
3. Enter the command to run inside the container (press Enter for `/bin/sh`, or type `exit` to quit).

## Customization

- To exclude additional services from the menu, edit the `exclude_services` array in the script.
- To change default regions, modify the `case` statement for `region` assignment.

## Example Session

```
$ passion-ssh

Select an environment:
1. production
2. staging
3. development
0. Exit
# (choose environment)

Select a service:
1. my-service
2. another-service
0. Exit
# (choose service)

Enter a command to run on the selected environment and service (default: /bin/sh, type 'exit' to exit):
# (enter command or press Enter)
```
