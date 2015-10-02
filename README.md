# whipsocket

Evil fake socket credentials thief

If `/tmp` is shared, it's possible to create a world-writable socket there (eg `/tmp/mysql.sock`). Assume this is a malicious daemon which does three things:

1. Identify sockets which may be tried by local apps (`/var/lib/mysql.sock`, `/var/run/postgresql/.s.PGSQL.5432`)
2. Create likely looking socket files in `/tmp`
3. Wait for connections
4. Capture creds and replay them to real sockets
