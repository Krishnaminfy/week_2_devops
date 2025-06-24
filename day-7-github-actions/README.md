# day-7-github-actions-takehome

# step 1
I created app.js and Dockerfile and installed express using npm, after doing npm init, I got package.json 
<img width="960" alt="0" src="https://github.com/user-attachments/assets/6af0cc6f-8b40-4b84-98a4-9764584c56fa" />
# Installing docker inside ec2 instance
I used terraform code to launch the ec2 instance, which I previously used in the last assignment.
<img width="960" alt="1" src="https://github.com/user-attachments/assets/813dd9e3-da47-48c6-8211-8c3c5df25921" />
<img width="960" alt="2" src="https://github.com/user-attachments/assets/fbce17cc-a3a2-4dad-8f8c-07c495732278" />
<img width="960" alt="3" src="https://github.com/user-attachments/assets/561d50ad-93ae-430b-9eb6-9c020bd9a402" />
# docker version
<img width="959" alt="12" src="https://github.com/user-attachments/assets/a925a726-3c36-43d6-9d05-3d6dd8d8b972" />

adding secret variables inside the settings of github repo 
<img width="960" alt="5" src="https://github.com/user-attachments/assets/3988eb85-4175-4d29-a884-44b664af18d3" />
<img width="960" alt="6" src="https://github.com/user-attachments/assets/7db8c2a3-86dc-4a22-8bf4-1922f5744589" />
# Actions tab
checking if my yaml code is working correct or not
<img width="960" alt="7" src="https://github.com/user-attachments/assets/6974d8a8-b42a-4f25-ae46-93dc1d99279a" />
 Doing some changes, which can be the issue and again trying.
<img width="958" alt="8" src="https://github.com/user-attachments/assets/c084085f-ac92-426e-b003-30c8eb070a70" />

<img width="959" alt="9" src="https://github.com/user-attachments/assets/8b3dc3f5-a736-422e-a108-19277136fd07" />

Deployed for the first time!!
<img width="958" alt="10" src="https://github.com/user-attachments/assets/2a77a6de-00f4-43b6-84e1-4b2df0f83eb7" />
# All workflows
<img width="960" alt="20" src="https://github.com/user-attachments/assets/3614b191-42e4-4334-a6dc-24e3357adb7a" />
After getting a green signal also, I wasnt able to see anything on http://<ip_adress>:3000, so I tried getting details via ssh into my local machine to make sure if docker is running or not.

<img width="959" alt="13" src="https://github.com/user-attachments/assets/28c3392c-b10f-4a73-94a1-f0c8a745754f" />
<img width="956" alt="14" src="https://github.com/user-attachments/assets/85735f63-981f-4f8b-9814-cb69b24a2b47" />
I can see from localhost inside ec2 instance.
<img width="960" alt="15" src="https://github.com/user-attachments/assets/dd248341-f3b5-49a2-819f-6691ae0f09d2" />

# problem
I forgot to give inbound traffic rule from port 3000, so I was not getting anything on http://<ip_adress>:3000, so I added manually, this happened because I used the previuos code, and this was the only difference.
<img width="960" alt="17 inboundrule" src="https://github.com/user-attachments/assets/a3c83880-d673-43e3-89a7-811c6d9f7641" />

# Done!!

after setting the inbound rule, I am able to see my container running inside ec2 instance.
<img width="960" alt="16" src="https://github.com/user-attachments/assets/49c42647-dc15-4807-a593-449f9219555d" />


# cleanup

destroying all the resources in use.
<img width="953" alt="18" src="https://github.com/user-attachments/assets/ef5b8096-2b94-44d0-9adb-ae1239917ff2" />
<img width="957" alt="19" src="https://github.com/user-attachments/assets/68fb6c29-4bf0-4c4b-b910-2c39c274073f" />

# changes

# in the app.js file
- app.listen(PORT, '0.0.0.0', () => {
-   console.log(`Server running on http://0.0.0.0:${PORT}`);
- });

# in workflow file
Hardcoded image name: Replaced ${{ github.repository }} with lowercase ghcr.io/krishnaminfy/day-7-github-actions-takehome to fix invalid tag error.

Removed metadata-action: Simplified tagging by using a fixed :latest tag to avoid digest-related complexity.

Replaced GITHUB_TOKEN with GHCR_PAT: Used a personal access token in EC2 to enable Docker login, as GITHUB_TOKEN doesn't work outside GitHub Actions.

Simplified Docker run logic: Pulled and ran image using :latest tag instead of digest to keep the deployment process clear and beginner-friendly.

# manual changes

I used GitHub Container Registry (GHCR) to store and access Docker images securely and seamlessly within GitHub Actions and from the EC2 server.





