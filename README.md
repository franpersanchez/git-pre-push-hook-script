# Git Hook: Pre-Push Script 🚀

This shell script is a **pre-push Git hook** designed to ensure that your tests pass and your server runs correctly before pushing changes to remote. If any of these tasks fail, the push is aborted, preventing problematic changes from being pushed to the repository.

## What Does This Script Do? 🤔

1. **Run Tests**: Executes the tests defined in your project before pushing.
2. **Check Test Results**: If tests fail, the push is aborted.
3. **Run Server**: Starts the server for a limited time (10 seconds by default) after tests.
4. **Check Server Status**: If the server fails to start correctly or exceeds the time limit, the push is aborted.

## Customization 🔧

You can easily customize the script by modifying the commands for running tests and starting the server. These commands are defined in the script’s variables, making it adaptable to any project setup.

### Variables to Customize

- **`TEST_COMMAND`**: The command to run your tests.
- **`START_COMMAND`**: The command to start your app/server.

You can modify these variables to suit your project's needs.

## Installation 📦
Place this script in your project directory under **.git/hooks/pre-push**.

Make sure the script is executable by running:

```bash
chmod +x .git/hooks/pre-push
```

## Customization Notes ✍️
- If your project uses different commands for tests or starting the server, simply modify the TEST_COMMAND and START_COMMAND variables at the top of the script to match your setup.
- This script is tailored for projects using npm for testing and server start commands. If you use a different package manager or framework, you can easily adjust the commands to fit your environment.
- The script assumes a 10-second timeout for starting the server. If your server requires more time to start, simply adjust the timeout parameter.