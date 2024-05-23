# Installation and Setup
## Installation
Follow official guide [here.](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
## Setup
User configuration:

> **Note:** This is a note

```

This is code

```

`This is highlighted`

```mermaid
sequenceDiagram
Rod -> Kasia: Hello
Rod --> Adam: Halo!
Adam -->> Rod: Selamat pagi, papa!
Rod -x Adam: Selamat pagi, sayang!
Adam --x Kasia: Dzien dobry, mamo!
```
```mermaid
gitGraph
commit
commit
branch dev
checkout dev
commit
commit
branch feat/feature-1
checkout feat/feature-1
commit
commit
checkout dev
merge feat/feature-1
checkout main
commit
checkout dev
commit
```

```mermaid
graph LR
A[Untracked] --git add . ---> B[Staged] --git commit ---> C[Committed]

```
