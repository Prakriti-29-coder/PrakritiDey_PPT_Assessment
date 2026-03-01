# Task 19: Azure Storage Account (Blob, File, Table)

## Objective
The purpose of this task is to **create and explore Azure Storage services** by working with **Blob Storage**, **File Storage**, and **Table Storage**. This helps in understanding Azure's multi-storage capabilities.

---

## Prerequisites
- Azure subscription (Free/Paid)
- Access to [Azure Portal](https://portal.azure.com/)
- Basic understanding of storage concepts (Blob, File, Table)

---

## Steps Performed

### Step 1: Create a Storage Account
1. Log in to the Azure Portal.
2. Search for **Storage Accounts** and click **+ Create**.
3. Fill in the required details:
   - **Subscription**: Select your subscription
   - **Resource Group**: Create new or use existing
   - **Storage Account Name**: `mystorageaccount`
   - **Region**: Choose your preferred region
   - **Performance**: Standard
   - **Replication**: LRS (Locally-redundant storage)
4. Click **Review + Create**, then **Create**.

---

### Step 2: Explore Blob Storage
1. Go to the created storage account.
2. Click **Containers** → **+ Container**.
3. Create a container:
   - **Name**: `myblobcontainer`
   - **Public Access Level**: Private (default)
4. Upload a sample file to the container:
   - Click **Upload** → Select file → **Upload**
5. Verify the file is uploaded.

---

### Step 3: Explore File Storage
1. In the storage account, go to **File shares** → **+ File Share**.
2. Create a file share:
   - **Name**: `myfileshare`
   - **Quota**: 100 GB (or any size)
3. Click **Create**.
4. Upload sample files:
   - Click **Upload** → Select file → **Upload**
5. Verify the files are visible in the file share.

---

### Step 4: Explore Table Storage
1. In the storage account, go to **Tables** → **+ Table**.
2. Create a table:
   - **Name**: `mytable`
3. Click **Create**.
4. Add sample data:
   - Click **Add entity**
   - Fill in **PartitionKey**, **RowKey**, and other fields
   - Click **OK** to save
5. Verify the entity is created in the table.

---

### Step 5: Verification
- Confirm that:
  - Blob container exists and files are uploaded
  - File share exists and files are uploaded
  - Table exists and entities are added

---

## Proof of Completion
- **Screenshot 1**: Storage account overview.
- **Screenshot 2**: Blob container and uploaded file.
- **Screenshot 3**: File share or Table with sample data.

---

## Outcome
- Successfully created an Azure Storage Account (`mystorageaccount`).
- Explored and uploaded data to **Blob**, **File**, and **Table** storage.
- Learned basic storage operations in Azure.

---

**Note**: Replace storage account name, container, file share, and table names according to your lab environment.
