# Deployment Guide

## Local Development to GitHub

Since Git is not available in the WebContainer environment, follow these steps to deploy your code:

### Step 1: Download the Project
1. Download all project files from the WebContainer
2. Extract them to your local machine

### Step 2: Prepare Local Repository
```bash
# Navigate to your project directory
cd your-project-directory

# Initialize Git (if not already done)
git init

# Add all files
git add .

# Commit with your message
git commit -m "Updates"

# Add your GitHub repository as remote
git remote add origin https://github.com/yourusername/your-repo-name.git

# Push to GitHub
git push -u origin main
```

### Step 3: Environment Setup
Create a `.env` file in the backend directory:
```env
MONGO_URI=your-mongodb-connection-string
JWT_SECRET=your-jwt-secret-key
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-gmail-app-password
PORT=5000
```

### Step 4: Production Deployment

#### Backend Deployment (Heroku/Railway/Render)
1. Create account on your preferred platform
2. Connect your GitHub repository
3. Set environment variables in the platform dashboard
4. Deploy the backend service

#### Frontend Deployment (Netlify/Vercel)
1. Build the frontend:
```bash
cd frontend
npm run build
```
2. Deploy the `dist` folder to your preferred platform
3. Update API URLs to point to your deployed backend

### Step 5: Database Setup
1. Set up MongoDB Atlas or your preferred database service
2. Update the `MONGO_URI` in your environment variables
3. Create an admin user in the database

### Step 6: Email Configuration
1. Enable 2FA on your Gmail account
2. Generate an App Password
3. Use the App Password in your `EMAIL_PASS` environment variable

## Quick Commands Reference

```bash
# Clone repository
git clone https://github.com/yourusername/your-repo-name.git

# Install backend dependencies
cd backend && npm install

# Install frontend dependencies  
cd frontend && npm install

# Start backend development server
cd backend && npm run dev

# Start frontend development server
cd frontend && npm run dev

# Build for production
cd frontend && npm run build

# Commit and push changes
git add .
git commit -m "Your commit message"
git push origin main
```

## Troubleshooting

- **MongoDB Connection**: Ensure your MongoDB URI is correct and accessible
- **Email Issues**: Verify Gmail App Password and 2FA settings
- **CORS Errors**: Update frontend API URLs to match your backend deployment
- **File Uploads**: Ensure uploads directory exists and has proper permissions