# metasploit

## metasploit architecture

### modules

- Located in
  - `/usr/share/metasploit-framework/modules/`
  - `~/.msf4/modules`
  - Load additional modules using
    - `msfconsole -m <modules directory>`, or
    - `msf> loadpath <modules directory>` at the interactive console.

#### Types of modules
- **exploits**. modules that use payloads.
- **auxiliary**. port scanners, fuzzers, sniffers, etc.
- **payloads**. code that runs remotely.
- **encoders**. code the ensures that payloads make it to their destination intact.
- **nops**. keeps payload sizes consistent across exploit attempts.

### metasploit object model

#### modules, mixins, and plugins
- Modules are Ruby classes.
- Payloads are generated at runtime.
- Metasploit uses Ruby's mixin feature to allow for modules to have different "flavors" (e.g. HTTP, SMB, FTP flavors).
- Metasploit plugins interact directly with the Metasploit API to extend the framework as a whole.

## msfconsole

### contexts

### common commands

- `info <module>`. get detailed information on particular module `<module>`.
- `set`. set context-specific variable.
- `setg`. set global variable.
- `color (true|false|auto)`. enable or disable color output.
- `grep <phrase> <command>`. search for `<phrase>` in the output of `<command>`.

## msfvenom

### List available payloads

```
msfvenom -l payloads
```

