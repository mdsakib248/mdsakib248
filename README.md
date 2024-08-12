// Node.js Example using Socket.io for real-time messaging
const io = require('socket.io')(3000);

io.on('connection', socket => {
  console.log('New user connected');
  
  socket.on('message', message => {
    console.log('Received message:', message);
    io.emit('message', message); // Broadcast message to all clients
  });
  
  socket.on('disconnect', () => {
    console.log('User disconnected');
  });
});
