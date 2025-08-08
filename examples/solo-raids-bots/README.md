# Solo server with raids and bots

This example spins up a private Rust server using the Oxide-enabled Docker image.
It adds bot-controlled raids, monument patrols, and timed events to simulate a
full server while you play alone.

## Usage

```shell
git clone https://github.com/max-pfeiffer/rust-game-server-docker.git
cd rust-game-server-docker/examples/solo-raids-bots
docker compose up -d
```

Stop the server with:

```shell
docker compose down
```

## Plugins

Download the required plugins and place the `.cs` files in
`oxide/plugins/` (see [oxide/plugins/README.md](oxide/plugins/README.md)):

- BotSpawn – roaming NPCs
- TruePVE – prevent player-vs-player damage
- BetterLoot – balanced loot tables
- HeliControl – control patrol helicopter spawns
- BradleyControl – control Bradley APC respawns
- AirDropExtended – schedule airdrops
- Raidable Bases – procedurally generated raid bases *(premium plugin)*

## Configuration

Plugin configuration files are located in `oxide/config/` and can be adjusted
as needed. The Rust server configuration resides in
`server/solo_server/cfg/server.cfg`.

## Connect

From the Rust client console, connect to the server:

```shell
client.connect <your-ip>:28015
```
