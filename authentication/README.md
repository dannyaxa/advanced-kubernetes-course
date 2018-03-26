# kube authentication resources

on cloud9
make virtualenv

virtualenv --version 
which python 
unalias python 
python --version
python3 --version 
which python36
cd ~/environment/ 
virtualenv -p /usr/bin/python36 vpy36 
source vpy36/bin/activate 
python --version 

cd advanced-kubernetes-course/kubernetes-auth-server/

pip install -r requirements-cli.txt


alias kubectl="kubectl --token=\$(AUTH0_CLIENT_ID=xxxxxxxxxxxxxxxx AUTH0_DOMAIN=kube-academy.auth0.com APP_HOST=authserver.kubernetes.kube-academy.net python /home/ec2-user/environment/advanced-kubernetes-course/kubernetes-auth-server/cli-auth.py)"

and virtualenvwraper

$ pip install virtualenvwrapper
...
$ export WORKON_HOME=~/Envs
$ mkdir -p $WORKON_HOME
$ source /usr/local/bin/virtualenvwrapper.sh
$ mkvirtualenv env1


Add oidc setup to kops cluster:
kops update cluster

```
spec:
  kubeAPIServer:
    oidcIssuerURL: https://kube-academy.auth0.com/
    oidcClientID: xxxxxxxxxxxxxx
    oidcUsernameClaim: sub
```

Create UI:

```
kubectl create -f https://raw.githubusercontent.com/kubernetes/kops/master/addons/kubernetes-dashboard/v1.6.3.yaml
```

