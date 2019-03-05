# Locale Settings

## List Active Locale Settings

Lists all active locale settings on the system: ```locale```

## Generate German Locales

* Uncomment the locale definition e.g. "de_DE.UTF-8 UTF-8" to create in the listed locales file: ```/etc/locale.gen```
* Generate the locales definitions: ```sudo locale-gen```

## Set Date and Time Local Setting

Set the date and time local settings for e.g. German so the weeks start at monday instead of Sunday as for US locale setting:

```sudo localectl set-locale LC_TIME=de_DE.UTF-8```

## Set Main Locale to German With US Additionals

> TODO: Alternativeley set all locale to german locals and just specifiy the keyboard and system language in US.
