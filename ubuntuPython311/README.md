# Ubuntu 22.04 + Python 3.11 Base Image

This image provides a clean, Ubuntu 22.04 LTS (Jammy) environment with **Python 3.11**, `pip`, `setuptools`, and `venv` pre-installed.  
It is designed to serve as a **general-purpose base image** for building Python applications and services.

---

## 🧩 Key Features
- Based on official **Ubuntu 22.04 LTS**
- Ships with **Python 3.11**, `pip`, `setuptools`, and `wheel`
- Includes essential build tools (`gcc`, `make`, `libffi-dev`, etc.)
- Suitable for data science, AI/ML, web, or backend workloads
- Clean and minimal — no unnecessary dependencies
- Regularly rebuilt and tested for security updates

---

## 📦 Example Usage

```dockerfile
FROM quay.io/samyaug/ubuntu-python3.11:base

# Install project dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . /app
WORKDIR /app

CMD ["python3", "app.py"]
```
### 🛠️ Installed Components

**Ubuntu:** 22.04 LTS (Jammy)  
**Python:** 3.11.x (via Deadsnakes PPA)  
**pip:** Latest  
**setuptools / wheel:** Latest  
**Compiler tools:** Included (build-essential)

---

### 🧰 Tags

**base:** Core Python 3.11 runtime on Ubuntu 22.04  
**slim (optional):** Stripped-down variant for smaller deployments

---

### 📬 Support

For inquiries, issues, or collaboration:

🌐 [https://www.samyaug.in](https://www.samyaug.in)  
✉️ [support@samyaug.in](mailto:support@samyaug.in)