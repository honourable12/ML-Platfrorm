# 🚀 ML Platform

A full-stack machine learning platform that empowers users to upload datasets, train ML models, make predictions, and visualize results—all through an intuitive web interface.

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115-green?logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18.3-61dafb?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178c6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-06b6d4?logo=tailwindcss&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

---

## ✨ Features

### 🔐 Authentication & Security

- **User Authentication** - Secure JWT-based authentication with bcrypt password hashing
- **Role-based Access Control** - Protected routes and user-specific data isolation
- **Session Management** - Automatic token refresh and secure logout

### 📊 Dataset Management

- **Upload & Store** - Easily upload CSV datasets and store them securely
- **Data Visualization** - Interactive charts and statistical summaries
- **Data Cleaning** - Multiple data preprocessing operations:
  - Handle missing values (drop, fill, forward/backward fill)
  - Remove duplicates
  - Convert column types
  - Outlier detection and removal
- **Data Exploration** - View dataset shape, columns, data types, and missing value analysis

### 🤖 ML Model Training

- **Multiple Algorithms** - Support for classification and regression models:
  - Linear Regression
  - Logistic Regression
  - Decision Trees
  - Random Forests
  - Support Vector Machines (SVM)
- **Flexible Training** - Configure train/test split and model hyperparameters
- **Model Persistence** - Save and load trained models for later use
- **Training History** - Track all trained models and their performance metrics

### 🔮 Predictions & Analysis

- **Make Predictions** - Use trained models to generate predictions on new data
- **Prediction History** - Track all predictions with timestamps and accuracy metrics
- **Batch Processing** - Process multiple predictions efficiently
- **Export Results** - Download prediction results as CSV files

### 📈 Dashboard & Analytics

- **Real-time Metrics** - View model performance, accuracy, and precision scores
- **Visual Analytics** - Interactive charts for data and model insights
- **User Profile** - Manage account settings and view personal statistics

---

## 🏗️ Project Structure

```
ml_trainer/
├── frontend/                 # React + TypeScript Frontend
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   │   ├── datasets/    # Dataset upload & management
│   │   │   ├── models/      # Model training & prediction
│   │   │   └── ui/          # Shared UI components
│   │   ├── pages/           # Page components
│   │   ├── services/        # API integration
│   │   ├── contexts/        # React context for state management
│   │   └── utils/           # Utility functions
│   ├── package.json
│   ├── tailwind.config.js   # Tailwind CSS configuration
│   ├── vite.config.ts       # Vite build configuration
│   └── tsconfig.json        # TypeScript configuration
│
├── model_api/               # FastAPI Backend
│   ├── app.py              # Main FastAPI application
│   ├── config.py           # Configuration settings
│   ├── database.py         # Database models and ORM
│   ├── requirements.txt    # Python dependencies
│   └── tests/              # Test suite
│
└── notes.txt               # Project documentation
```

---

## 🚀 Quick Start

### Prerequisites

- **Python** 3.12+
- **Node.js** 18+ & npm
- **SQLite** (included with Python)

### Backend Setup

1. **Navigate to the backend directory:**

   ```bash
   cd model_api
   ```

2. **Create and activate a virtual environment:**

   ```bash
   python -m venv mlplat
   mlplat\Scripts\Activate.ps1  # On Windows PowerShell
   # or
   source mlplat/bin/activate   # On macOS/Linux
   ```

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the backend server:**

   ```bash
   python app.py
   # or with uvicorn
   uvicorn app:app --reload --host 0.0.0.0 --port 8000
   ```

   The API will be available at `http://localhost:8000`

### Frontend Setup

1. **Navigate to the frontend directory:**

   ```bash
   cd frontend
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Start the development server:**

   ```bash
   npm run dev
   ```

   The application will be available at `http://localhost:5173`

---

## 📡 API Endpoints

### Authentication

- `POST /register` - Create a new user account
- `POST /login` - Login and receive JWT token
- `POST /token` - Get access token

### Datasets

- `POST /upload_dataset` - Upload a new CSV dataset
- `GET /datasets` - List all user datasets
- `GET /datasets/{dataset_id}` - Get specific dataset details
- `GET /visualize_dataset/{dataset_id}` - Get dataset statistics and visualization data
- `POST /clean_dataset/{dataset_id}` - Apply data cleaning operations
- `DELETE /datasets/{dataset_id}` - Delete a dataset

### Models

- `POST /train_model` - Train a new ML model
- `GET /models` - List all trained models
- `GET /models/{model_id}` - Get model details
- `GET /models/{model_id}/accuracy` - Get model performance metrics
- `DELETE /models/{model_id}` - Delete a model

### Predictions

- `POST /predict` - Make predictions using a trained model
- `GET /predictions` - Get prediction history
- `GET /predictions/{prediction_id}` - Get specific prediction details
- `DELETE /predictions/{prediction_id}` - Delete a prediction record

### User

- `GET /user/profile` - Get current user profile
- `PUT /user/profile` - Update user profile

---

## 🛠️ Technology Stack

### Backend

- **FastAPI** - Modern, fast web framework for building APIs
- **SQLAlchemy** - SQL toolkit and ORM
- **Pandas** - Data manipulation and analysis
- **scikit-learn** - Machine learning algorithms
- **NumPy** - Numerical computing
- **PyJWT** - JWT token management
- **Bcrypt** - Password hashing

### Frontend

- **React** - UI library
- **TypeScript** - Type-safe JavaScript
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **Tailwind CSS** - Utility-first CSS framework
- **Lucide React** - Icon library
- **Recharts** - Chart library
- **React Hook Form** - Form state management

---

## 🧪 Testing

Run the test suite:

```bash
cd model_api
pytest tests/
# or run specific test file
pytest tests/test_ml_models_comprehensive.py
```

---

## 🔒 Security Features

- **JWT Authentication** - Secure token-based authentication
- **Password Hashing** - bcrypt for secure password storage
- **CORS Protection** - Configured to allow specific origins
- **SQL Injection Prevention** - SQLAlchemy parameterized queries
- **User Data Isolation** - Each user only accesses their own data

---

## 📝 Environment Variables

Create a `.env` file in the `model_api` directory:

```env
DATABASE_URL=sqlite:///./ml_platform.db
JWT_SECRET_KEY=your-secret-key-here
JWT_ALGORITHM=HS256
JWT_ACCESS_TOKEN_EXPIRE_MINUTES=30
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🎯 Roadmap

- [ ] Add more ML algorithms (XGBoost, Neural Networks)
- [ ] Implement model evaluation metrics dashboard
- [ ] Add real-time model training progress tracking
- [ ] Support for different file formats (Excel, Parquet, etc.)
- [ ] API rate limiting and usage analytics
- [ ] Model versioning and rollback
- [ ] Automated data preprocessing suggestions
- [ ] Integration with popular ML frameworks (TensorFlow, PyTorch)

---

## 📞 Support

For issues, questions, or suggestions, please open an issue on GitHub or contact the development team.

---

## 🌟 Acknowledgments

Built with ❤️ using FastAPI, React, and the amazing Python/JavaScript ecosystem.

---

<div align="center">

**[↑ back to top](#-ml-platform)**

Made with 💡 for machine learning enthusiasts

</div>
