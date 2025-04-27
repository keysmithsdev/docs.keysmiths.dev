# Keyload Types

There are two supported protocols for keyloading - TWI and DLI.

## TWI
TWI will fill keys via a physical serial link to the radio. This requires the use of an adapter (e.g. KFDtool, KFDShield, KFDmicro, etc.). A non-exhaustive list of compatible adapters can be found on the [Adapters](Adapters/index.md) page.

## DLI
DLI will fill keys via an IP link to the radio. The radio can be filled so long as it reachable by a route in the Windows routing table - for example, RNDIS over USB; PPP over serial; etc.