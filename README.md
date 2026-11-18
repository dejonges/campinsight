# Warmtepomp-dashboard

Met een wachtwoord beveiligd dashboard van de Panasonic Aquarea-warmtepomp.
De data zelf staat in de private repo `aquarea-warmtepomp-data`; deze publieke repo
bevat alleen de publicatie-workflow. De pagina wordt met [StatiCrypt](https://github.com/robinmoisson/staticrypt)
(AES-256) versleuteld voordat ze online komt; zonder wachtwoord is de inhoud onleesbaar.

Elke ochtend (en manueel via **Actions → Dashboard publiceren → Run workflow**) wordt de
pagina opnieuw gebouwd met de laatste data.

## Eenmalige instelling

1. **Settings → Pages → Source:** GitHub Actions.
2. **Settings → Secrets and variables → Actions → New repository secret:**
   - `DASHBOARD_PASSWORD`: het wachtwoord voor het dashboard.
   - `DATA_REPO_TOKEN`: een fine-grained personal access token met enkel
     *Contents: Read-only* op `dejonges/aquarea-warmtepomp-data`.

`staticrypt-salt.txt` is geen geheim; het zorgt ervoor dat "Onthoud mij" blijft werken na een nieuwe publicatie.
