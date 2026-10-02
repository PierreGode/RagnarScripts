# Console scripts

JSON serial-console command sequences for the **Device Console** card in Ragnar
(Dashboard). Install one → it is copied into `data/console_scripts/` and appears
in the Run-script picker. Schema:

```json
{
  "name": "Show Version (Arista)",
  "description": "What it does",
  "vendor": "arista",
  "commands": [ {"cmd": "show version", "delay": 2} ]
}
```

The **file name is the script id** (letters, digits, `_`, `-`). A bare `""`
command sends Enter to wake the prompt.
