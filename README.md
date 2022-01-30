# Eureka

A Git-based Collaborative Knowledge Management System powered by Obsidian

## Getting Started

### Duplicate/Fork Eureka

1. Create new git repository to host your eureka repository
2. `git clone --bare git@github.com:TongHuaLabs/eureka.git`
3. `cd eureka.git`
4. `git lfs fetch --all`
5. `git push --mirror https://github.com/exampleuser/new-repository.git`
6. `git lfs push --all https://github.com/exampleuser/new-repository.git`
7. `cd .. && rm -rf eureka.git`

### Clone

1. `git clone https://github.com/exampleuser/new-repository.git`
2. `git remote add template git@github.com:TongHuaLabs/eureka.git`
3. `git submodule init`
4. `git submodule update`— Populate submodule folders

### Updating Eureka

```bash
git pull template main
```

## Eureka Module

- A Eureka Module is a Git Submodule containing Markdown files that support the Obsidian Wikilinks Syntax.
- Use modules instead of normal folders when you need access control to note files.

### Create a new Eureka Module

See <https://github.com/TongHuaLabs/eureka-module>

### Add an existing Eureka Module

The command below creates a new folder in the current folder for storing the eureka module. As a convention, folder name should be in the following format: `<two-digit-number> - <name>` (e.g. `10 - Personal`, `11 - Work`, etc.) — Please note that `00 - 09` and `99` are reserved for built-in modules.

```bash
git submodule add <eureka-module-repository> <folder-name>
```

### Update a Eureka Module

Update all submodules to latest remote head

```bash
git submodule update --remote
```

or

```bash
cd submodule
git checkout main
git pull origin main
```

### Edit an Eureka Module

```bash
cd submodule
git checkout <branch-name>
git add .
git commit -m "message"
git push origin <branch-name>
cd ..
git add .
git commit -m "update submodule"
```

Note: To stage the submodule in Eureka — `git add .`, you must commit the submodule first

## Known Bugs

- <https://github.com/tgrosinger/advanced-tables-obsidian/issues/147>
