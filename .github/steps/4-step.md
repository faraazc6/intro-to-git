## Step 4: Comparing Changes

Now that we understand how to "undo", let's make some real game changes and learn how Git can show us what was changed **before** we commit it to the repository history.

Understanding file differences is crucial for reviewing your work and catching errors!

### 📖 Theory: Understanding Git Diffs

Git uses symbols and coloring to show file changes:

- `+` in green indicates lines that were added
- `-` in red indicates lines that were removed

Example:

```diff
+ This is a line that was added
- This is a line that was removed
```

> [!TIP]
> You can change Git's default comparison colors with the below commands:
>
> ```bash
> git config --global color.diff.old yellow
> git config --global color.diff.new blue
> ```

### Git Diff Commands

The `git diff` command shows differences between development states.

- `git diff` - Shows differences between the working directory and the staging area.
- `git diff --staged` - Shows differences between the staging area and the previous commit.
- `git diff HEAD~1` - Shows differences between the current commit and the previous commit.

### ⌨️ Activity 1: View differences (using the CLI)

Let's make some changes to the game, then use the CLI to show the differences.

1. Open `src/index.html`.

1. On `line 20`, replace the `info-section` area about scoring with the below example:

   ```txt
   <div class="info-section">
      <h3>Current Score</h3>
      <div class="score" id="score">0</div>
      <h3>High Score</h3>
      <div class="high-score" id="high-score">0</div>
   </div>
   ```

   This will demonstrate 3 kinds of changes:

   - Modify the `Score` label to `Current Score`
   - Add the `High Score` information.
   - Remove the `status` information.

1. View the difference between your working directory and the last commit.

   ```bash
   git diff src/index.html
   ```

   <img width="500px" src="https://github.com/user-attachments/assets/f41d6917-1651-4549-bb7b-5441a1832e38"/>

1. Add the changes to the staging area.

   ```bash
   git add src/index.html
   ```

1. Run the same comparison again. Notice that no changes are displayed, because the working directory now matches the staging area.

   ```bash
   git diff src/index.html
   ```

1. View the differences between the staging area and the last commit.

   ```bash
   git diff --staged src/index.html
   ```

   <img width="500px" src="https://github.com/user-attachments/assets/f6aad38c-56fa-49ed-8209-9fe249c209ff"/>

1. Commit the changes with the following message:

   ```md
   git commit -m "Add element for showing high score"
   ```

   <img width="500px" src="https://github.com/user-attachments/assets/8381b943-ca22-4b22-97b5-4520e174fc4c"/>

### ⌨️ Activity 2: View differences (using VS Code)

Let's make some more changes to the game, then use the VS Code to show the differences.

1. Open `src/patterns.js`.

1. On `line 3`, replace the `Null Pointer` area with the below example to change the pattern:

   ```txt
   {
     name: "Null Pointer",
     pattern: [
       [0, 1, 1, 1, 0],
       [0, 1, 0, 1, 0],
       [0, 1, 1, 1, 0],
       [0, 0, 1, 0, 0],
       [0, 0, 1, 0, 0],
     ],
   },
   ```

1. In the **File Explorer**, notice that the file name `patterns.js` has changed color and now has an `M`, indicating that it has been modified.

   <img width="350px" src="https://github.com/user-attachments/assets/93a8f34c-9b16-4783-bc46-81532cdeffdf"/>

1. Open the **Source Control** tab. In the **Changes** list, click `patterns.js` to open the diff (comparison) view.

   <img width="350px" src="https://github.com/user-attachments/assets/4dce9e42-caca-4c6e-a6fe-8d83d58cd06d"/><br/>

   <img width="500px" src="https://github.com/user-attachments/assets/4c410689-2a53-462f-9200-79d21bddbf2c"/>

   > 💡 **Tip**: You can modify the content in the comparison view for live feedback!

1. Add the file to the **staging** area. ⚠️ Don't commit yet!

   Notice the comparison view stopped showing changes since the current file matches the staging area.

   <img width="500px" src="https://github.com/user-attachments/assets/b1274ece-2b03-42d2-88e8-9f3aaaa8f2c5"/>

1. In the **Staged Changes** list, click `patterns.js` to open the diff (comparison) view.

   Notice that you can't make changes here. The staging area is locked in preparation for committing.

   <img width="350px" src="https://github.com/user-attachments/assets/da306727-49f1-4f73-9f38-3a0e5d406cef"/><br/>

   <img width="500px" src="https://github.com/user-attachments/assets/de1448eb-d0dd-4ec5-89a2-74fb4aa1cf5f"/>

1. Commit the change with the following message:

   ```txt
   Make null pointer pattern easier to complete
   ```

1. With your new commits added to the repository, Mona should already be busy checking your work. Give her a moment and keep watch in the comments. You will see her respond with progress info and the next steps.

<details>
<summary>Having trouble? 🤷</summary><br/>

- If the list of change is longer than one screen, you can press `q` to exit the scrolling file viewer.

</details>
