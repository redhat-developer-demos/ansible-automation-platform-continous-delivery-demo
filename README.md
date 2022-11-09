DEVNATION DEMO COMMANDS & Names:
-----------------CI Jenkins---------------
  oc project dev-game-app
1.oc apply -f <buildconfig file name>
2.oc create secret docker-registry my-secret --docker-server=quay.io --docker-username=narathod  --docker-password=123@Nagesh
3.oc secrets link builder my-secret --for=mount
----------------AAP--------------------
4. oc apply -f sa-cluster-role.yaml
5. export SA_SECRET=$(oc get sa containergroup-service-account -o json | jq '.secrets[0].name' | tr -d '"')
oc get secret $(echo ${SA_SECRET}) -o json | jq '.data.token' | xargs | base64 --decode > containergroup-sa.token
oc get secret $SA_SECRET -o json | jq '.data["ca.crt"]' | xargs | base64 --decode > containergroup-ca.crt

------------------Name of componants in AAP---------
-Instance Groups
name: dev-container-group
\\\\\\
dev-game-app

containergroup-service-account
\\\\\\

-Inventories
name: dev-inventory

-host
name: dev-host
{'ansible_host': '127.0.0.1', 'ansible_connection': 'local'}

-project
Dev-Project

-Template
dev-template
