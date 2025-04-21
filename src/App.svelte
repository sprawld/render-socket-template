<script>
  import { io } from "socket.io-client";

  const socket = io();
  let connection = $state("connecting");

  socket.on("connect", () => {
    connection = "connected";
  });

  socket.on("disconnect", () => {
    connection = "disconnected";
  });

  socket.on("error", err => {
    connection = `Error: ${err}`;
  });

</script>

<h1>Render Socket.io Base Template</h1>
<h2>{connection}</h2>