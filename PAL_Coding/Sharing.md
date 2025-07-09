# Storage Structure Overview in PAL's Coding Component 

## Personal Buckets

- **`~/my-private-bucket`**  
  Each user has a private bucket folder mounted in `/home/jovyan`. This is your personal, private storage.

- **`~/my-public-bucket`**  
  A public folder for each user.  
  - Files placed here are **automatically uploaded** and become **publicly accessible**.  
  - To find your user ID:
    ```bash
    ls -l ~/my-public-bucket
    ```

## Shared Buckets

- **`my_storage/`**
  - `Processing_outputs/`  
  - `Uploaded_data/`

- **`Shared-bucket/`**  
  A shared space accessible by multiple users.


