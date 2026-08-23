# Warp Tracker for Linux

Linux ports for the HSR and Genshin warp trackers when running game in Proton for using on StarRailStation and Paimon.moe (Or simular sites).

## Quickstart
Ensure you have `curl` installed, then  
  
Star Rail
```
curl -fsSL "https://raw.githubusercontent.com/billsboard/linux-warp-tracker/main/star-rail/star-rail-warp-link" | bash -s --
```
Genshin
```
curl -fsSL "https://raw.githubusercontent.com/billsboard/linux-warp-tracker/main/genshin/genshin-wish-link" | bash -s --
```


## Run full script from repository
Star Rail
```
warp-tracker --star-rail 
```
Genshin
```
warp-tracker --genshin
```

  
### Options
`--prefix /path/to/proton/prefix`: Specify proton prefix to check the path for
`--cache-file /path/to/cache`: Use a specific Cache_Data
`--region <region>`: global (default) or china
`--no-validate`: Return the newest cached URL without testing its auth key