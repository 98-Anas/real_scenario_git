# real_scenario_git
---------------------

![image](https://github.com/user-attachments/assets/7c5cd71b-844d-41a7-9ed8-5c13bb419b73)

## Task Steps

### Initialize Repository Locally or Clone it

### Branch Setup
Create two branches from `main`:
```bash
git branch develop
git branch alpha
```

### Part 1: Develop Branch Work

#### Switch to `develop`:
```bash
git checkout develop
```

#### Create and commit files:
```bash
echo "Content for file1" > file1
git add file1
git commit -m "first-commit"

echo "Content for file2" > file2
git add file2
git commit -m "second-commit"
```

#### View history:
```bash
git log --oneline
```

#### Hard reset to first commit:
```bash
git reset --hard HEAD~1
```

#### Recover using reflog:
```bash
git reflog

git reset --hard <second-commit-hash>
```

![step_1](https://github.com/user-attachments/assets/8adda3d7-bcb0-4f26-aa3a-f8d90141ee2a)

![step_2](https://github.com/user-attachments/assets/17b71330-450f-4c84-91b5-daf8c33ffc9e)

---

### Part 2: Alpha Branch Work

#### Commit to `alpha`:
```bash
git checkout alpha
echo "Content for file3" > file3
git add file3
git commit -m "third-commit"
```

#### Commit to `develop`:
```bash
git checkout develop
echo "Content for file4" > file4
git add file4
git commit -m "fourth-commit"
```

#### Visualize divergence:
```bash
git log --oneline --decorate --all --graph
```

![step_3](https://github.com/user-attachments/assets/91e1dbfa-607b-48e8-938c-16a99f2b4642)

---

### Part 3: Rebase Operation

#### Rebase `alpha` onto `develop`:
```bash
git checkout alpha
git rebase develop

```

#### Verify linear history:
```bash
git log --oneline --decorate --all --graph
```

![step_4](https://github.com/user-attachments/assets/4a322b6b-ef90-4164-8294-8fc74c0bd2b8)

---
### Verify on GitHub:
- Check branch dropdown menu
- Inspect commit histories for each branch
---

## Key Concepts Demonstrated
| Concept           | Command/Example                  | Purpose                          |
|-------------------|----------------------------------|----------------------------------|
| Branching         | `git branch`, `git checkout`     | Isolate concurrent workstreams   |
| Reset             | `git reset --hard HEAD~1`        | Discard commits (with caution!)  |
| Reflog            | `git reflog`                     | Recover lost commits             |
| Rebase            | `git rebase develop`             | Linearize history                |
| Remote Sync       | `git push -u origin <branch>`    | Collaborate via GitHub           |

