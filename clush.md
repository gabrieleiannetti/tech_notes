# Cluster Shell Notes

## Displaying Gathered Results in a dshbak-Like Way

```
clush -b -l root -w "host0[123-456]" "dpkg -l | grep image"
```
