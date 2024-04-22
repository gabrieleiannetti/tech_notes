# Debian

## Package Repositories

Package repository list `/etc/apt/sources.list`:

```
deb http://deb.debian.org/debian buster main contrib non-free
deb-src http://deb.debian.org/debian buster main contrib non-free

deb http://deb.debian.org/debian-security/ buster/updates main contrib non-free
deb-src http://deb.debian.org/debian-security/ buster/updates main contrib non-free

deb http://deb.debian.org/debian buster-updates main contrib non-free
deb-src http://deb.debian.org/debian buster-updates main contrib non-free

deb http://deb.debian.org/debian buster-backports main contrib non-free
deb-src http://deb.debian.org/debian buster-backports main contrib non-free

deb http://deb.debian.org/debian/ unstable main contrib non-free
```

Specify lower prio for unstable packages `/etc/apt/preferences.d/99pin-unstable`:

```
Package: *
Pin: release a=stable
Pin-Priority: 900

Package: *
Pin release a=unstable
Pin-Priority: 10
```

Update repository references: `apt-get update`

## Sudoers

First install required package: `apt-get install sudo`

Add new USER to sudoers file `/etc/sudoers`:  

```
root ALL=(ALL:ALL) ALL
USER ALL=(ALL:ALL) ALL
```

## Firefox

* `sudo apt install -t unstable firefox`
* `sudo apt purge firefox-esr`

	Installing latest Firefox from unstable might also install/upgrade packages from unstable mirror.  
	Downgrading unstable packages could be an option on system failure.

## Troubleshooting

### Audio

https://support.system76.com/articles/audio/
