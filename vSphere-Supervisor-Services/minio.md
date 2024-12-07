---
title: MinIO
menu_order: 1
post_status: draft
comment_status: closed
taxonomy:
    category: vSphere-Supervisor-Services
---

![MinIO](/_images/minio-logo.png)

# MinIO Quickstart Guide - Updated for vSphere 8 U3 (VCF 5.2.1) Supervisor Service
---

When I decided to deploy MinIO to my "vSphere Supervisor" Lab I of course warmed up my search skills. Did some finger streches and pounded on the keyboard. I found quite a lot of info out there. However reading through blogs and docs, and tigers and bears. I found, that what was out there, got me 85% of the way there. The amazing coimmunity of support just could not get me over the finish line. Everything I found was 7 U3 or before. Luckily I had the time and contacts to find the answers to what buttons to push to get thissimply task done. So to help give back here is what I quickly put together as a QuikStart Step by Step on getting Minio Installed and ready to go.


![alt text](/_images/shot1.png)




1. In vCenter - From the Berger Menu - Select **Workload Management**

---
![alt text](/_images/workload.mangement.png)

2. In Workload Management Select **Services**

3. Click **ADD** under Add new Service
---

![alt text](/_images/register.service.png)

Click the URL Discover and download available Supervisor Services here.
---

![alt text](/_images/vsan.dpp.png)

Click the **URL** vSAN Data Persistance Platform (vDPP) Services:
---

![alt text](/_images/vsan.dpp.2.png)

Click the **URL** for Downlod version: Minio 2.0.10 to download the deployment yaml for the Minio Service.
---
![alt text](/_images/register.service.png)

Go back to vCenter and click Upload, select the downloaded minio yaml file
---
![alt text](/_images/new.service.minio.png)

Click **NEXT**

![alt text](/_images/eula.png)

Accept the **EULA**

Click **FINISH**
---
![alt text](/_images/manage.service.minio.png)

Once the Service is deployed to vSphere it needs to added to the Supervisor

Click **ACTIONS** under Minio

Select Manage Service
---
![alt text](/_images/manage.configure.png)

Select your Superviser

Click **NEXT**
---
![alt text](/_images/manage.review.png)

No Values file for Minio

Click **FINISH**
---
![alt text](/_images/plugin.deployed.png)

Wait for the Minio Plugin install task to finish
---
![alt text](/_images/minio.plugin.general.png)

In Workload management slect the **Supervisor --> Configure --> Minio --> General** to confirm that the Service is up and you can get to the vCenter plugin
---
![alt text](/_images/minio.plugin.tenant.png)

Click in **Minio --> Tenant --> ADD**
---
![alt text](/_images/create.tenant.name.tenant.png)

Give the Tenant a Name (MetaData)

Enter the vSphere Supervisor Namespace you wish to assign this Tenant to (must match)

Choose the storage class assigned to the Namespace you wish to use for tenant Storage

Click **NEXT**
---
![alt text](/_images/create.tenant.tenant.size.png)

Configure the Tenant Server size
---
![alt text](/_images/create.tenant.preview.configuration.png)

Preview your entries

Click **CREATE**
---
![alt text](/_images/create.tenant.credetials.png)

Make Sure you Download the credentials file. You will not be shown this info again.

Click **FINISH**
---
![alt text](/_images/minio.tenant.details.1.png)

Select the new Tenant click **DETAILS**

---
![alt text](/_images/minio.tenant.details.2.png)

Click **HEALTH**

---
![alt text](/_images/minio.tenant.details.3.png)

Once the Tenant is up and Running click back to **DETAILS**

---
![alt text](/_images/minio.tenant.details.2.png)

Click the **Console Endpoint URL**

---
![alt text](/_images/creds.json.file.png)

Find the crentials.json file you downloaded earlier

For Login into the Console "access_key" = **UserID** and "secret_key" = **Password**

---
![alt text](/_images/object.store.login.1.png)

**Login**

---
![alt text](/_images/object.store.ui.png)

You are ready to administer the tenant.
