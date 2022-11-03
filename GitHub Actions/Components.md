#GitHubActions #devOps 

## Components

### Event
- [ ] Trigger

### Workflow
- [ ] One or more jobs
- [ ] Pipeline
- [ ] .github/workflows

### Job
- [ ] Set of steps that run on the **same runner**
- [ ] jobs can be **squential** or **parallel**
- [ ] by default, jobs have no dependencies

### Steps
- [ ] step is either shell **script** or **actions**
- [ ] steps are executed in **order** and are **dependent** on each other
- [ ] as steps are on same virtual machine, it can share data between steps.

### Action
- [ ] action is a complex but frequently repeated task.
- [ ]  like **functions**. e.g: authentication, git pull, etc
- [ ] `actions/checkout`: git clone

### Runner 
- [ ] erver that runs your workflows
- [ ] a single job at a time
- [ ] GitHub hosted and Self hosted runners

