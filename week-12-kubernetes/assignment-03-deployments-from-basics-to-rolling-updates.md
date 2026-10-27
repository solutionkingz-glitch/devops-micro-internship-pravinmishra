# Assignment 3 — Deployments: From Basics to Rolling Updates

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

Create an NGINX Deployment, configure RollingUpdate, update the container image, roll back to the previous revision, and scale the workload.

---

# Task 0 — Pre-check: Remove the Assignment 02 ReplicaSet

## Goal

Confirm that you are connected to your learning cluster and remove the previous ReplicaSet and its managed Pods before starting this lab.

### Evidence

No screenshots required.

---

# Task 1 — Set Up the Working Directory

## Goal

Create and enter the dedicated Deployment lab directory.

### Evidence

#### Screenshot 01 — Output of `pwd` showing the directory ending in `/k8s-labs/deployments`

![Assignment 5 Screenshots](screenshots/assgn3-img1.png)

---

# Task 2 — Create the Basic Deployment

## Goal

Create a two-replica NGINX Deployment and verify the automatically managed ReplicaSet and Pods.

### Evidence

#### Screenshot 02 — Completed basic `nginx-deployment.yaml` showing two replicas and the initial NGINX image

![Assignment 5 Screenshots](screenshots/assgn3-img2.png)

---

#### Screenshot 03 — Successful apply output and verification output showing the Deployment, its automatically created ReplicaSet, and two Pods with `1/1` under `READY` and `Running` under `STATUS`

![Assignment 5 Screenshots](screenshots/assgn3-img3.png)

---

# Task 3 — Configure the RollingUpdate Strategy

## Goal

Configure RollingUpdate to maintain the desired available replica count during an image update.

### Evidence

#### Screenshot 04 — Updated YAML showing `RollingUpdate`, `maxSurge: 1`, and `maxUnavailable: 0`

![Assignment 5 Screenshots](screenshots/assgn3-img4.png)

---

#### Screenshot 05 — Successful apply output and Deployment details showing the configured rolling-update strategy

![Assignment 5 Screenshots](screenshots/assgn3-img5.png)

---

# Task 4 — Perform and Roll Back an Image Update

## Goal

Update NGINX to 1.23.1, observe the rollout, and return to the previous stable revision.

### Evidence

#### Screenshot 06 — Image-update command and rollout status showing successful completion

![Assignment 5 Screenshots](screenshots/assgn3-img6.png)

---

#### Screenshot 07 — ReplicaSet output showing the previous and updated ReplicaSets, and Deployment details showing `nginx:1.23.1`

![Assignment 5 Screenshots](screenshots/assgn3-img7.png)

---

#### Screenshot 08 — Rollback command and rollout status showing successful completion

![Assignment 5 Screenshots](screenshots/assgn3-img8.png)

---

#### Screenshot 09 — Rollout history and Deployment details showing the restored `nginx:1.21.1` image

![Assignment 5 Screenshots](screenshots/assgn3-img9.png)

---

# Task 5 — Scale the Deployment

## Goal

Scale the workload to five replicas and return it to two.

### Evidence

#### Screenshot 10 — Scale-up command and output showing five Pods with `1/1` under `READY` and `Running` under `STATUS`

![Assignment 5 Screenshots](screenshots/assgn3-img10.png)

---

#### Screenshot 11 — Scale-down command and output showing the final two Pods with `1/1` under `READY` and `Running` under `STATUS`

![Assignment 5 Screenshots](screenshots/assgn3-img11.png)

---

# Task 6 — Share Your Kubernetes Deployment Progress on WhatsApp Status

## Goal

Share your Kubernetes Deployment learning progress on WhatsApp Status, including your generated DMI leaderboard progress link.

### Steps

1. Go to the DMI Leaderboard.
2. Find your name and select **Share your progress**.
3. Click the **WhatsApp icon**.
4. Copy the automatically generated leaderboard message containing your rank and progress link.
5. Open WhatsApp and go to **Updates**.
6. Create a new text Status.
7. Copy and paste the message below.
8. Insert the generated leaderboard message in the indicated place.
9. Review and publish your Status.

### WhatsApp Status Message

I practiced Kubernetes Deployments as part of my DevOps learning journey! 🚀

Today, I deployed NGINX, configured rolling updates, updated the container image, and rolled back to the previous version.

I also scaled my Deployment from two Pods to five and back to two!

[I just completed 12/14 weeks of the DevOps Micro Internship — Cohort 3 · Live! � https://dmi.pravinmishra.com/s/solutionkingz-glitch.html?utm_source=dmi&utm_medium=share&utm_campaign=badge-share-hero-whatsapp]

#DMIByPravinMishra #DevOps #Kubernetes

### Evidence

#### Screenshot 12 — Published WhatsApp Status showing your Kubernetes Deployment message and generated DMI leaderboard progress link

![Assignment 5 Screenshots](screenshots/assgn3-img12.png)

---

# Lab Summary

Write a short note explaining how Deployments manage ReplicaSets, perform rolling updates and rollbacks, and scale Pods.

**How do Deployments manage ReplicaSets, perform rolling updates and rollbacks, and scale Pods?**

A **Deployment** is a higher-level controller that manages ReplicaSets for you. You declare the desired state (image, replica count, update strategy), and the Deployment creates and controls a ReplicaSet, which in turn creates and maintains the Pods. You rarely touch the ReplicaSet directly.

**Managing ReplicaSets**
Each time you change the Pod template (for example, the image version), the Deployment creates a **new ReplicaSet** for that version. The old ReplicaSets are kept (scaled to 0) as revision history. You can see them with `kubectl get replicaset`.

**Rolling updates**
When the Pod template changes, the Deployment gradually shifts Pods from the old ReplicaSet to the new one instead of replacing everything at once. With the `RollingUpdate` strategy in this lab:

- `maxSurge: 1` allows one extra Pod above the desired count during the update.
- `maxUnavailable: 0` means no Pod is removed until its replacement is ready.

This keeps the application available throughout the update.

    kubectl set image deployment/nginx-deployment nginx=nginx:1.25
    kubectl rollout status deployment/nginx-deployment

**Rollbacks**
Because old ReplicaSets are retained, the Deployment can return to a previous version quickly by scaling the old ReplicaSet back up and the new one down.

    kubectl rollout history deployment/nginx-deployment
    kubectl rollout undo deployment/nginx-deployment

**Scaling**
Scaling changes the `replicas` value, and the Deployment passes that to its current ReplicaSet, which adds or removes Pods. Scaling does not create a new revision.

    kubectl scale deployment/nginx-deployment --replicas=5

Or edit `replicas` in the YAML and re-run `kubectl apply -f nginx-deployment.yaml`.

**Summary:** A Deployment manages ReplicaSets to provide versioned, zero-downtime rolling updates, quick rollbacks, and simple scaling, which is why Deployments are preferred over bare ReplicaSets in real environments.

---

# Submission Instructions

- Include all required screenshots, numbered 01–12.
- Ensure screenshots are clear and readable.
- Submit the final `nginx-deployment.yaml` containing two replicas, the initial NGINX image, and the configured RollingUpdate strategy.
- Complete the Lab Summary in your own words.
- Include evidence of your published WhatsApp Status.
- Do not expose passwords, tokens, private keys, or kubeconfig credentials.

---

# Completion Checklist

- [ ] Completed Task 0
- [ ] Created the deployments directory (Screenshot 01)
- [ ] Created the basic two-replica NGINX Deployment manifest (Screenshot 02)
- [ ] Applied the Deployment and verified its ReplicaSet and two running Pods (Screenshot 03)
- [ ] Added RollingUpdate with `maxSurge: 1` and `maxUnavailable: 0` (Screenshot 04)
- [ ] Applied and verified the rolling-update strategy (Screenshot 05)
- [ ] Updated NGINX to 1.23.1 and confirmed rollout completion (Screenshot 06)
- [ ] Inspected the ReplicaSets and verified the updated image (Screenshot 07)
- [ ] Rolled back the update and confirmed rollout completion (Screenshot 08)
- [ ] Reviewed rollout history and verified the restored image (Screenshot 09)
- [ ] Scaled to five running Pods (Screenshot 10)
- [ ] Scaled back to two running Pods (Screenshot 11)
- [ ] Published the WhatsApp Status with the generated leaderboard progress link (Screenshot 12)
- [ ] Submitted the final `nginx-deployment.yaml`
- [ ] Included screenshots 01–12
- [ ] Completed the Lab Summary
- [ ] No sensitive data exposed

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track.*
