oc new-project gitlab
oc adm policy add-scc-to-user anyuid -z gitlab-ce-user -n gitlab
oc adm policy add-scc-to-user privileged -z gitlab-runner-user -n gitlab

# gitlab installation (Optional)
oc apply -f https://gitlab.com/gitlab-org/omnibus-gitlab/raw/f04b5c4443b3a98011577cdd7c9de766a287531e/docker/openshift-template.json

# gitlab openshift runner template

https://gitlab.com/gitlab-org/omnibus-gitlab/blob/f04b5c4443b3a98011577cdd7c9de766a287531e/docker/openshift/runner-template.yml

# Setup gitlab runner

oc apply -f https://raw.githubusercontent.com/edwin-noh/gitlab-ci-openshift/master/runner-template.yml
