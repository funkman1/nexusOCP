# Configure Nexus Docker hosted repository for OpenShift


## Overview

TBD

## Important Notes

TBD




## 1) Configure a Docker hosted repo in Nexus

**1.1)** Click the Sign in button in the top right of the Nexus UI, and **log in as the admin user.**

**1.2)** To create our docker hosted repo, we first need **to create a blob store.** **Click the cog icon in the top left of the screen, and under the repo sections on the left side bar click the blob stores tab.**

**1.3)** **Select File as the blob store type, give it an appropriate name, and note the path of where the store is located.**

**1.4)** Now click repositories on the left side bar and click the option, **docker (hosted)**.

**1.5)** Start by giving your repo a name.

**1.6)** **Specify a repository connecter**, I specified port 8083 under HTTP as it is available on my machine and follows port 8081 which the Nexus UI runs on.

**1.7)** **Scroll down to blob store and then pick the blob store we just created.**

**1.8)** ***Deployment policy?***

**1.9)** **Hit create**, our repo should now display to be online.

## 2) Create Privileges for Roles to apply to users
#### Note: Privileges define actions which can be performed against specific functionality. Privileges can only be assigned to roles. Privileges included by default are prefixed with nx-

#### The following example creates a local read only user 
**2.1)** **Make sure you are signed in as admin in the Nexus UI.**

**2.2)** Click the cog button at the top of the page, scroll down on the left side bar until you see security, under the security section click on roles, and create role.

**2.3)** The Role type is of type **Nexus role.**

**2.4)** Assign an **appropriate Role ID and name.** Ideally something correlated to the repo and privilege the role extends.

**2.5)** Click the modify applied privileges section. **In the filter search for the name of your repo, then select the repository-view browse and read privileges.**

**2.6)** **Click save and our role has been created.**

**2.7)** **To create a read write user,** follow the same steps with the **addition of repository-view add and edit** in the applied privileges section(2.5).

## 3) Create Openshift pull secret
