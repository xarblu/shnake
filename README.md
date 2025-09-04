# SHNAKE

Shell Snake - a basic snake written in [pure](#notes) bash

## Quick Start

To play you can simply `curl` the script and run it with `bash`:

```bash
$ bash <(curl https://raw.githubusercontent.com/xarblu/shnake/refs/heads/main/shnake)
```

See help with:

```bash
$ bash <(curl https://raw.githubusercontent.com/xarblu/shnake/refs/heads/main/shnake) --help
```

## Notes

Technically we call a single external command (`stty`) to disable tty input echo.
Because it involves `ioctl()` calls I'm not sure this is possible in just BASH.
The `read -s` builtin somehow achieves no-echo - so *BASH can disable echo* - it's just not
a feature available to us outside of `read`.

I personally will still consider `shnake` pure because you could just rip out `stty` and everything
would work the same (besides the occasional echoed control chars messing with drawing the frame).


