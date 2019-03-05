# Locale Settings

## List Active Locale Settings

Lists all active locale settings on the system: ```locale```

## Generate German Locales

* Uncomment the locale definition e.g. "de_DE.UTF-8 UTF-8" to create in the listed locales file: ```/etc/locale.gen```
* Generate the locales definitions: ```sudo locale-gen```

## Set Date and Time Local Setting

Set the date and time local settings for e.g. German so the weeks start at monday instead of Sunday as for US locale setting:

```sudo localectl set-locale LC_TIME=de_DE.UTF-8```

## Set Primary Language to German with US User Interface

Setting all locale categories (LC*) to german: ```sudo localectl set-locale LANG=de_DE.UTF-8```

Important here is to keep US for english text translations for the UI: ```LANGUAGE=en_US:en```

## Ressources and Further Reading

* Short overview about locales: https://wiki.archlinux.org/index.php/locale
* Description of LANGUAGE variable: http://www.gnu.org/software/gettext/manual/gettext.html#The-LANGUAGE-variable
