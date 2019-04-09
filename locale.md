# Locale Settings

## List Active Locale Settings

Lists all active locale settings on the system: ```locale```

## Generate German Locales

* Uncomment the locale definition __de_DE.UTF-8 UTF-8__ in `/etc/locale.gen`.
* Generate the locales definitions: `sudo locale-gen`

### Set Locales by localectl

#### Explicitly Set Date and Time Local Setting

Set the date and time local settings for e.g. German so the weeks start at monday instead of Sunday as for US locale setting:

```sudo localectl set-locale LC_TIME=de_DE.UTF-8```

#### Set Primary Language to German with American English User Interface

Setting all locale categories (LC*) to german: ```sudo localectl set-locale LANG=de_DE.UTF-8```

Then override specific LC settings explicitley if neccessary.  
For instance to display texts on the UI in en_US: ```sudo localectl set-locale LC_MESSAGES=en_US.UTF-8```

### Set Locales by locale.conf

If setting locales by localectl does not work, set the locale settings in `/etc/locale.conf`:

```
LANG="de_DE.utf8"
LC_TIME="de_DE.utf8"
```

## Ressources

* Short overview about locales: https://wiki.archlinux.org/index.php/locale
