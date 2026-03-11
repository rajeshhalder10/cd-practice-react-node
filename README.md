# CI/CD Practice – React & Node

This repository is created to practice a basic **CI/CD workflow** using Git branching strategies.

The goal is to simulate a real development environment where code moves through different stages before reaching production.

---

## Branching Strategy

This project uses a simple branch structure:

```
main      → Production
develop   → Staging
feature/* → Development features
```

### Meaning of Each Branch

**main**

* Represents the production environment.
* Only stable and tested code should be merged here.

**develop**

* Represents the staging environment.
* Features are merged here first for testing.

**feature/***

* Used by developers to build new features.
* These branches are created from `develop`.

---

## Development Workflow

### 1. Create a Feature Branch

Developers create a new branch from `develop`.

```
git checkout develop
git pull
git checkout -b feature/login
```

---

### 2. Make Changes and Commit

```
git add .
git commit -m "Add login feature"
```

---

### 3. Push Feature Branch

```
git push origin feature/login
```

---

### 4. Merge Feature into Staging

Create a Pull Request:

```
feature/login → develop
```

After review, merge it.

This simulates **deploying to the staging environment**.

---

### 5. Promote Code to Production

Once testing on staging is successful, create a Pull Request:

```
develop → main
```

After merging, the code is considered **ready for production**.

---

## Example Workflow Diagram

```
feature/login
      ↓
Pull Request
      ↓
develop (staging)
      ↓
Testing
      ↓
Pull Request
      ↓
main (production)
```

---

## Purpose of This Repository

This repository is used to practice:

* Git branching strategies
* Pull request workflows
* CI/CD pipelines
* Staging to production deployment flow
