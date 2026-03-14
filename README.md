# 🚀 End-to-End Data Engineering: Incremental ETL Lab with Azure Databricks

This repository provides a hands-on guide to mastering **Incremental Data Ingestion** and transformation using **Azure Databricks**, **ADLS Gen2**, and the **Medallion Architecture**.

---

## 🏗️ Project Architecture
This diagram illustrates the end-to-end data pipeline from source ingestion to final reporting.

![Project Architecture](images/project_Architecture.jpg)

---

## 📋 Prerequisites
Ensure you have the following ready before starting:
* **Azure Account:** An active subscription.
* **VS Code Extensions:** Ensure the **Azure** and **Databricks** extensions are installed.
* **Workspace:** An existing Azure Databricks workspace.

![Databricks Extensions](images/DataBricks_Extensions_installed.jpg)

---

## 🛠️ Step 1: Azure Environment Setup

### 1. Resource Group Creation
Create a Resource Group named `Databricks_project1` to act as the container for all lab resources.

| Action | Visual Reference |
| :--- | :--- |
| **Defining the Group** | ![Creating Resource Group](images/create_Resources_Group.png) |
| **Success Confirmation** | ![Created Resource Group](images/Created_Resources_Group.png) |

---

### 2. Storage Configuration (ADLS Gen2)
The **Storage Account** serves as the landing zone for our raw data.

1. **Search Marketplace:** Search for "Storage account" and click **Create**.
2. **Basics:** Link it to your `Databricks_project1` resource group.
3. **Advanced:** 🔑 **Enable hierarchical namespace** to activate Data Lake Gen2.

| Step | Visual Reference |
| :--- | :--- |
| **Marketplace** | ![Search Storage](images/First_resource_storage1_MarketPlace.png) |
| **Networking** | ![Networking](images/Networking_Configuration.png) |
| **ADLS Gen2 Enable** | ![Advanced Tab](images/Advanced_Configuration.png) |

---

### 3. Data Lake Ingestion Structure
Now we prepare the specific folders where our raw files will be stored.

#### **A. Create a Container**
Create a container named `source`. This will hold all our incoming raw data.

![Create Container](images/container_storage_databricks01p01.png)

#### **B. Create Directories & Upload Data**
Inside the `source` container, create a directory called `orders` and upload your raw CSV/JSON files.

| Action | Visual Reference |
| :--- | :--- |
| **Add Directory** | ![Add Directory](images/folder_container_storage_databricks01p01.png) |
| **Upload Files** | ![Upload Process](images/upload_folder_container_storage_databricks01p01.png) |
| **Final View** | ![Files Uploaded](images/source_folders_datauplodedin.png) |

---

## ⚠️ Troubleshooting: Git Remote Sync
If you encounter a `Not Found` error during your first push, verify your remote URL:

```bash
git remote set-url origin [https://github.com/MomoGasmi/End-to-End-Data-Engineering-Incremental-ETL-Lab-with-Azure-Databricks-.git](https://github.com/MomoGasmi/End-to-End-Data-Engineering-Incremental-ETL-Lab-with-Azure-Databricks-.git)
git pull origin main --rebase