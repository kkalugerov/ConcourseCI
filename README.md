# ConcourseCI Examples

## For more details check: https://concourse-ci.org/fly.html

### Authenticate against Concourse target
fly --target "target-name" login --concourse-url http://localhost:8080 -u admin -p admin

### Execute task
fly -t "target-name" execute -c "path/dir-to-task"/"task-name.yml" 
fly -t "target-name" execute -c "path/dir-to-task"/"tasl-name".yml

### Create pipeline
fly -t "target-name" set-pipeline -p "pipeline-name" -c "pipeline-config-file"

### Unpause pipeline
fly -t "target-name" unpause-pipeline -p "pipeline-name"

### Passing file with variables during the creation of pipeline
fly -t "target-name" set-pipeline -p "pipeline-name" -c "pipeline-config".yml -l "variable-file-name".yml

### Show existing builds, not more than 10
fly -t bucc builds --count=10

### Watch job from from pipeline in build 1/2/3/...
fly -t "target-name" watch --job "pipeline-name"/"job-name" --build N

### Trigger job from pipeline and watch it
fly -t "target-name" trigger-job -j "pipeline-name"/"job-name" --watch

### Destroy pipeline
fly -t "target-name" destroy-pipeline -p "pipeline-name"

### Create secret in CredHub for pipeline with name "pipeline-name"
credhub set -n /concourse/main/"pipeline-name"/"secret-name" --type value --value test-value