# SkyScan - Professional Vulnerability Detection Platform

[![Python](https://img.shields.io/badge/Python-3.13-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-green.svg)](https://fastapi.tiangolo.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Latest-brightgreen.svg)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Deployed on Railway](https://img.shields.io/badge/Deployed-Railway-blueviolet.svg)](https://railway.app/)

A professional-grade vulnerability detection and security assessment platform for network infrastructure and cloud environments. Features advanced scanning capabilities, compliance mapping, and comprehensive vulnerability reporting.

🔗 **Live Demo**: [SkyScan on Railway](https://skyscan-production.up.railway.app/)
### Advanced Scanning Capabilities
- ✅ **Professional Network Scanning** - Multi-technique Nmap scanning with service detection, OS fingerprinting, and version analysis
- ✅ **Cloud Security Assessment** - Comprehensive checks for AWS/Azure/GCP with compliance framework mapping (CIS, NIST, PCI-DSS, HIPAA, SOC2)
- ✅ **Real-time Vulnerability Detection** - Automated CVE correlation based on service versions with risk scoring
- ✅ **CVSS v3 Scoring** - Professional risk assessment and vulnerability prioritization
- ✅ **Compliance Reporting** - Automated compliance status for multiple frameworks
- ✅ **Detailed Remediation Plans** - Step-by-step guidance with prioritized recommendations

### User Experience
- ✅ **Modern UI** - Starry animated background with professional dashboard
- ✅ **Real-time Updates** - Live scan progress tracking and history
- ✅ **Secure Authentication** - JWT-based auth with bcrypt password hashing
- ✅ **Responsive Design** - Works seamlessly on desktop and mobile

### Technical Excellence
- **Backend**: Python 3.13, FastAPI, Uvicorn (async)
- **Database**: MongoDB with Motor (async driver)
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla), Bootstrap 5
- **Security**: JWT tokens, bcrypt hashing, environment-based configuration
- **Deployment**: Docker, Railway (production), easy local setup

## 📁 Project Structure

```
skyscan/
│
├── app/                          # Backend application
│   ├── auth/                     # Authentication system
│   │   ├── auth_models.py        # User & token Pydantic models
│   │   ├── auth_service.py       # JWT & bcrypt services
│   │   └── auth_router.py        # Login/register endpoints
│   │
│   ├── users/                    # User management
│   │   └── users_router.py       # User info & scan history
│   │
│   ├── scan/                     # Professional scanning engine
│   │   ├── network_scanner.py    # Nmap-based network scanner with CVE detection
│   │   ├── cloud_scanner.py      # Cloud security & compliance scanner
│   │   ├── fingerprint.py        # Service version fingerprinting
│   │   ├── match_engine.py       # CVE matching & correlation
│   │   ├── cvss_engine.py        # CVSS v3 scoring & risk assessment
│   │   └── scan_router.py        # Scan initiation endpoints
│   │
│   ├── reports/                  # Report generation
│   │   └── report_builder.py     # Professional report formatting
│   │
│   ├── database/                 # Database layer
│   │   └── mongodb.py            # Async MongoDB connection
│   │
│   ├── config.py                 # Environment-based configuration
│   └── main.py                   # FastAPI application entry point
│
├── frontend/                     # Modern web interface
│   ├── index.html                # Landing page with starry background
│   ├── dashboard.html            # Security dashboard
│   ├── login.html                # Authentication pages
│   ├── register.html
│   └── static/                   # Assets
│       ├── styles.css            # Professional styling
│       ├── starry-bg.js          # Animated background
│       ├── dashboard.js          # Dashboard logic
│       └── auth.js               # Authentication handling
│
├── Dockerfile                    # Production Docker image
├── docker-compose.yml            # Local development setup
├── requirements.txt              # Python dependencies
├── runtime.txt                   # Python 3.13 for Railway
├── run.py                        # Production entry point
└── .env.example                  # Environment configuration template
│   │   ├── scan_router.py        # Scan endpoints
│   │   └── cve_database.json     # CVE data
│   │
│   ├── database/                 # Database layer
│   │   └── mongodb.py            # MongoDB connection
│   │
│   ├── reports/                  # Report generation
│   │   └── report_builder.py     # Report builder
│   │
│   ├── config.py                 # Configuration
│   └── main.py                   # FastAPI application
│
├── frontend/                     # Frontend application
│   ├── index.html                # Landing page
│   ├── login.html                # Login page
│   ├── register.html             # Registration page
│   ├── dashboard.html            # User dashboard
│   │
│   └── static/                   # Static assets
│       ├── styles.css            # Custom styles
│       ├── auth.js               # Authentication logic
│       └── dashboard.js          # Dashboard logic
│
├── requirements.txt              # Python dependencies
├── Dockerfile                    # Docker image config
├── docker-compose.yml            # Docker compose config
├── .env.example                  # Environment template
├── .gitignore                    # Git ignore rules
└── README.md                     # This file
```

## 🚀 Quick Start

### Prerequisites
- **Python 3.13+** installed
- **MongoDB** (via Railway for production, or local for development)
- **Nmap** installed (for network scanning)
- **Git** for version control

### Local Development Setup

#### 1. Install Nmap
Download and install Nmap from [nmap.org](https://nmap.org/download.html)

Add Nmap to system PATH (usually `C:\Program Files (x86)\Nmap`)

#### 2. Clone Repository
```powershell
git clone https://github.com/kaizer2nd/skyscan.git
cd skyscan
```

#### 3. Create Virtual Environment
```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

#### 4. Install Dependencies
```powershell
pip install -r requirements.txt
```

#### 5. Configure Environment
Create `.env` file from template:
```powershell
cp .env.example .env
```

Edit `.env` with your MongoDB connection string:
```env
MONGODB_URL=mongodb://localhost:27017/skyscan
SECRET_KEY=your-secret-key-here
```

#### 6. Run Application
```powershell
python run.py
```

Visit `http://localhost:8000` to access SkyScan.

### Production Deployment (Railway)

SkyScan is deployed on [Railway](https://railway.app) at [skyscan-production.up.railway.app](https://skyscan-production.up.railway.app)

#### Deploy Your Own Instance

1. **Fork Repository**
```powershell
# Fork on GitHub, then clone your fork
git clone https://github.com/YOUR_USERNAME/skyscan.git
```

2. **Create Railway Project**
- Visit [railway.app](https://railway.app)
- Click "New Project" → "Deploy from GitHub"
- Select your forked repository

3. **Add MongoDB Service**
- In Railway project, click "New" → "Database" → "Add MongoDB"
- Copy the connection string from MongoDB service variables

4. **Configure Environment Variables**
Set these variables in Railway:
```
MONGODB_URL=<your-railway-mongodb-connection-string>
SECRET_KEY=<generate-secure-random-key>
PORT=8000
```

5. **Deploy**
- Railway auto-deploys on push to main branch
- Build uses `Dockerfile` (installs nmap automatically)
- Application starts with `run.py`

### Docker Setup (Alternative)

```powershell
# Build image
docker build -t skyscan .

# Run container
docker run -p 8000:8000 -e MONGODB_URL="your-connection-string" skyscan
```

Or use Docker Compose:
```powershell
docker-compose up --build
```

```powershell
docker-compose up --build
```

## 📖 Usage

### 1. Register Account
- Visit `/register` or click "Register" on homepage
- Create account with email and secure password
- Login redirects to dashboard automatically

### 2. Network Scanning
Scan network infrastructure for vulnerabilities:

```bash
POST /api/scan/network
{
  "targets": "192.168.1.0/24",  # Single IP, range, or CIDR
  "scan_type": "quick"           # 'quick' or 'comprehensive'
}
```

**Features:**
- **Asset Discovery**: Detects live hosts with OS fingerprinting
- **Port Analysis**: Scans 22+ common ports (SSH, HTTP, HTTPS, FTP, MySQL, RDP, SMB, etc.)
- **Service Detection**: Identifies running services with version information
- **CVE Matching**: Automatically correlates known vulnerabilities with detected services
- **Risk Scoring**: CVSS v3-based risk assessment for each finding
- **Compliance Mapping**: Maps vulnerabilities to CIS, NIST, PCI-DSS, HIPAA, SOC2 frameworks

### 3. Cloud Security Scanning
Assess cloud infrastructure security posture:

```bash
POST /api/scan/cloud
{
  "provider": "aws",             # 'aws', 'azure', or 'gcp'
  "credentials": {...},          # Cloud provider credentials
  "region": "us-east-1"
}
```

**Checks:**
- **Storage Security**: Public buckets, versioning, encryption at rest
- **Network Exposure**: SSH, RDP, database ports open to 0.0.0.0/0
- **IAM Security**: MFA enforcement, inactive users, overprivileged service accounts
- **Encryption**: Unencrypted EBS volumes, KMS key rotation
- **Logging**: CloudTrail, VPC Flow Logs, S3 access logging
- **Password Policies**: Strength requirements, rotation, expiration
- **Compliance Assessment**: Automated compliance framework alignment
- **Risk Scoring**: Weighted risk score (0-100) based on findings

### 4. View Reports
- Access scan history from dashboard
- Download detailed PDF/JSON reports
- Review compliance status across frameworks
- Track remediation progress

### 5. API Documentation
Interactive API docs available at:
- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

Key endpoints:
- `POST /api/auth/register` - Create account
- `POST /api/auth/login` - Get JWT token
- `GET /api/users/me` - Get user profile
- `POST /api/scan/network` - Initiate network scan
- `POST /api/scan/cloud` - Initiate cloud scan
- `GET /api/users/me/scans` - Retrieve scan history
cd C:\Users\RAKSHIT\OneDrive\Documents\MIT\MINI_PROJECT

# Build and start containers
docker-compose up --build

# Or run in detached mode
docker-compose up -d
```

#### Stop Application
```powershell
docker-compose down

# To remove volumes as well
docker-compose down -v
```

## 🔐 API Usage

### Authentication Flow

#### 1. Register User
```bash
POST /api/auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Response:**
```json
{
  "id": "507f1f77bcf86cd799439011",
  "email": "user@example.com",
  "created_at": "2024-12-03T10:30:00",
  "is_active": true,
  "scan_count": 0
}
```

#### 2. Login
```bash
POST /api/auth/login
Content-Type: application/x-www-form-urlencoded

username=user@example.com&password=securepassword123
```

**Response:**
```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "token_type": "bearer"
}
```

### Vulnerability Scanning

#### Network Scan
```bash
POST /api/scan/network
Authorization: Bearer {access_token}
Content-Type: application/json

{
  "target": "127.0.0.1",
  "scan_type": "quick"
}
```

#### Cloud Scan
```bash
POST /api/scan/cloud
Authorization: Bearer {access_token}
Content-Type: application/json

{
  "config": null
}
```

#### Full Scan (Network + Cloud)
```bash
POST /api/scan/full
Authorization: Bearer {access_token}
Content-Type: application/json

{
  "target": "127.0.0.1",
  "scan_type": "full"
}
```

### User Management

#### Get User Info
```bash
GET /api/user/info
Authorization: Bearer {access_token}
```

#### Get Scan History
```bash
GET /api/user/history
Authorization: Bearer {access_token}
```

#### Get Scan Details
```bash
GET /api/user/scan/{scan_id}
Authorization: Bearer {access_token}
```

## 📊 Database Schema

### Users Collection
```javascript
{
  _id: ObjectId,
  email: String,
  hashed_password: String,
  created_at: DateTime,
  is_active: Boolean,
  scan_history: [
    {
      scan_id: String,
      timestamp: DateTime,
      scan_type: String,        // "network", "cloud", "full"
      summary: String,
      severity_counts: {
        CRITICAL: Number,
        HIGH: Number,
        MEDIUM: Number,
        LOW: Number
      },
      full_report_json: Object,
      status: String            // "pending", "running", "completed", "failed"
    }
  ]
}
```

## 🧪 Testing with Postman

1. Import the Postman collection: `Vulnerability_Detector_API.postman_collection.json`
2. Set the `base_url` variable to `http://localhost:8000`
3. Run the requests in order:
   - Register User
   - Login (automatically saves token)
   - Get User Info
   - Start Network Scan
   - Get Scan History
   - Get Scan Detail

## 🛠️ Development

### Running Tests
```powershell
# Install test dependencies
pip install pytest pytest-asyncio httpx

# Run tests
pytest
```

### Code Formatting
```powershell
# Install formatters
pip install black isort

# Format code
black app/
isort app/
```

### Linting
```powershell
# Install linters
pip install flake8 mypy

# Run linters
flake8 app/
mypy app/
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Default | Required |
|----------|-------------|---------|----------|
| `MONGODB_URL` | MongoDB connection string with credentials | `mongodb://localhost:27017/skyscan` | ✅ |
| `SECRET_KEY` | JWT secret key (min 32 chars) | *Random generated* | ✅ |
| `DATABASE_NAME` | Database name | `skyscan` | ❌ |
| `ALGORITHM` | JWT signing algorithm | `HS256` | ❌ |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | JWT token expiration | `30` | ❌ |
| `PORT` | Application port (Railway uses this) | `8000` | ❌ |

### Security Best Practices
- **Never commit `.env`** to version control
- **Use strong SECRET_KEY**: Generate with `openssl rand -hex 32`
- **Production MongoDB**: Use authenticated connection strings with TLS
- **Railway deployment**: Store secrets in environment variables, not code

## 🧪 Testing

### Manual Testing
Use Postman collection: `Vulnerability_Detector_API.postman_collection.json`

1. Import collection into Postman
2. Set `base_url` variable to `http://localhost:8000` or production URL
3. Run requests:
   - `POST /api/auth/register` - Create account
   - `POST /api/auth/login` - Get token (auto-saved)
   - `GET /api/users/me` - Verify authentication
   - `POST /api/scan/network` - Run network scan
   - `GET /api/users/me/scans` - View scan history

### API Testing Script
```powershell
python test_scanner.py
```

## 📈 Architecture

**SkyScan** uses a modern, scalable architecture:

```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│  Frontend   │─────▶│   FastAPI    │─────▶│  MongoDB    │
│  (HTML/JS)  │      │   Backend    │      │  (Railway)  │
└─────────────┘      └──────────────┘      └─────────────┘
                            │
                            ▼
                     ┌──────────────┐
                     │    Nmap      │
                     │   Scanner    │
                     └──────────────┘
```

**Technology Stack:**
- **Backend**: FastAPI 0.115 (async Python 3.13)
- **Authentication**: JWT with bcrypt password hashing
- **Database**: MongoDB with Motor (async driver)
- **Scanning Engine**: Nmap with subprocess integration
- **Deployment**: Docker + Railway PaaS
- **Frontend**: Vanilla JavaScript with modern CSS

## 🤝 Contributing

Contributions welcome! Please follow these guidelines:

1. **Fork repository** and create feature branch
2. **Follow code style**: Use Black formatter and isort
3. **Add tests** for new features
4. **Update documentation** for API changes
5. **Submit pull request** with clear description

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- **Nmap Project** for the powerful network scanning engine
- **FastAPI** for the excellent async Python framework
- **Railway** for seamless deployment platform
- **MongoDB** for flexible document storage

## 📞 Support

- **Live Demo**: [skyscan-production.up.railway.app](https://skyscan-production.up.railway.app)
- **GitHub Issues**: [github.com/kaizer2nd/skyscan/issues](https://github.com/kaizer2nd/skyscan/issues)
- **Documentation**: See `/docs` endpoint on running instance

---

**Built with ❤️ for cybersecurity professionals**
- ✅ Input validation with Pydantic
- ✅ SQL injection protection (NoSQL)
- ✅ Rate limiting ready (can be added)

## 🚨 Important Notes

### Windows Compatibility
- **Nmap**: Must be installed and in system PATH
- **MongoDB**: Can run as Windows service or manually
- **PowerShell**: Use PowerShell (not CMD) for better compatibility
- **Firewall**: May need to allow MongoDB (port 27017) and FastAPI (port 8000)

### Production Deployment
Before deploying to production:

1. **Change SECRET_KEY** to a strong random value
2. **Configure CORS** to specific origins
3. **Enable HTTPS** with reverse proxy (nginx/IIS)
4. **Set up MongoDB authentication**
5. **Configure firewall rules**
6. **Enable rate limiting**
7. **Set up monitoring** (logs, metrics)
8. **Regular CVE database updates**

## 📝 API Documentation

Once the application is running, access:
- **Interactive API Docs (Swagger)**: http://localhost:8000/docs
- **Alternative Docs (ReDoc)**: http://localhost:8000/redoc

## 🤝 Contributing

This is a MIT Mini Project. For improvements:
1. Fork the repository
2. Create feature branch
3. Make changes
4. Submit pull request

## 📜 License

MIT License - See LICENSE file for details

## 👥 Team

**MIT Mini Project - Cybersecurity: Vulnerability Detector**

- **Rakshit** - PRN 071
- **Meghraj** - PRN 237
- **Bhargav** - PRN 354
- **Mohak** - PRN 240

Institution: MITAOE

## 🔗 Resources

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [Python-Nmap Documentation](https://pypi.org/project/python-nmap/)
- [CVE Database](https://cve.mitre.org/)
- [CVSS Scoring Guide](https://www.first.org/cvss/)

## 📞 Support

For issues or questions:
1. Check the API documentation at `/docs`
2. Review this README
3. Check MongoDB and Nmap installation
4. Verify firewall settings
5. Check application logs

## 🎯 Next Steps

After installation:
1. ✅ Register a new user account
2. ✅ Login to the dashboard
3. ✅ Run your first vulnerability scan
4. ✅ Review the scan results
5. ✅ Download detailed reports
6. ✅ Test with Postman collection

---

**Built with ❤️ for Cybersecurity**
