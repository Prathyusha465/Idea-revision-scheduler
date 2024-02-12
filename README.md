# Idea-revision-scheduler

FEATURES:
User Authentication: Secure user authentication and registration system.
Revision Management: Create, edit, and delete your revision topics.
Recipe Discovery: Browse and search for revision topics shared by other users.
Responsive Design: Works seamlessly on both desktop and mobile devices.

ROUTES:
  * Auth :
         /api/auth/register: Register a new user.
         /api/auth/login: Login an existing user.
         /api/auth/logout: Logout the currently authenticated user.
 * User profile:
        /api/profile/me : Get the profile of the currently authenticated user.
        /api/profile/update : Update the profile information of the user.
 * Revision :
        /api/schedule: Get the revision schedule for the user.
        /api/schedule/add: Add a new revision task to the schedule.
        /api/schedule/edit/:taskId: Edit an existing revision task.
        /api/schedule/delete/:taskId: Delete a revision task from the schedule.

SCHEMA :
  * User :
         User Schema:
javascript
Copy code
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  username: {
    type: String,
    required: true,
    unique: true
  },
  email: {
    type: String,
    required: true,
    unique: true
  },
  password: {
    type: String,
    required: true
  },
  // Additional fields like name, profile picture, etc.
}, { timestamps: true });

module.exports = mongoose.model('User', userSchema);

