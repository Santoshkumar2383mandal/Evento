# Vercel Deployment Guide

This guide will help you deploy both the frontend and backend of the Event Management System to Vercel.

## Prerequisites

1. A Vercel account (sign up at https://vercel.com)
2. MongoDB Atlas account (for cloud database) or your MongoDB connection string
3. GitHub repository: https://github.com/Santoshkumar2383mandal/Evento

## Deployment Steps

### Step 1: Deploy Backend (API)

1. **Go to Vercel Dashboard** → Click "Add New Project"
2. **Import your GitHub repository**: `Santoshkumar2383mandal/Evento`
3. **Configure the project**:
   - **Root Directory**: Select `api` folder
   - **Framework Preset**: Other
   - **Build Command**: Leave empty (or `npm install`)
   - **Output Directory**: Leave empty
   - **Install Command**: `npm install`

4. **Environment Variables** (Add these in Vercel project settings):
   ```
   MONGO_URL=your_mongodb_connection_string
   JWT_SECRET=your-secret-key-here
   FRONTEND_URL=https://your-frontend-url.vercel.app
   NODE_ENV=production
   ```

5. **Deploy** → Click "Deploy"

6. **Note your backend URL**: After deployment, you'll get a URL like `https://your-api.vercel.app`

### Step 2: Deploy Frontend (Client)

1. **Go to Vercel Dashboard** → Click "Add New Project"
2. **Import the same GitHub repository**: `Santoshkumar2383mandal/Evento`
3. **Configure the project**:
   - **Root Directory**: Select `client` folder
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build` (auto-detected)
   - **Output Directory**: `dist` (auto-detected)
   - **Install Command**: `npm install`

4. **Environment Variables** (Add these in Vercel project settings):
   ```
   VITE_API_URL=https://your-backend-api-url.vercel.app
   ```

5. **Deploy** → Click "Deploy"

6. **Note your frontend URL**: After deployment, you'll get a URL like `https://your-frontend.vercel.app`

### Step 3: Update Backend CORS

After deploying the frontend, update the backend environment variable:

1. Go to your **Backend project** in Vercel
2. Go to **Settings** → **Environment Variables**
3. Update `FRONTEND_URL` to your actual frontend Vercel URL
4. **Redeploy** the backend

### Step 4: Update Frontend API URL (if needed)

If you need to update the frontend API URL:

1. Go to your **Frontend project** in Vercel
2. Go to **Settings** → **Environment Variables**
3. Update `VITE_API_URL` to your actual backend Vercel URL
4. **Redeploy** the frontend

## Important Notes

### File Uploads
- The backend now stores images as base64 strings in MongoDB (compatible with Vercel serverless)
- For production with large files, consider using cloud storage (AWS S3, Cloudinary, etc.)

### MongoDB Connection
- Use MongoDB Atlas (free tier available) for cloud database
- Connection string format: `mongodb+srv://username:password@cluster.mongodb.net/database-name`

### Environment Variables Summary

**Backend (`api`):**
- `MONGO_URL` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT tokens
- `FRONTEND_URL` - Your frontend Vercel URL
- `NODE_ENV` - Set to `production`

**Frontend (`client`):**
- `VITE_API_URL` - Your backend Vercel URL

## Troubleshooting

1. **CORS Errors**: Make sure `FRONTEND_URL` in backend matches your frontend URL exactly
2. **API Not Found**: Check that `VITE_API_URL` in frontend is correct
3. **Database Connection**: Verify `MONGO_URL` is correct and MongoDB Atlas allows connections from anywhere (0.0.0.0/0)
4. **Build Errors**: Check Vercel build logs for specific error messages

## Testing

After deployment:
1. Visit your frontend URL
2. Try registering a new user
3. Create an event with an image
4. Verify all features work correctly

## Continuous Deployment

Vercel automatically deploys when you push to your GitHub repository's main branch. Each push will trigger a new deployment.

