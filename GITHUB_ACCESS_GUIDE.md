# How to Give Git Write Access to Another User on GitHub

## 📋 Prerequisites
- You must be the **owner** or **admin** of the repository
- The other user must have a GitHub account

## 🚀 Steps to Grant Write Access

### Method 1: Add as Collaborator (Recommended)

1. **Go to Your Repository**
   - Navigate to: `https://github.com/dhanajack/maestro`

2. **Open Settings**
   - Click on **"Settings"** tab at the top of the repository
   - (You need to be the owner/admin to see this tab)

3. **Access Collaborators**
   - In the left sidebar, click **"Collaborators and teams"** or just **"Collaborators"**
   - You may be asked to enter your GitHub password for security

4. **Add Collaborator**
   - Click the **"Add people"** button (green button)
   - Enter the GitHub username, full name, or email of the person
   - Select the correct user from the dropdown

5. **Choose Permission Level**
   - Select **"Write"** permission level
   - Options available:
     - **Read**: Can pull and view code
     - **Write**: Can push to the repository ✅ (Choose this)
     - **Admin**: Full access including settings

6. **Send Invitation**
   - Click **"Add [username] to this repository"**
   - The user will receive an email invitation

7. **User Accepts Invitation**
   - The invited user must:
     - Check their email
     - Click the invitation link
     - Accept the invitation on GitHub

## 🔐 Permission Levels Explained

| Permission | Can Read | Can Write/Push | Can Merge PRs | Can Change Settings |
|------------|----------|----------------|---------------|---------------------|
| **Read**   | ✅       | ❌             | ❌            | ❌                  |
| **Write**  | ✅       | ✅             | ✅            | ❌                  |
| **Admin**  | ✅       | ✅             | ✅            | ✅                  |

## 📱 Alternative Methods

### Method 2: Create a Team (For Organizations)

If your repository is under an organization:

1. Go to **Organization Settings** → **Teams**
2. Create a new team or select existing team
3. Add members to the team
4. Add the team to the repository with **Write** access

### Method 3: Make Repository Public with Fork & PR Model

1. Make repository public (Settings → General → Danger Zone)
2. Users can fork and submit Pull Requests
3. You review and merge their changes
4. **No write access needed** (more secure for open source)

## 🔗 Quick Access URLs

For your repository `maestro`:
- **Settings**: `https://github.com/dhanajack/maestro/settings`
- **Collaborators**: `https://github.com/dhanajack/maestro/settings/access`
- **Invitations**: `https://github.com/dhanajack/maestro/invitations`

## ✅ Verify Access

After adding collaborator, they can verify by:

```bash
# Clone the repository
git clone https://github.com/dhanajack/maestro.git

# Make changes and try to push
git add .
git commit -m "Test commit"
git push origin main
```

If they can push without errors, write access is working!

## 🔒 Security Best Practices

1. **Only grant write access to trusted users**
2. **Use branch protection rules**:
   - Settings → Branches → Add rule
   - Require pull request reviews before merging
   - Require status checks to pass

3. **Enable two-factor authentication** for your GitHub account

4. **Review collaborators regularly** and remove those who no longer need access

## 🚫 Removing Access

To remove a collaborator:
1. Go to **Settings** → **Collaborators**
2. Find the user
3. Click **"Remove"** button next to their name

## 📝 Notes

- Collaborators can push directly to **all branches** (unless protected)
- They **cannot** delete the repository or change settings (unless Admin)
- They **can** create, edit, and delete issues and pull requests
- They **can** merge pull requests
- **Free GitHub accounts** have unlimited collaborators for public repositories
- **Private repositories** on free accounts are limited to 3 collaborators

## 🆘 Troubleshooting

**"I don't see the Settings tab"**
- You're not the owner/admin of the repository
- Contact the repository owner

**"User didn't receive invitation"**
- Check spam folder
- Verify the username/email is correct
- User can check: `https://github.com/dhanajack/maestro/invitations`

**"User can't push even after accepting"**
- Ensure they accepted the invitation
- Check if branch is protected
- Verify they're using the correct credentials
- Try re-adding them as collaborator

---

## 🎯 Summary for Your Repository

**Repository**: `dhanajack/maestro`

**Quick Steps**:
1. Go to: https://github.com/dhanajack/maestro/settings/access
2. Click "Add people"
3. Enter their GitHub username
4. Select "Write" permission
5. Click "Add to repository"
6. They accept the email invitation
7. Done! ✅
