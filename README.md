# homebrew-dumpcft

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Homebrew](https://img.shields.io/badge/homebrew-blue.svg)](https://brew.sh)

Homebrew tap for the `dumpcft` application - a tool that dumps the templates of all CloudFormation stacks in one or more AWS regions.

## What is dumpcft?

`dumpcft` is a command-line utility that allows you to extract and save the templates of all CloudFormation stacks across one or more AWS regions. This can be useful for:

- Backup and documentation purposes
- Analyzing your infrastructure as code
- Migrating stacks between accounts
- Auditing CloudFormation templates

## Installation

### Prerequisites

- [Homebrew](https://brew.sh/) installed on your macOS or Linux system

### Install via Homebrew

```bash
# Add the tap
brew tap scottbrown/dumpcft

# Install the application
brew install dumpcft
```

### Supported Platforms

The formula supports the following platforms:

- macOS (Intel/AMD64 and ARM64)
- Linux (Intel/AMD64 and ARM64)

## Usage

Once installed, you can use `dumpcft` from the command line:

```bash
# Display help information
dumpcft --help

# Example: Dump all CloudFormation templates in the us-east-1 region
dumpcft --region us-east-1

# Example: Dump templates from multiple regions
dumpcft --region us-east-1 --region us-west-2
```

For more detailed usage instructions, refer to the [dumpcft GitHub repository](https://github.com/scottbrown/dumpcft).

## AWS Credentials

`dumpcft` requires AWS credentials to access your CloudFormation stacks. You can configure these using:

- AWS CLI configuration (`~/.aws/credentials`)
- Environment variables (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`)
- IAM roles (when running on EC2 or ECS)

Ensure your credentials have permission to describe CloudFormation stacks.

## Versioning

The current version is 1.0.0.

## For Contributors

### Updating the Formula

To update the formula for a new version:

1. Update the `VERSION` constant in `Formula/dumpcft.rb`
2. Generate new binaries and calculate their SHA256 checksums
3. Update the SHA256 values in the formula
4. Commit and push your changes

### Release Process

When releasing a new version:

1. Build the binaries for all supported platforms
2. Create a new GitHub release with tag format `v{VERSION}` (e.g., `v1.0.1`)
3. Upload the binaries with the naming convention `dumpcft_v{VERSION}_{OS}_{ARCH}.tar.gz`
4. Update the formula as described above

### Local Testing

You can test your changes locally:

```bash
# Install from the local formula
brew install --build-from-source ./Formula/dumpcft.rb

# Test the formula
brew test dumpcft
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Links

- [dumpcft GitHub Repository](https://github.com/scottbrown/dumpcft)
- [Report Issues](https://github.com/scottbrown/homebrew-dumpcft/issues)

## Acknowledgments

- Created by [Scott Brown](https://github.com/scottbrown)
