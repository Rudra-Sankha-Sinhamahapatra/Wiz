# Wiz - WebSockets Chat App

## **Project Overview**
Wiz is a real-time chat application built using modern technologies to enable seamless communication in virtual chat rooms. Users can join specific rooms and exchange messages with others in real-time.

### **Frontend**
- **Frameworks and Libraries**:
  - **Next.js**: For server-side rendering and routing.
  - **React.js**: Core library for building the user interface.
  - **Tailwind CSS**: For responsive and modern styling.
  - **TypeScript**: For type safety and enhanced developer experience.

### **Backend**
- **Technologies**:
  - **Node.js**: Runtime environment for the server.
  - **WebSockets**: For real-time, bidirectional communication.
  - **TypeScript**: Ensures type safety and scalability.

---

## **Key Features**
1. **Room Concept**:
   - Users can navigate to the `/join` route to enter a room ID.
   - Multiple users can join the same room and chat together in real-time.

2. **Real-Time Messaging**:
   - Messages are instantly broadcasted to all users in the room using WebSockets.

3. **Unique Identifiers**:
   - Each **user** and **message** is assigned a unique ID using UUID (`v4`).
   - This ensures:
     - Messages sent by the current user are distinguishable from those sent by others.
     - Reliable state management and avoidance of duplicate messages.

---

## **Frontend Workflow**
1. **Joining a Room**:
   - Users input a `roomId` to connect to a specific chat room.
   - The room ID is passed to the backend via WebSocket messages to join the room.

2. **Sending Messages**:
   - Messages are typed into a text area and sent via the WebSocket connection.
   - Each message includes the sender's unique `userId`, the message content, and a `messageId` for tracking.

3. **Receiving Messages**:
   - The frontend listens for incoming WebSocket messages.
   - Messages are displayed in real-time in the chat window.

4. **UI Features**:
   - Messages from the current user are styled differently (e.g., aligned to the right with a blue background).
   - Opponent messages are styled distinctly (e.g., aligned to the left with a gray background).

---

## **Backend Workflow**
1. **WebSocket Connection**:
   - A WebSocket server is initialized to handle real-time communication.

2. **Room Management**:
   - When a user joins a room, the backend stores their connection under the specific `roomId`.
   - Messages are broadcasted only to users in the same room.

3. **Message Broadcasting**:
   - Upon receiving a message, the backend:
     - Verifies the room and user.
     - Broadcasts the message payload (including `userId` and `messageId`) to all connected clients in the room.

4. **Error Handling**:
   - Handles connection errors gracefully (e.g., connection drops, invalid payloads).

---

## **Technical Highlights**
1. **WebSocket Implementation**:
   - Lightweight, low-latency communication using WebSockets for real-time updates.

2. **UUID for Identifiers**:
   - Ensures uniqueness for users and messages.

3. **Scalable Architecture**:
   - TypeScript ensures the codebase is maintainable and scalable.
   - Tailwind CSS enables a responsive and consistent UI.

4. **Optimized State Management**:
   - Messages are added to the local state immediately after sending, ensuring a smooth user experience.
   - Duplicate messages are avoided using `messageId`.

---

## **Future Enhancements**
1. **Typing Indicators**:
   - Show when a user is typing in the room.

2. **Message Timestamps**:
   - Display timestamps for each message.

3. **Room Persistence**:
   - Store chat history in a database to allow users to view previous messages.

4. **User Avatars**:
   - Add profile pictures or avatars to identify users visually.

5. **Notifications**:
   - Notify users when someone joins or leaves a room.

---

## **Setup and Installation**
1. Clone the repository:
   ```bash
   git clone https://github.com/Rudra-Sankha-Sinhamahapatra/Wiz
   ```

2. Navigate to the project folder:
   ```bash
   cd Wiz
   ```

3. Install dependencies for both frontend and backend:
   ```bash
   npm install
   ```

4. Create a `.env` file in the root directory and add the WebSocket URL:
   ```env
   NEXT_PUBLIC_WS_URL=your-websocket-url
   ```

5. Start the development servers:
   - Frontend:
     ```bash
     npm run dev
     ```
   - Backend:
     ```bash
     npm run dev
     ```

6. Open the app in your browser:
   - Frontend: [http://localhost:3000](http://localhost:3000)
   - Backend: [ws://localhost:8080](ws://localhost:8080)

---

Enjoy seamless real-time communication with Wiz! 🚀

