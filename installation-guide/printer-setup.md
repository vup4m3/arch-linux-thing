# Printer Setup

## Install the software:

```console
sudo pacman -S cups gutenprint cups-pdf gtk3-print-backends nmap 
```

## Enable Cups Service: 

```console
sudo systemctl enable org.cups.cupsd.service 
```

## Start the Cups Service: 

```console
sudo systemctl start org.cups.cupsd.service 
```