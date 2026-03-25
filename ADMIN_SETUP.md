# Admin Setup Guide

## Creating an Admin Account

To access the admin dashboard, you need to create an admin user account in Supabase:

### Option 1: Using Supabase Dashboard (Recommended)

1. Go to your Supabase project dashboard
2. Navigate to **Authentication** > **Users**
3. Click **Add User** (or **Invite User**)
4. Enter the email address and password for the admin account
5. Click **Create User**

### Option 2: Using SQL (Advanced)

You can also create a user directly using SQL in the Supabase SQL Editor:

```sql
-- This will create a user with email and password
-- You'll need to set the actual encrypted password via the Supabase dashboard
INSERT INTO auth.users (email, encrypted_password, email_confirmed_at, created_at, updated_at)
VALUES ('admin@example.com', crypt('your_password_here', gen_salt('bf')), NOW(), NOW(), NOW());
```

**Note:** For security reasons, it's recommended to use the Supabase Dashboard to create users.

## Accessing the Admin Dashboard

1. Navigate to the login page at `/login`
2. Enter the email and password you created
3. Click **Sign In**
4. You'll be redirected to the admin dashboard at `/admin`

## Admin Features

Once logged in, you can manage:

- **Site Settings**: Customize site title, welcome message, colors, and fonts
- **Professor Info**: Update professor details, contact information, and academic identifiers
- **Members**: Add, edit, and delete current research group members
- **Alumni**: Manage alumni information
- **News**: Create and manage news updates and announcements
- **Outcomes**: Add patents, books, and book chapters
- **Images**: Upload and manage profile photos, group photos, backgrounds, and logos

## Image Management

- Click on the **Images** tab in the admin dashboard
- Use the upload buttons to select images from your computer
- Images are stored directly in the database
- Only one active image per type will be displayed on the public site
- Toggle the active status by clicking the "Set Active" button

## Security Notes

- Only authenticated users can access the admin dashboard
- All content management operations require authentication
- Public users can only view content, not edit it
- Always use a strong password for the admin account
- Consider enabling two-factor authentication in Supabase for added security
