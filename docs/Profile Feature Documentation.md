# User Profile Feature

## Overview
The user profile page allows authenticated users to view and modify their profile information including:

- Email address
- Bio/description
- Known keywords list
- Password (with current password verification)

## Backend Implementation

### Profile API Endpoint
- **GET** `/api/profile/` - Retrieve current user profile
- **PUT** `/api/profile/` - Update user profile

### Profile Model Fields
- `username` - Unique username (non-editable)
- `email` - User email address (editable, must be unique)
- `bio` - User biography/description (editable)
- `known_keywords` - JSON array of known keywords (editable)
- `password_hash` - Hashed password (editable with current password verification)

### Password Change
To change password, both `current_password` and `new_password` must be provided in the PUT request.

```json
{
  "current_password": "oldpassword",
  "new_password": "newpassword123"
}
```

### Known Keywords Management
Keywords are stored as a JSON array and are automatically:
- Trimmed of whitespace
- Converted to lowercase
- Deduplicated
- Filtered to remove empty strings

## Frontend Implementation

### Profile Page (`/profile`)
- **Location**: `/app/profile/page.tsx`
- **Authentication**: Redirects to login if not authenticated
- **Features**:
  - Form validation for email
  - Real-time keyword management (add/remove)
  - Modal for password change
  - Success/error notifications
  - Loading states

### Navigation
- Accessible via user menu in top navigation
- Added "Profile" menu item to existing user dropdown

### Key Components Used
- **Forms**: TextInput, Textarea, PasswordInput
- **UI**: Paper, Stack, Group, Badge, Modal, Alert
- **Icons**: Lucide React icons (Plus, X, Check, Edit)
- **Navigation**: Next.js router for navigation

## User Experience Features

1. **Keyword Management**:
   - Add keywords by typing and pressing Enter or clicking the plus button
   - Remove keywords by clicking the X on each badge
   - Duplicate prevention with user feedback
   - Visual feedback with badges

2. **Password Security**:
   - Separate modal for password changes
   - Current password verification required
   - Password confirmation field
   - Minimum password length validation

3. **Form Validation**:
   - Email format validation
   - Required field indicators
   - Real-time error feedback
   - Disabled submit buttons when invalid

4. **Visual Feedback**:
   - Loading states during API calls
   - Success/error alerts
   - Disabled states for invalid forms
   - Professional UI with Mantine components

## Usage

1. **Access Profile**: Click user menu → "Profile"
2. **Edit Information**: Modify any field and click "Update Profile"
3. **Manage Keywords**: Add keywords with the input field, remove with badge X buttons
4. **Change Password**: Click "Change Password" button, enter current and new passwords
5. **Navigate Back**: Use "Back" button to return to previous page

## API Integration

The profile page integrates with the existing authentication context (`useAuth`) and makes calls to:
- `authApi.updateProfile()` - For profile updates
- Authentication state management - For user data and login state

All API calls include proper error handling and user feedback.