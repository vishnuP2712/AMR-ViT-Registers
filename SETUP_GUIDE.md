# GitHub Setup Guide

This guide will help you upload your AMR-ViT project to GitHub.

## Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Fill in the details:
   - **Repository name**: `amr-vit-project` (or your preferred name)
   - **Description**: "Adaptive Multi-Register Vision Transformer for medical and natural image classification"
   - **Visibility**: Choose Public or Private
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
5. Click "Create repository"

## Step 2: Initialize Git in Your Project

Open your terminal and navigate to your project folder, then run:

```bash
cd amr-vit-project
git init
```

## Step 3: Add Your Files

```bash
git add .
git commit -m "Initial commit: AMR-ViT implementation with MedMNIST and CIFAR-10 experiments"
```

## Step 4: Connect to GitHub

Replace `yourusername` with your GitHub username:

```bash
git remote add origin https://github.com/yourusername/amr-vit-project.git
git branch -M main
git push -u origin main
```

## Step 5: Verify Upload

1. Go to your repository URL: `https://github.com/yourusername/amr-vit-project`
2. You should see all your files including:
   - README.md
   - AMR_ViT.ipynb
   - requirements.txt
   - LICENSE
   - .gitignore

## Optional: Add Topics/Tags

To make your repository more discoverable:

1. Go to your repository on GitHub
2. Click the gear icon next to "About"
3. Add relevant topics like:
   - `vision-transformer`
   - `deep-learning`
   - `medical-imaging`
   - `pytorch`
   - `attention-mechanism`
   - `cifar10`
   - `medmnist`

## Optional: Enable GitHub Pages

If you want to create a project website:

1. Go to Settings → Pages
2. Select source: Deploy from a branch
3. Select branch: main
4. Your site will be published at: `https://yourusername.github.io/amr-vit-project/`

## Troubleshooting

### Authentication Issues

If you encounter authentication problems, you may need to use a Personal Access Token (PAT):

1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token with `repo` scope
3. Use the token as your password when pushing

### Large Files

If you have large model checkpoints (`.pth` files), consider using Git LFS:

```bash
git lfs install
git lfs track "*.pth"
git add .gitattributes
```

## Next Steps

After uploading:

1. ✅ Add a nice repository banner/logo
2. ✅ Write detailed documentation
3. ✅ Add example outputs/visualizations
4. ✅ Create a CONTRIBUTING.md if accepting contributions
5. ✅ Set up GitHub Actions for CI/CD (optional)
6. ✅ Add badges to README (build status, license, etc.)

## Updating Your Repository

When you make changes:

```bash
git add .
git commit -m "Description of changes"
git push
```

---

Good luck with your project! 🚀
