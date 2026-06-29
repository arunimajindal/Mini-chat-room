# 💬 Mini Chat Room

A lightweight Python implementation of a chat room system using Object-Oriented Programming. Models users, messages, and chat rooms with join/leave/broadcast functionality — all in-memory, no external libraries needed.

## 🧠 Concepts Demonstrated

- OOP with multiple interacting classes
- Instance methods and state management
- Class-level variables (auto-incrementing message IDs)
- Encapsulation of chat room logic
- Guard clauses for invalid actions (e.g. messaging without joining)

## 🏗️ Class Structure

### `User`
Represents a participant in the chat.

| Method | Description |
|---|---|
| `join_chatroom(chatroom)` | Joins a chatroom — a user can only be in one at a time |
| `leave_chatroom()` | Leaves the current chatroom and clears the reference |
| `send_message(content)` | Broadcasts a message; blocked if not in a room |

### `Chatroom`
The shared space where users interact.

| Method | Description |
|---|---|
| `add_user(user)` | Adds a user to the room's user list |
| `remove_user(user)` | Removes a user from the room |
| `broadcast(sender, content)` | Creates a `Message`, stores it, and prints it |
| `show_chat_history()` | Prints all messages sent in the room |

### `Message`
Represents a single chat message with an auto-incrementing global ID.

| Attribute | Description |
|---|---|
| `id` | Unique message ID via class-level `message_counter` |
| `sender` | The `User` object who sent it |
| `content` | Message text |

## 🚀 Getting Started

No dependencies, no installs — pure Python.

```bash
git clone https://github.com/arunimajindal/Mini-chat-room.git
cd Mini-chat-room
python code.py
```

## 📟 Sample Output

```
Alice joined Python lounge
Bob joined Python lounge
(1) Alice : Hello everyone
(2) Bob : Hello alice
charlie joined Python lounge
(3) charlie : helloo

Chat History of Python lounge :
(1) Alice : Hello everyone
(2) Bob : Hello alice
(3) charlie : helloo

Alice left Python lounge
Bob left Python lounge
charlie left Python lounge
```

## 📁 Project Structure

```
Mini-chat-room/
├── code.py    # All classes + demo usage
└── README.md
```

## 🔧 Ideas to Extend

- Support multiple rooms per user simultaneously
- Add private messaging between two users
- Persist chat history to a `.txt` or `.json` file
- Add timestamps to each message
- Build a real-time networked version using Python's `socket` module
