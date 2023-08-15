Since I have a much-beloved, far-too-long-unused Nord G2X, and am currently
running NixOS for a desktop, I want to get this running on NixOS.

In an ideal world I'd be able to build it from source, using
[Lazarus](https://www.lazarus-ide.org/), but since the Gen2 codebase uses FMX
(FireMonkey), but judging from these
[forum](https://forum.lazarus.freepascal.org/index.php?topic=16356.0)
[threads](https://forum.lazarus.freepascal.org/index.php?topic=46571.0), I
don't think Lazarus supports FMX or ever will. If I was going to go through the
kind of effort required to port to a different toolkit, I'd probably port to a
language I know fairly well and which other contributors might use.

So, that kind of leaves me at using the existing Linux binaries. For
future-proofness, I've committed the Linux binary downloaded from
https://www.bverhue.nl/g2dev/?page_id=17 to `Gen2/G2_editor_FMX`.

Starting it with `steam-run Gen2/G2_editor_FMX` (as I have the `steam` package
configured
[here](https://gitlab.com/NateEag/nixos-framework-setup/blob/754754c26f07174834b40fd1ffab2fe5f75462b7/etc/nixos/configuration.nix#L220))
actually *almost* works. If no G2 is connected, it boots as you'd expect.

When the G2 *is* connected, it fails.

Guessing that's due to the libusb dependency not being available?
