# kubernetes takehome assignment

# step 1 
creating mongo-secret.yaml file in which our encoded username and password will be present, for authorization.
<img width="960" alt="1" src="https://github.com/user-attachments/assets/886fcccb-c459-4cb6-88c6-f3c940709713" />

we can see that our secrets are stored.
<img width="960" alt="2" src="https://github.com/user-attachments/assets/6de4f213-ba0b-4564-ad03-d8808c2ca846" />

# step 2
creating mongo-deployment.yaml file
<img width="960" alt="3" src="https://github.com/user-attachments/assets/b624eaef-d629-4677-83cb-c478d0fba755" />
we can see the replicaset and the pods that are ready.
<img width="960" alt="4" src="https://github.com/user-attachments/assets/b5deced4-20bd-43f1-9bf0-3fe32a648ea9" />

# step 3
creating mongo-config.yaml to store non-sensitive data like database address, like "mongodb-service" in this case.
<img width="960" alt="5" src="https://github.com/user-attachments/assets/8941968d-6921-4671-a36c-094aadbf7625" />
<img width="960" alt="6" src="https://github.com/user-attachments/assets/cdb12f3d-15c3-4098-87f5-72e9f7f79bc3" />

# step 4
creating mongo-express.yaml file 
<img width="960" alt="7" src="https://github.com/user-attachments/assets/116ce197-1814-4741-99e5-d3e939198201" />

# step 5
mongo-express-service created
<img width="960" alt="8" src="https://github.com/user-attachments/assets/52f6146e-b1ac-4fc6-ac43-95f7421c14d6" />

we got directed to login page
<img width="960" alt="10" src="https://github.com/user-attachments/assets/812183b0-68eb-4357-bf0e-ba23e2e5db81" />
I was not able to login through the user-name and password, because in the mongo express code we have to add "BASICAUTH" to login.

So I did again all the steps.
<img width="960" alt="r1" src="https://github.com/user-attachments/assets/9d68cd07-0f20-4f43-b01a-e2b56f2514a5" />
<img width="960" alt="r2" src="https://github.com/user-attachments/assets/b7624835-7649-4cbf-b8cb-0020bcb52834" />
# Public ip
<img width="960" alt="r4" src="https://github.com/user-attachments/assets/f5845458-4d0d-4620-904a-a8a77317319b" />
# now I am able to login thorugh user-name and password
<img width="960" alt="r3" src="https://github.com/user-attachments/assets/96a76dee-b363-495d-9020-d651ef100ce1" />
# cleanup 
<img width="960" alt="r5" src="https://github.com/user-attachments/assets/3960fdad-b4b9-4ff3-a86c-25b5264f9b4a" />
