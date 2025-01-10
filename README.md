### **Design & Structure**

#### **1. Configuration File (`config.json`)**
The configuration file will store all necessary parameters:
- **`google_credentials_path`**: Path to the service account credentials file.
- **`bucket_name`**: The GCS bucket where files will be uploaded.
- **`source_file_path`**: Path to the local file that needs to be uploaded.
- **`destination_blob_name`**: Destination path and filename inside the GCS bucket.

**Example `config.json`:**
```json
{
    "google_credentials_path": "/path/to/service-account-file.json",
    "bucket_name": "your-bucket-name",
    "source_file_path": "/path/to/local/file.txt",
    "destination_blob_name": "uploads/2025_01_10/file.txt"
}
```

#### **2. Authentication (`auth.py`)**
This module will handle authentication with Google Cloud using the service account credentials. The **`google-auth`** library will be used to securely authenticate and obtain access to the Google Cloud Storage API.

#### **3. File Upload Logic (`file_upload.py`)**
This module will be responsible for the file upload functionality. It will use the **`google-cloud-storage`** Python library to upload the file to the specified GCS bucket.

#### **4. Main Program (`main.py`)**
The main script will:
- Load the configuration from `config.json`.
- Authenticate with Google Cloud.
- Perform the file upload to the GCS bucket.

---

### **Folder Structure**

The project will follow a modular and organized structure:

```
google-file-upload/
│
├── config/
│   └── config.json          # Configuration file for settings
├── src/
│   ├── auth.py             # Authentication logic for Google Cloud
│   ├── file_upload.py      # File upload logic using GCS API
│   ├── config_loader.py    # Logic to load and validate config
│   └── main.py             # Main program to run the upload process
├── tests/
│   └── test_upload.py      # Unit tests for the upload functionality
├── requirements.txt        # List of Python dependencies
└── README.md               # Project documentation
```

- **`src/`**: Contains all core logic and modules.
- **`tests/`**: Contains unit tests to validate the functionality.
- **`config/`**: Stores configuration files.
- **`requirements.txt`**: Lists required Python libraries (`google-auth`, `google-cloud-storage`, `json`).
- **`README.md`**: Provides project setup instructions and usage.

---
