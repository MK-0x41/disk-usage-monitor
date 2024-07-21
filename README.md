   # Disk Usage Monitor

   Dieses Repository enthält ein Skript, das den Speicherplatz überwacht und eine Benachrichtigung über Matrix sendet, wenn der Speicher zu 95% voll ist.

   ## Installation

   1. **Repository klonen**:

      ```bash
      git clone https://git.cs30.de/MK_0x41/disk-usage-monitor.git; \
      cd disk-usage-monitor
      ```

   2. **Konfigurationsdatei bearbeiten**:

      Bearbeite die Datei `config.cfg` und setze deine Matrix-Server-URL, dein Zugriffstoken und die Raum-ID ein:

      ```bash
      nano config.cfg
      ```

      ```bash
      vim config.cfg
      ```

      Erstelle einen matrix token für die config:
      ```bash
      curl -XPOST -d '{"type": "m.login.password", "identifier": {"user": "botusername", "type": "m.id.user"}, "password": "passwordforuser"}' "https://home.server/_matrix/client/r0/login"
      ```

   3. **Installationsskript ausführen**:

      ```bash
      sudo ./install.sh
      ```

      Dieses Skript kopiert das Überwachungsskript nach `/usr/local/bin`, ersetzt die Platzhalter durch die Werte aus der Konfigurationsdatei, erstellt und startet einen Systemd-Dienst.
   4. **Check status**

      ```bash
      systemctl status check_disk_usage.service
      ```

      and for timer

      ```bash
      systemctl status check_disk_usage.timer
      ```
   5. **To change setting**
      Change Settings in config.cfg and run `./install.sh` again

   ## Lizenz

   Dieses Projekt ist unter der MIT-Lizenz lizenziert. Siehe die [LICENSE](LICENSE)-Datei für Details.
