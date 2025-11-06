[README.md](https://github.com/user-attachments/files/23386687/README.md)
# 🎓 College ID Fine Management System

A professional desktop GUI application built with Python Tkinter for managing college ID card fines and payments digitally.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Overview

This is a comprehensive desktop application designed for colleges to manage student ID card violations and fines efficiently. The system implements a **3-strike fine system** where fines escalate with each violation within a month.

### ✨ Key Features

- **Student Registration** - Register students with roll number, name, email, contact, and ID card photo
- **QR Code Generation** - Generate payment QR codes with unique tokens
- **Payment Verification** - Token-based secure payment confirmation system
- **Admin Dashboard** - Complete overview with statistics and pending payments
- **Receipt Generation** - Automatic PDF receipt generation after payment
- **3-Strike System** - Progressive fine amounts (₹50 → ₹100 → ₹150)
- **Time-Limited Tokens** - Payment tokens expire after 10 minutes
- **Monthly Limit** - Maximum 3 violations per student per month

## 🛠️ Tech Stack

- **Language:** Python 3.8+
- **GUI Framework:** Tkinter
- **Libraries Used:**
  - `qrcode` - QR code generation
  - `json` - Data storage
  - `datetime` - Time management
  - `pathlib` - File operations
  - `re` - Input validation

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Setup Instructions

1. **Clone or download the repository**
```bash
cd college-fine-management
```

2. **Install required dependencies**
```bash
pip install qrcode[pil]
```

3. **Run the application**
```bash
python gui_app.py
```

## 🚀 Usage

### 1. Register Student
- Enter roll number (Format: F089, S102, or T145)
- Fill in name, email, and contact details
- Optionally upload college ID card photo
- Click "Register Student"

### 2. Generate QR Code
- Enter student's roll number
- System automatically calculates fine based on attempts
- Generates QR code with unique token
- Token valid for 10 minutes

### 3. Confirm Payment
- Enter roll number and payment token
- Optionally add transaction ID
- System verifies token and confirms payment
- Receipt is automatically generated

### 4. Admin Panel (Password: `admin123`)
- View system statistics
- See all registered students
- Monitor pending payments
- Track revenue and violations

## 📁 Project Structure

```
college-fine-management/
│
├── gui_app.py              # Main application file
├── data.json               # Student database (auto-created)
│
├── qr_codes/               # Generated QR codes
├── receipts/               # Payment receipts
└── uploads/                # Student ID card uploads
```

## ⚙️ Configuration

You can modify these settings at the top of `gui_app.py`:

```python
ADMIN_PASSWORD = "admin123"           # Admin panel password
TOKEN_TTL_MINUTES = 10                # Token validity time
FINE_AMOUNTS = {1: 50, 2: 100, 3: 150}  # Fine amounts for strikes 1, 2, 3
MAX_ATTEMPTS_PER_MONTH = 3            # Maximum violations per month
```

## 🎯 Fine System

| Attempt | Fine Amount | Description |
|---------|-------------|-------------|
| 1st     | ₹50         | First violation of the month |
| 2nd     | ₹100        | Second violation |
| 3rd     | ₹150        | Third and final violation |
| 4th+    | Blocked     | No more attempts allowed |

## 📸 Screenshots

### Main Menu
Clean and intuitive main interface with all options.

### Student Registration
Simple form with validation for roll number, email, and contact.

### Admin Dashboard
Comprehensive statistics with tabs for users and pending payments.

## 🔒 Security Features

- Token-based payment verification
- Time-limited QR codes (10 minutes)
- Password-protected admin panel
- Input validation for all fields
- Unique payment IDs for each transaction

## 📝 Roll Number Format

The system accepts roll numbers in the following format:
- **F089** - First Year students (F + 3 digits)
- **S102** - Second Year students (S + 3 digits)
- **T145** - Third Year students (T + 3 digits)

## 🐛 Troubleshooting

**QR Code not generating?**
- Make sure `qrcode` library is installed: `pip install qrcode[pil]`

**Window not centered?**
- Application automatically centers on screen launch

**Data not saving?**
- Check write permissions in the application directory

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is open-source and available under the MIT License.

## 👨‍💻 Author

**Suraj Jaiswal**

Developed with ❤️ for college administration

## 📞 Support

For issues or questions:
- Create an issue in the repository
- Contact the developer

---

**Note:** This is a demonstration project. For production use, consider adding:
- Database integration (SQLite/MySQL)
- Encrypted password storage
- Cloud backup system
- Email notifications
- SMS integration for payment confirmations
