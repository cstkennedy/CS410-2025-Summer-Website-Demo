Title: Phase 3
TOC: yes
Author: Thomas J. Kennedy


# Overview

During Phase 3... you will, in collaboration with your team, set up

  - your team's GitHub Repository through GitHub Classroom
  - Project Build & Configuration Management
  - Third-Party Dependencies
  - Code Testing, Documentation, Analysis, and Linting Tools

During this process... you will construct a set of classes and tests based on
[the Phase 3 Design Discussion](doc:phase3_DesignMeeting). Once everything is
set up... you will begin implementation.


# Initial Tasks

This section (and the subsections therein) describe the initial steps to set up
your team's GitHub repository.


## Create or Join Your Team’s Repository

Your repository for the project will be managed via GitHub classroom.

  1. Navigate to [GitHub Classroom](https://classroom.github.com/a/a2kNhXKU)

     Because this is a team project, you will be asked to select or
     create a team.

  2. Look for your team among those listed.

  3. If it does not exist yet, use the box to create your team. You must
     use the **exact group name as listed in Canvas...**

    > - Tuesday 1 - Java
    > - Tuesday 2 - Java
    > - Tuesday 3 - Java
    > - Tuesday 4 - Java
    > - Tuesday 5 - Python
    > - Tuesday 6 - Python
    > - Tuesday 7 - Rust
    > - Thursday 1 - Java
    > - Thursday 2 - Java
    > - Thursday 3 - Java
    > - Thursday 4 - Python
    > - Thursday 5 - Python
    > - Thursday 6 - Python

  4.  Once your repository has been selected or created you will be
     presented with two links.

    - The first link will take you to that repository.

    - The second link (in the form of a green button) will accept your invitation
      to join that GitHub repository


## Identify Yourself to Git

Each team member **must** follow the procedure outlined in [CS252’s
`git`
lesson](https://www.cs.odu.edu/~zeil/cs252/latest/Public/git/#example3)
to identify yourself so that all commits you make are listed under your
Midas name.

Specifically, use the commands...

``` console
git config user.name "your-real-name"
git config user.email "your-odu.edu-email"
```

\bSidebar

You can, alternatively use the `--global` flag to set the configuration option for all
repositories on your machine.

``` console
git config --global user.name "your-real-name"
git config --global user.email "your-odu.edu-email"
```

\eSidebar

...from within a cloned copy of your team's Semester Project repository.

  - If you work on multiple machines or multiple installations of `git`
    on the same machine, you need to do this on each such instance of
    `git`.

  - If you are using the built-in `git` features of Eclipse, you set
    these values in `Window > Preferences > Version Control > Git >
    Configuration`.

Commits that are made under different email addresses will not be
counted towards your contribution to the team.

> In most cases... this includes commits made from the GitHub website rather
> than via a `git` command issued from a PC.


# Phase 3 - Tasks & Requirements

This section covers the general repository and Semester Project requirements.
Java, Python, and Rust specific requirements are detailed within Java, Python,
and Rust subsections. At a high level... the requirements for Phase 3 are...

  1. Organize your project repository.

  2. Your code must follow an Object-Oriented Design and best practices.

  3. You must employ Test Driven Development.

    You do not need to commit and push after each switch between test
    and production code. You do not need to use tags to document your
    process.

  4. Your code must conform to the guidelines of Clean Coding. In
      particular,

      - use meaningful naming.

      - make sure that all public API elements are documented.

      - The declaration of each public class, data member, or function
        member must be preceded by a JavaDoc, PyDoc, or RustDoc comment (based on language).
        with appropriate explanatory text.

      - Each function body must “do one thing”. Overly long bodies and
        overly elaborate control flow must be refactored.

  5. Automate the build/configuration of the project components.

     This must include all tests (unit, integration, and system).

  6. Completed work must be committed and pushed (and merged) to the `main`
     branch of your team's GitHub repository.


## Requirements - Git Repository

As you add components to the project, check them into the repository
using `git`.

  1. Include the `.gitignore` file(s). **In fact, add this file first\!**. I
     recommend that you [start with the one from one of the example
     repos](https://github.com/cstkennedy/cs330-examples/blob/master/.gitignore)

  2. Populate your team's `README.md` file. *A starting template was added to
     your team's repo when it was created.*

  3. Material placed under version control must include all source code,
     hand-edited data files, etc., as well as build/configuration setting
     files.

  4. Do **not** include binaries produced by compiling your own code, Jars
    or other binaries of 3rd-party libraries you have imported, etc.

  5. Do **not** include IDE Project files (e.g.,  the Eclipse `.project` and
     `.classpath` files or the VSCode `.vscode/` directory).

You may work temporarily in other branches if you so desire, but
committing and pushing to the `main` branch is how you share your code
with your teammates.

  - Good teamsmanship requires that this should be done as early and as
    often as possible, without breaking the code for other teammates. A
    good team member does not wait until just before the end of an
    increment to commit and merge all of their changes.

  - Commits in other branches will not count as contributions until they
    are merged into the main branch.

  - You must always opt to merge branches using the
    fast-forward/merge technique. *Do not `rebase`.*

  - Your repository is supposed to be a permanent record of the work
    performed. `git` does feature a few commands that violate this idea
    by permanently deleting commits (e.g., by permanently deleting
    branches on the remote repository). *Do not do anything that alters
    or removes the record of past commits. Doing so will be be
    considered evidence of academic dishonesty.*


## Requirements - Java

Your code must compile and run with...

```console
./gradlew run
```

Your project will eventually make use of a number of third-party libraries. Add
the dependencies to your Gradle build file. Use `implementation` and
`testImplementation` configurations as appropriate.


| Dependency Type  | Gradle Dependency                | Description                                                                      |
| :--              | --------------                   | --------------------------                                                       |
| `implementation` | org.jsoup:jsoup:1.16.1           | [HTML Parsing](https://jsoup.org/)                                               |
| `implementation` | org.apache.poi:poi:5.2.3+        | [Read/write Microsoft document formats](https://poi.apache.org/)                 |
| `implementation` | org.apache.poi:poi-ooxml:5.2.3+  | [Read & write Excel spreadsheets](https://poi.apache.org/spreadsheet/index.html) |
| `implementation` | com.cedarsoftware:json-io:4.14.0 | [JSON Export/Import](https://github.com/jdereg/json-io)                          |


Your tests must compile and run with...

```console
./gradlew test
```

1.  Organize your project repository.

    - Your project directories must be organized according to the
      Android conventions.

    - All code for this project must reside in the package
      `edu.odu.cs.cs350`. Sub-packages of that are permitted.

    - **Do** include the gradle wrapper `gradlew*` files and the
     associated `gradle/` directory.

    - That includes committing and pushing the Jar file inside the gradle
     wrapper – it’s the one exception to the “Don’t push jar files” rule.


4.  Using `gradle`, automate the build of the project components so far.

    This must include all tests. The build must run all tests
    and (for now) whether those are passed or not, package the non-test
    components of the project as a Jar file.

    Use the *gradle wrapper* so that all team members are using a
    consistent builder.


### Tools & Gradle

During Phase 4... I will have you set up custom Gradle Tasks to handle running various
tools (e.g.,. `spotbugs`, `pmd`). For this phase...

  1. Start playing around with custom Gradle Tasks. You will be able to find example
     projects in the [course example repository](https://github.com/cstkennedy/cs350-examples).

     Your custom Gradle Task setup will be evaluated during Phase 4.

  2. Make sure that `./gradlew run`, `./gradlew jar`, `./gradlew test`,
     `./gradlew javadoc`, `./gradlew pmdMain`  and `./gradlew spotbugsMain` can
     all be run on your project. All commands should show a *successful* build.

  3. You will need to configure settings for each tool.


### Documentation & JavaDoc

You will be able to find example projects in the [course example
repository](https://github.com/cstkennedy/cs350-examples).

All classes and functions must be documented using JavaDoc.


## Requirements - Python

You will need to install
[uv](https://docs.astral.sh/uv/getting-started/installation/). Your code must
run with...

```console
uv run main.py
```

If you have set up your `pyproject.toml` file correctly... all dependencies
will be installed in a virtual environment. Refer to [the CS 350 Example
Repo](https://github.com/cstkennedy/cs350-examples). All Python examples have a
`pyproject.toml` file and can be run with `uv`.

Your project will eventually make use of a number of third-party libraries. Add
the dependencies to your `pyproject.toml` file. Use

```console
uv add ...
```

...and...

```console
uv add --dev ...
```

...as appropriate.

| Dependency Type | `pyproject.toml` Entry | Description                                                | Notes                                            |
| :--             | :---                   | :---                                                       | :--                                              |
|                 |                        | [beautifulsoup4](https://pypi.org/project/beautifulsoup4/) |                                                  |
|                 | `openpyxl>=3.1.5`      | [openpyxl](https://pypi.org/project/openpyxl/)             | openpyxl is one of two backends that Pandas uses |
|                 | `jsonpickle>=4.1.0`    | [jsonpickle](https://pypi.org/project/jsonpickle/)         |                                                  |


Your tests must compile and run with...

```console
uv run pytest -ra -v tests
```

### Tools & taskipy

During Phase 4... I will have you set up
[taskipy](https://github.com/taskipy/taskipy) within `uv` to run
various tools (e.g.,. `isort`, `ruff`). For this phase...

  1. Start playing around with [taskipy](https://github.com/taskipy/taskipy). You will be able to find example
     projects in the [course example repository](https://github.com/cstkennedy/cs350-examples).

     Your custom  [taskipy](https://github.com/taskipy/taskipy) setup will be
     evaluated during Phase 4.

  2. Make sure that `uv run`, `uv run pytest`,
     `uv run pydoc`, `uv run isort` `uv run black`, `uv run ruff`, and `uv run mypy --strict` can
     all be run on your project. 

     **You must add these tools as `dev` dependencies**

  3. While not required... you may want to configure settings for each tool.
     All tools must be configured in `pyproject.toml`.


### Documentation & PyDoc

You will be able to find example projects in the [course example
repository](https://github.com/cstkennedy/cs350-examples).

All classes and functions must be documented using pydoc.

Type hints must be listed for...

  1. Class data members (instance and class members)
 
  2. Constants
 
  3. Function arguments and return types

*Function local variables* do not need to have type hints/annotations.


## Requirements - Rust

Your code must run with...

```console
cargo run
```

Your project will eventually make use of a number of third-party libraries. Add
the dependencies to your `Cargo.toml` file. Use

```console
cargo add ...
```

...and...

```console
cargo add --dev ...
```

...as appropriate.

| Dependency Type | `Cargo.toml` Entry | Description                                                 |
| :--             | :--                | :---                                                        |
|                 |                    | [dom_query](https://crates.io/crates/dom_query)             |
|                 |                    | [rust_xlsxwriter](https://crates.io/crates/rust_xlsxwriter) |
| `dev`           |                    | [calamine](https://crates.io/crates/calamine)               |
|                 |                    | [serde](https://crates.io/crates/serde)                     |
|                 |                    | [serde_json](https://crates.io/crates/serde_json)           |
| `dev`           |                    | [rstest](https://crates.io/crates/rstest)                   |


Your tests must compile and run with...

```console
cargo test
```


### Tools & Cargo Make

During Phase 4... I will have you set up
[cargo-make](https://crates.io/crates/cargo-make/) to handle running various
tools (e.g.,. `cargo fmt`, `cargo check`). For this phase...

  1. Start playing around with cargo-make. You will be able to find example
     projects in the [course example repository](https://github.com/cstkennedy/cs350-examples).

     Your cargo-make setup will be evaluated during Phase 4.

  2. Make sure that `cargo run`, `cargo test`, `cargo doc`, `cargo fmt`, `cargo check`, and
     `cargo clippy` can all be run on your project.

  3. While not required... you may want to configure settings for each tool
     (e.g., `rustfmt.toml`)



### Documentation & Rustdoc

You will be able to find example projects in the [course example repository](https://github.com/cstkennedy/cs350-examples).

All structs and functions must be documented according to [rustdoc conventions
& best practices](https://doc.rust-lang.org/stable/rustdoc/index.html).


# Submission

## Peer Evaluation - Individual

**Each** team member must individually take the
[peer evaluation survey](@peerEvals@/evalSurvey.cgi?survey=350@sem@&amp;asst=phase3)
by the end of the phase.
The purpose of this survey is to help assess
the contribution made by individual team members.


## Team Repository - Group

"Submit" your project for this phase by tagging the version for review as
"phase3".  **This must be a *tag*,** a name attached to a particular snapshot
in the main/origin branch, **not** a new branch.


# Contribution & Evaluation

**Your team's code and tests must compile.** If your teams code (production or
test) fails to compile... your team will receive a zero for Phase 3.


## Team Score

Your team's overall grade is computed as...

\\[ s_{\mbox{team}} = \mbox{infra} * \mbox{effort}_t \\]

The team score $s_{\mbox{team}}$ is the product of the infrastructure score
(the measure of how well the team carried out the _process_ of doing software
development) and the team effort multiplier, which is computed by dividing the
number of stories completed by the number of active participants on the team.

> The assumption is that each active team member will complete, on average, one
> and a half (1.5) stories.

Completed stories will be evaluated based on a review of your team's codebase
by the instructor. The points for each story will be awarded based on its
status...

  1. Interface designed
  2. Tests written
  3. Implementation completed
  4. Integrated

You cannot skip steps (e.g., if you skip from *interface designed* to
*implementation*... you will only receive points for *interface designed*).
Credit for each story will then be scaled by a `correctness` multiplier.

The team effort multiplier can be greater than one, increasing the team score,
or lower than one, decreasing the team score.


## Individual Score

After the team review meeting, the instructor will assign each individual a
separate score $s_{\mbox{indiv}}$ as a combination of their...

  - first meaningful commit to the team GitHub repository (start early)

  - performance during the review team meeting

  - on-time completion of the peer evaluation survey.

A person's overall score is 80% of the team score plus 20% of their individual
score, all multiplied by the individual effort multiplier.

\\[ s_{\mbox{overall}} = \left( 0.8 * s_{\mbox{team}} + 0.2 * s_{\mbox{indiv}} \right) * \mbox{effort}_i \\]

The individual effort multiplier estimates how much effort the student put into
the project compared to the rest of the team.  It is computed from a
combination of...

  - peer evaluations

  - estimated number of work sessions

    Phase 3 is divided into `n`-hour blocks. A work session is defined as any
    such block during which at least one (meaningful) commit was made. *Note
    that while commit count will be recorded... the raw count will not directly
    impact your grade.*

The effort multiplier is computed from the ratio of the actual values for each
member to the expected value, given the team size.

\bExample{Effort Multiplier - Team Sizes}

If a team has

  - 3 active members, each should average $\approx$ 33.3% of the task
    completions.

  - 4 active members, each should average 25% of the task
    completions.

  - 5 active members, each should average 20% of the task
    completions.

  - 6 active members, each should average $\approx$16.6% of the task
    completions.

  - 7 active members, each should average $\approx$14.3% of the task
    completions.

\eExample

This individual effort multiplier can be...

  - greater than one, increasing a student's score

  - less than one, decreasing a student's score

If a student receives a score of zero in the peer evaluations for "quantity of
contribution" from a majority of their teammates responding to the survey, then

\bSidebar

The instructor may discard any peer evaluations that are determined to be
*divorced from reality*

\eSidebar

1. Their $\mbox{effort}_i$ is set to zero, giving them an overall grade of zero for the phase.

2. Such students are not counted as active participants in the project when
   computing the team effort $\mbox{effort}_t$, reducing the expected number of
   story completions for the team and thereby raising $s_{\mbox{team}}$ for
   everyone else.

3. They are also not counted as active participants in the calculations of
   $\mbox{effort}_i$ values for the other team members, thereby increasing the
   expected percentages for each team member.

    (For example, if a team starts as 4 members... if one
    person is marked as inactive, then it's really a 3-person team.)


