# Choosing a DX cluster

DX Pilot keeps its existing connection as **DX Pilot default**. Existing users
keep their saved server and reporting-station filter when updating. A previously
saved non-default server is automatically treated as Custom.

In web setup, under **Conventional DX cluster**:

1. Leave Default selected, or choose **Custom cluster**.
2. For Custom, enter the node's server address and TCP port. Use the address
   supplied by its operator, without `http://`, `telnet://` or a webpage path.
3. Usually leave Login options blank: DX Pilot uses your station callsign.
   Enter a different permitted login and/or node password only when needed.
4. Press **Test connection**. It tests these details without saving them, then
   reconnects the saved cluster. Press **Save settings and restart display**
   when you want to make the change permanent.

The same options are available on the display under **Settings > DX cluster**.
Choose Custom, then Server and login options. Reporters and Test connection
have separate pages. Return to the main Settings menu and save to apply changes.
The test temporarily interrupts the normal cluster connection. PSK propagation
remains independent; test reports do not enter spot caches or trigger DX alerts.

**UK stations** preserves the existing G*,M*,2* reporting-prefix filter.
**Worldwide stations** includes reports from all spotters. **Custom reporting
stations** accepts exact callsigns separated by commas and prefixes ending in *.
Worldwide reports do not establish that a station is audible from your home;
PSK propagation near home continues to use the separate receiver-radius filter.

A connection test succeeds only after a recognised logged-in prompt or valid DX
spot is received. Reaching a TCP port or sending a callsign is not sufficient.
A quiet or unusual node that gives neither within 25 seconds produces an
unconfirmed-login result. DX Pilot supports conventional Telnet DX cluster
login and `DX de` reports, including the usual DX Spider flow. Browser-only,
TLS-only, multi-factor and operator-specific interactive login flows are outside
this version's support. Ask the node operator for its client address/port and
registration requirements.

If another logger uses the same node and callsign, the node may disconnect one
client. Use a separate login/suffix only when the operator permits it. DX Pilot
does not send spots or issue node filter/setup commands.

Passwords are never returned in web HTML or status responses. Blank keeps a
saved password when the custom server, port and login are unchanged; Clear
removes it. Changing the destination or account clears the old password unless
a replacement is entered. For on-device editing, enter the server and login first,
then enter the password. Selecting Default never sends a stored Custom login
or password to the default server. Traditional Telnet is unencrypted: use a
password dedicated to that node. On the display, Show reveals an edited password
only while you are editing it.

Available on both supported display sizes.
