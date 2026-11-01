# Systemd-tjänst för Dlorg

Dlorg kan köras som en användartjänst med systemd. Det gör att Dlorg startar automatiskt vid inloggning och övervakar `~/Downloads` i bakgrunden.

## Varför användartjänst?

En användartjänst (`systemctl --user`) körs under den inloggade användaren och kräver **inga root-rättigheter**. Det gör tjänsten portabel och säker.

## Skapa tjänsten

### 1. Skapa mappen för användartjänster

```bash
mkdir -p ~/.config/systemd/user
