# ChatApp - Modern Social Messaging Platform

A modern, feature-rich web application for connecting people with a dark theme UI, built with Python Flask.

## Features

✨ **User Authentication**
- User registration with email verification
- Secure login with "Remember Me" functionality
- Password hashing with Werkzeug security

🔐 **Human Verification**
- Human verification checkbox during registration
- Enhanced security for account creation

👥 **Friend Management**
- Find and search other users
- Send friend requests
- Accept/reject friend requests
- View friends list
- Remove friends
- Block/unblock users
- Blocked users list

💬 **Real-time Messaging**
- Private messaging between friends
- Message history
- Read/unread status
- Message timestamps

👤 **User Profiles**
- Custom user profiles
- User bio and information
- Online/offline status
- Last seen information
- Profile picture avatars

🎨 **Modern Dark Theme UI**
- Sleek dark mode interface
- Responsive design for all devices
- Smooth animations and transitions
- Bootstrap 5 framework
- FontAwesome icons

📱 **Responsive Design**
- Mobile-friendly interface
- Tablet optimized
- Desktop experiences

## Technology Stack

- **Backend**: Python Flask
- **Database**: SQLite (SQLAlchemy ORM)
- **Authentication**: Flask-Login
- **Frontend**: Bootstrap 5, HTML5, CSS3, JavaScript
- **Icons**: FontAwesome 6

## Installation

### Prerequisites
- Python 3.8+
- pip (Python package manager)

### Setup Instructions

1. **Clone or download the project**
   ```bash
   cd d:\projects\project01
   ```

2. **Create a virtual environment (optional but recommended)**
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Access the application**
   - Open your browser and navigate to: `http://localhost:5000`

## Default Routes

- `/` - Home (redirects to login)
- `/register` - User registration
- `/login` - User login
- `/dashboard` - Main dashboard
- `/profile` - Your profile
- `/user/<user_id>` - Other user's profile
- `/find-friends` - Find and add friends
- `/chat` - Messages inbox
- `/chat/<user_id>` - Chat with specific user
- `/blocked-users` - View blocked users
- `/logout` - Logout

## API Endpoints

### Friend Management
- `POST /friend-request/<user_id>` - Send friend request
- `POST /friend-request/<request_id>/accept` - Accept request
- `POST /friend-request/<request_id>/reject` - Reject request
- `POST /remove-friend/<user_id>` - Remove friend

### Blocking
- `POST /block-user/<user_id>` - Block user
- `POST /unblock-user/<user_id>` - Unblock user

### Messaging
- `POST /api/send-message/<user_id>` - Send message
- `GET /api/messages/<user_id>` - Get messages

## Database Schema

### Users Table
- `id` - UUID (Primary Key)
- `username` - Unique username
- `email` - Unique email
- `password_hash` - Hashed password
- `full_name` - User's full name
- `bio` - User biography
- `profile_pic` - Profile picture URL
- `is_verified` - Verification status
- `is_online` - Online status
- `created_at` - Account creation timestamp
- `last_seen` - Last activity timestamp

### Other Tables
- **FriendRequest** - Friend request management
- **Friendship** - Active friendships
- **BlockList** - Blocked users
- **Message** - Chat messages

## Configuration

Edit `config.py` to customize:
- Database URI
- Secret key (IMPORTANT: Change in production)
- Max file upload size
- Allowed file extensions

## Security Notes

⚠️ **Important for Production:**
1. Change the `SECRET_KEY` in `config.py`
2. Use a proper database (PostgreSQL, MySQL)
3. Enable HTTPS
4. Set `DEBUG = False`
5. Use environment variables for sensitive config
6. Implement proper email verification
7. Add rate limiting
8. Use CSRF protection

## How to Use

### Creating an Account
1. Click "Register" on the login page
2. Enter username, email, and password
3. Check the "I am human" verification box
4. Submit to create account

### Adding Friends
1. Go to "Find Friends" page
2. Search for users by username or name
3. Click "Add Friend" to send request
4. User receives notification on dashboard

### Messaging Friends
1. Go to "Messages" page
2. Click on a friend to open chat
3. Type messages and click Send
4. Messages appear in real-time

### Blocking Users
1. Visit user's profile
2. Click "Block User" button
3. Blocked user cannot see your profile or message you

## Troubleshooting

**Database Issues**
- Delete `chatapp.db` to reset database
- Make sure the `static/uploads` folder exists

**Port Already in Use**
- Change port in `app.py`: `app.run(port=5001)`

**Login Issues**
- Verify username and password are correct
- Check database is initialized

## Future Enhancements

- 🔔 Real-time notifications
- 📸 Image/file sharing
- 👁️ User typing indicators
- 💬 Group chats
- 🎵 Voice/video calls
- 📍 User location sharing
- ⭐ User ratings/reviews
- 🎭 User presence detection

Scaffolding added:

- A lightweight set of blueprint placeholders was added under `scaffolds/` to help prototype these features quickly:
   - `scaffolds/notifications.py` — notifications endpoints (placeholder)
   - `scaffolds/file_sharing.py` — file upload placeholder
   - `scaffolds/typing.py` — typing indicator placeholder
   - `scaffolds/group_chat.py` — group chat placeholder
   - `scaffolds/calls.py` — voice/video calls placeholder
   - `scaffolds/location.py` — location-sharing placeholder
   - `scaffolds/ratings.py` — ratings/reviews placeholder
   - `scaffolds/presence.py` — simple presence/heartbeat endpoint

These blueprints are automatically discovered and registered by the app at startup. They are intentionally minimal and return JSON messages so you can incrementally replace the placeholders with real implementations (WebSocket support, database models, storage integrations, etc.).

## Contributing

Feel free to fork and submit pull requests.

## License

This project is open source and available for educational purposes.

## Support

For issues or questions, please create an issue in the project repository.

---

**Happy Chatting! 💬**
