# Project Setup Guide

## Environment Variables Setup

To run this project, you need to create a `.env.local` file in the root directory with the following environment variables:

```env
# Sanity Configuration
NEXT_PUBLIC_SANITY_PROJECT_ID=your_sanity_project_id_here
NEXT_PUBLIC_SANITY_DATASET=production
NEXT_PUBLIC_SANITY_API_VERSION=2024-11-02
SANITY_WRITE_TOKEN=your_sanity_write_token_here

# NextAuth Configuration
AUTH_SECRET=your_auth_secret_here
AUTH_GITHUB_ID=your_github_oauth_app_id_here
AUTH_GITHUB_SECRET=your_github_oauth_app_secret_here
```

## How to Get These Values:

### 1. Sanity Configuration
1. Go to [sanity.io](https://www.sanity.io/) and create an account
2. Create a new project
3. Get your Project ID from the project settings
4. Create a dataset (usually "production")
5. Generate a write token in the API section

### 2. GitHub OAuth App
1. Go to GitHub Settings > Developer settings > OAuth Apps
2. Create a new OAuth App
3. Set the callback URL to `http://localhost:3000/api/auth/callback/github`
4. Copy the Client ID and Client Secret

### 3. Auth Secret
Generate a random string for AUTH_SECRET (you can use `openssl rand -base64 32`)

## Running the Project

After setting up the environment variables:

```bash
pnpm dev
```

The project should now run successfully at http://localhost:3000 
