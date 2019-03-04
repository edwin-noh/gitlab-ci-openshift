oc new-project gitlab
oc adm policy add-scc-to-user anyuid -z gitlab-ce-user -n gitlab
oc adm policy add-scc-to-user privileged -z gitlab-runner-user -n gitlab

# gitlab openshift runner template

https://gitlab.com/gitlab-org/omnibus-gitlab/blob/f04b5c4443b3a98011577cdd7c9de766a287531e/docker/openshift/runner-template.yml

# Setup gitlab runner

oc apply -f https://gitlab.com/gitlab-org/omnibus-gitlab/raw/f04b5c4443b3a98011577cdd7c9de766a287531e/docker/openshift/runner-template.yml
