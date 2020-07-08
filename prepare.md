# Este laboratorio se despliega en RHPDS Workshop 4.3.

**username:** opentlc-mgr

**password:** r3dh4t1!

## Para desplegar ociproject:


```bash
oc adm policy add-scc-to-group anyuid system:authenticated

oc new-project occli

oc new-app quay.io/jasonredhat/openshift-wetty-client

oc create route edge --service=openshift-wetty-client --port=8888

for i in {1..60}; do oc adm policy add-role-to-user view user$i -n occli --as=system:admin; done

Para la app de ejemplo:
oc create -f https://raw.githubusercontent.com/rmkraus/ocp4-workshop/master/hello_world_template.json -n openshift
`
