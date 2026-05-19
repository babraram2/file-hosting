# 📦 Split Files (45MB parts)

Each file below is split into **45MB zip parts** and stored in its own folder.

## 📄 gemma-3-4b-it-abliterated.q4_k_m

**Parts: 1**

- [gemma-3-4b-it-abliterated.q4_k_m.zip](https://github.com/babraram2/file-hosting/raw/main/model/gemma-3-4b-it-abliterated.q4_k_m/gemma-3-4b-it-abliterated.q4_k_m.zip) (39M)

## 🔧 How to Reassemble

### Option 1: Download using Git (PowerShell)

Use this PowerShell script to download all parts for a specific file:

```powershell
# Clone the repository with sparse checkout to get only the model files
git clone --filter=blob:none --sparse https://github.com/babraram2/file-hosting.git
cd file-hosting

# Enable sparse checkout and set it to get only the model folder you need
git sparse-checkout init --cone
git sparse-checkout set model/foldername

# Pull the LFS files
git lfs pull

# Navigate to the folder
cd model/foldername

# Reassemble and extract the file
unzip filename.zip
```

**Note:** Replace `foldername` and `filename` with the actual folder and file names from above.

### Option 2: Download individual files (Linux/macOS)

```bash
# Download all parts manually (replace foldername with actual name)
mkdir -p model/foldername
cd model/foldername

# Download each part (check the parts list above for exact filenames)
wget https://github.com/babraram2/file-hosting/raw/main/model/foldername/filename.zip
wget https://github.com/babraram2/file-hosting/raw/main/model/foldername/filename.z01
# ... continue for all parts ...

# Extract the file
unzip filename.zip
```

### Option 3: Download with PowerShell (Windows)

```powershell
# Create folder and download all parts (replace foldername and filename)
$folder = "model/foldername"
New-Item -ItemType Directory -Force -Path $folder
cd $folder

# Download each part (check the parts list above for exact filenames)
Invoke-WebRequest -Uri "https://github.com/babraram2/file-hosting/raw/main/model/foldername/filename.zip" -OutFile "filename.zip"
Invoke-WebRequest -Uri "https://github.com/babraram2/file-hosting/raw/main/model/foldername/filename.z01" -OutFile "filename.z01"
# ... continue for all parts ...

# Extract using 7-Zip or WinRAR
# Right-click filename.zip → Extract Here
```

## 📝 Notes

- Git clone with sparse checkout is the fastest way to get all parts
- All files use Git LFS (Large File Storage)
- Make sure you have Git LFS installed: https://git-lfs.com
- Split archives can be extracted with 7-Zip, WinRAR, or the unzip command
