# ConcourseCI Examples

## For more details check: https://concourse-ci.org/fly.html

### Authenticate against Concourse target
fly --target test login --concourse-url http://localhost:8080 -u admin -p admin

### Execute task
fly -t test execute -c "path-to-task"/"task-name.yml" 
fly -t test execute -c tasks/task_ubuntu_uname.yml

### Create pipeline
fly -t tutorial set-pipeline -p "pipeline-name" -c "pipeline-config-file"

### Unpause pipeline
fly -t test unpause-pipeline -p "pipeline-name"

