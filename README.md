# Commit-Generator

# Introduction
Welcome to the Commit-Generator, a tool designed to streamline the process of creating conventional commits using ChatGPT. Writing clear and descriptive commit messages is crucial for effective collaboration and project management. This tool leverages the capabilities of ChatGPT to assist developers in generating standardized commit messages effortlessly.

# Usage
To use the Commit-Generator effectively, follow these simple steps:

1. **Configure Git Alias:** Before utilizing the Commit-Generator, set up the following Git alias:

```
# Linux or MAC
git config --global alias.save '!f() { git add . && git commit -m "$*"; }; f'

# Windows
git config --global alias.save "!f() { git add . && git commit -m \"$*\"; }; f"
```

> [!TIP]
> This alias simplifies the commit process, allowing you to directly commit changes with a message.

If you want to check all yout git alias, run the following command:

```
git config --get-regexp alias
```

2. **Prompt:** When you're ready to commit your changes, use the next prompt for the Commit-Generator. Provide your commit message in a "raw" format, either in English or Spanish.

``` 
I need you to help me write conventional commits, you must act like a senior developer, i will give you an example of a conventional commit:

"fix (navbar): change responsiveness width in desktop and mobile version

	Adjust width in the 4 pages from program section in mobile version."

I'll tell you about the base structure, the prefix, which in the example is "fix" is to indicate what type of commit it is, among some prefixes we can find:

- feat: when new functionality is added.
- fix: when a bug is fixed.
- chore: Routine tasks that are not specific to a feature or a bug, such as adding content to the .gitignore file or installing a dependency.
- test: if we add or fix tests.
- docs: when only documentation is modified.
- build: when the change affects the compilation of the project.
- ci: The change affects configuration files and scripts related to continuous integration.
- style: readability or code formatting changes that do not affect functionality.
- refactor: A code change that does not fix bugs or add functionality, but improves the code.
- perf: used for performance improvements.
- revert: if the commit reverts to a previous commit. The hash of the commit being reverted should be indicated.

These are some of the prefixes that exist, there are more and you must have enough criteria to identify what type it is.

Now, how is it that I will provide you with the input, I will give you the message in a "raw" way and you must reformulate and correctly write the conventional commit, an example of what my input would be like (I can give it to you in English or Spanish, If I give you the input in Spanish, you must convert it to English:

"(dashboard) I modified the general sales and expense graphs, I did this in the general dashboard implementing the logic of showing the graphs after rendering"

The final output you must add "git save", this is because I am using an alias that does git add . and git commit in this alias, which makes the process of making a commit more efficient, the example would be something like what you see below

git save "feat (dashboard): modify general sales and expense graphs

    - Implemented logic to display the graphs after rendering in the general dashboard.
    - Modified general sales and expense graphs for better data visualization."

You can notice that here the list is not always going to be listed, it will only be listed if several things have been done in the commit, like in this example, otherwise you don't need to list it and you can do it with in the first example

Finally, to be clear, let's make an analogy as if it were an email:

- The prefix indicates what type of commit it is.
- What goes in parentheses is the scope, where it occurred.
- The subject should be brief, not long, it is like the subject you put when sending an email, brief, assertive and concise, here the verb is in the present simple.
- The description is the why and how, considering the verb in the past tense. Here you can consider what I told you, a single-line description or a list type, depending on the case.

The output you should give me should be in bash type, so I can copy and paste, literally something like the first or second example. Consider including the quotes at the start and in the end as seen in the examples.

git save "feat (dashboard): modify general sales and expense graphs

    - Implemented logic to display the graphs after rendering in the general dashboard.
    - Modified general sales and expense graphs for better data visualization."

Do not rewrite anything, you just have to give me the committee concatenated with the alias at the beginning as in the previous example, you have to do it by writing everything in bash, so that I can only copy and paste in my terminal and be able to execute it with a simple enter, no You separate it, write everything inside bash. Don't forget the quotes at the beginning and end of the commit, before the prefix and at the end of the full stop.
```

# Expected output

```
git save "feat (dashboard): modify general sales and expense graphs

    - Implemented logic to display the graphs after rendering in the general dashboard.
    - Modified general sales and expense graphs for better data visualization."
```

> [!WARNING]
> This output that ChatGPT should give you is ready for copy and paste only, clearly you should have configured your "save" alias in git for it to work correctly.

# Conclusion
With the Commit-Generator, writing clear and consistent commit messages becomes a seamless part of your development workflow. By leveraging the power of ChatGPT, developers can ensure that their commits adhere to established conventions, promoting better communication and collaboration within their teams.
