# Socket Echo Server & Client

A small TCP echo server that handles multiple clients at once using threads,
plus a matching client.

## Run it

Terminal 1:
    python server.py

Terminal 2 (and 3, 4...):
    python client.py

Anything you type in a client gets echoed back as `echo: <your message>`.

## Notes

- Server spawns a thread per connection (`daemon=True` so they die with the main process).
- Uses `SO_REUSEADDR` so you don't get "address already in use" on quick restarts.
- Client uses a background thread to receive while the main thread reads input.
- Type `quit` in the client to disconnect.

## Possible next steps

- Add usernames per client
- Broadcast messages to all clients instead of echoing
- Swap `input()` for a proper CLI
- Move config into env vars or argparse
