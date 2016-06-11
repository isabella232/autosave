# Autosave package
[![OS X Build Status](https://travis-ci.org/atom/autosave.svg?branch=master)](https://travis-ci.org/atom/autosave) [![Windows Build Status](https://ci.appveyor.com/api/projects/status/3aktr9updp722fqx/branch/master?svg=true)](https://ci.appveyor.com/project/Atom/autosave/branch/master) [![Dependency Status](https://david-dm.org/atom/autosave.svg)](https://david-dm.org/atom/autosave)

Autosaves editor when they lose focus, are destroyed, or when the window is closed.

This package is disabled by default and can be enabled via the
`autosave.enabled` config setting or from the Autosave section of the Settings view (OS X: <kbd>cmd-,</kbd>, Windows & Linux: <kbd>Ctrl-,</kbd>).

## Service API

### package.json
``` json
"consumedServices": {
  "autosave": {
    "versions": {
      "0.22.0": "consumeAutosave"
    }
  }
}
```

### package initialize
``` coffeescript
consumeAutosave: (dontSaveIf) ->
  dontSaveIf (paneItem) -> paneItem.getPath() is '/dont/autosave/me.coffee'
```
