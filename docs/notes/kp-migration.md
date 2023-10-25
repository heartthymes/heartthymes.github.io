
1. Make sure required schemas for tenants are created using Terraform
```
   projects/pp/europe-west1/cloud-sql/postgres-01-01/terragrunt.hcl
```
_if not, apply the changes to the target stage, using github action_
2. Make sure GCP Keypooling is able to connect to CloudSQL
4. Measure estimated downtime based on amount of free keys and QA migration data
5. Make public announcement in advance. (Time TBD! Week?)
6. ----------
7. Switch off Facade endpoint for tenant
	```bash
	kubelogin
	kubectl config use-context XXX
	kubectl edit configmap cdm-facade-endpoints
	```
	Set `keyPool.enabled.{TENANT}: 'false'` and save! (Verify with the team)
8. Adjust Facade to use different URLs for KP 
1. Scale down PENG Keypooling to 0 (TBD. Not needed if we do migration on tenant level)
```bash
kubectl scale --replicas=0 deployment/keypooling 
```
7. Exclude target tenants from the kafka listener list in PENG
8. Include tenants to GCP KP kafka listener list
9. Run migration scripts for tenant
10. Compare the number of free keys inserted to CloudSQL to the PENG one.
11. Reroute the facade endpoint to the GCP Keypooling
12. Scale up GCP Keypooling to the required number
13. Switch on Facade endpoint
14. Verify the test results and datadog logs for the required stage
15. Make an "UP and Runnung" public announcement.
16. Run initial load to migrate used keys for migrated tenant





GCP F --- PENG F <-- API Calls for RU Blocked <- configmap change

API Calls --- Kafka MQ

[x] KP GCP --- [OK] KP PENG <-- Kafka Listener for RU unsubs <-- restart

Run script for RU

KP GCP <--- only RU for kafka listener

Change URL on FACADE <--- configmap change?
UNblock API Calls




