# Public Sync Dev Template 🔄

This is the `public-sync` template. It's designed to help you work on your code in a `Private` folder and sync non-sensitive files to a `Public` folder.

<details>
<summary>🚀 Quick Start</summary>

1. **Create & Clone**: Use this template to create a new repo and clone it.
2. **Install**: Run `npm install` in your local repo.
3. **Init**: Run `npm run sync` to create `Private` & `Public` folder.
4. **Work**: Add your code to the `Private` folder.
5. **Configure**: Adjust `public-sync` settings in `package.json` if needed.
6. **Sync**: Run `npm run sync` to copy files from `Private` to `Public`.
7. **Commit & Push**: Use `git` commands in your synced directories.

</details>

## How Sync Works ❓

Running `npm run sync` copies all files from `Private` to `Public`, excluding sensitive files. You can specify which files are sensitive in `package.json`. This allows you to share your project without exposing sensitive information. For more details, visit the [public-sync repository](https://github.com/OllyFN/public-sync).

## Git Control 🎛️

After syncing, you can use `git` in the `Public` folder. The `.git` folder is not affected by the sync process, so your version history is preserved.

You can also maintain a separate Git repo in the `Private` folder. The `.git` folder in `Private` is not synced, allowing you to keep some version history private.

## My File Structure 📂

Here's how I set up my folders:

```
.
├── Private
│ ├── .git (private git repo)
│ ├── client
│ │ ├── ... (client-side code)
│ │ └── .env (client-side secrets)
│ └── server
│ ├── ... (server-side code)
│ └── .env (server-side secrets)
└── Public
├── .git (public git repo)
├── client
│ └── ... (client-side code)
└── server
└── ... (server-side code)
```

I keep `.env` files in `Private` for client and server secrets. `Public` gets all the code, but no `.env` files. I set `public-sync` to skip `.env` files.

I use separate `.git` folders in both `Public` and `Private` for independent version control. This lets me share my code publicly, while keeping sensitive data secure and synced. Remember, the `.git` folder can be anywhere. This setup keeps my secrets secret while I share my code.

If you're only dealing with either server or client, you can simplify the structure. Just put your source code directly in the `Private` folder. No need to create a separate `server` or `client` folder.

## FAQ 🤔

### **A lot of information about how to use public-sync is answered in the [public-sync repository](https://github.com/OllyFN/public-sync)**

<details>
<summary>What's the difference between `.gitignore` and `public-sync`?</summary>
`.gitignore` excludes files from Git tracking, while `public-sync` automates the process of copying files from one directory to another, excluding specified files. This is useful when you want to keep sensitive files (like `.env`) in a private GitHub repo, but also share your code publicly. Instead of manually managing two repositories and copying files, `public-sync` does the heavy lifting for you.
</details>

<details>
<summary>Can I use `public-sync` with other programming languages?</summary>
Yes, `public-sync` is language-agnostic. You can use it with any programming language.
</details>

<details>
<summary>How do I specify which files `public-sync` should ignore?</summary>
You can specify the files to ignore in the `package.json` file. In the `public-sync` configuration, add the file names or patterns to the `ignore` array. for more detailed information go to the Regex section of the public-sync repository.
</details>

<details>
<summary>Can I customize the names of the `Private` and `Public` folders?</summary>
Yes, you can customize the folder names. However, you'll need to update the `public-sync` configuration in `package.json` to reflect the new folder names.
</details>

<details>
<summary>Can I use `public-sync` to sync more than two folders?</summary>
`public-sync` is designed to sync files from one source folder to one destination folder. If you need to sync multiple folders, you will need to put all the folders you would want to sync inside the source folder.
</details>

<details>
<summary>What types of files can I exclude from the sync process?</summary>
You can exclude any type of file from the sync process. Commonly excluded files include `.env` files, log files, and other files containing sensitive information.
</details>
