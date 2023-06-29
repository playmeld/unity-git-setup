### 1. Configure Unity for Version Control\*\*

1. Open the editor settings window.

- `Edit > Project Settings > Editor`

2. Make .meta files visible to avoid broken object references.

- `Version Control / Mode: “Visible Meta Files”`

3. Use plain text serialization to avoid unresolvable merge conflicts.

- `Asset Serialization / Mode: “Force Text”`

4. Save your changes.

- `File > Save Project`

### 2. Copy `.gitignore` from this repo into your repo

`.gitignore` combines the following templates

- Unity `.gitignore`: https://github.com/github/gitignore/blob/master/Unity.gitignore
- VS Code `.gitignore`: https://github.com/github/gitignore/blob/main/Global/VisualStudioCode.gitignore
- MacOS `.gitignore`: https://github.com/github/gitignore/blob/master/Global/macOS.gitignore
- Windows `.gitignore`: https://github.com/github/gitignore/blob/master/Global/Windows.gitignore

### 3. Configure Git to use [Unity Smart Merge](https://docs.unity3d.com/Manual/SmartMerge.html)

1. Copy `.gitconfig` from this repo. It's content is the following

```
[merge]
tool = unityyamlmerge

[mergetool "unityyamlmerge"]
trustExitCode = false
cmd = '/Applications/Unity/Hub/Editor/2022.3.4f1/Unity.app/Contents/Tools/UnityYAMLMerge' merge -p "$BASE" "$REMOTE" "$LOCAL" "$MERGED"
```

2. Make sure to update the path to UnityYAMLMerge

### 4. Setup [Git LFS](https://git-lfs.com/)

Git LFS uses `.gitattributes` to track large files with git.

Instructions to install and use are [here](<(https://git-lfs.com/)>).

Copy `.gitattributes` file to your repository.

### 5. Setup pre-commit hook

Copy `pre-commit` file into `.git/hooks` foler
This hook prevents large text files from being added to commit - https://stackoverflow.com/questions/53690327/prevent-large-text-file-from-being-added-to-commit-when-using-github/53692461#53692461

### Based on

- https://gist.github.com/j-mai/4389f587a079cb9f9f07602e4444a6ed
- https://gist.github.com/bitinn/4a82d7dbdaff62163031d318c57cd62d
- https://gist.github.com/nemotoo/b8a1c3a0f1225bb9231979f389fd4f3f
