# 🏆 TopServerRewards

Plugin do automatycznego nagradzania graczy za głosowanie na serwer na **[TopServer.pl](https://topserver.pl/)** — polskiej liście serwerów Minecraft.

## ✨ Funkcje

- **Odbieranie nagród** za głosy przez prostą komendę `/ts odbierz`
- **Konfigurowalny system nagród** — itemy, komendy, pieniądze (Vault)
- **Ogłoszenia na serwerze** — broadcast po odebraniu nagrody
- **Pełna customizacja wiadomości** — kolory, placeholdery, możliwość wyłączenia każdej wiadomości
- **Cooldown** — ochrona przed spamem komendy
- **Reload konfiguracji** na żywo (`/ts reload`)
- **Tab-completion** komend

## 📋 Wymagania

- Serwer Minecraft **1.20+** (Spigot / Paper / Forks)
- Java **17+**
- Dodany serwer na [TopServer.pl](https://topserver.pl/)

## ⚙️ Instalacja

1. Pobierz najnowszy `TopServerRewards-x.x.jar` z [TopServer.PL](https://topserver.pl/tutorial.php)
2. Wrzuć plik `.jar` do folderu `plugins/` na serwerze
3. Zrestartuj serwer
4. Edytuj `plugins/TopServerRewards/config.yml` — ustaw **`server-ip`** na adres IP swojego serwera (taki jak na TopServer.pl)
5. Przeładuj konfig: `/ts reload`

## 🔧 Komendy

| Komenda | Opis | Uprawnienie |
|---------|------|-------------|
| `/ts` | Wyświetla pomoc | — |
| `/ts odbierz` | Odbiera nagrodę za głos | `topserver.claim` (domyślnie: wszyscy) |
| `/ts reload` | Przeładowuje konfigurację | `topserver.admin` (domyślnie: OP) |

**Aliasy:** `/topserver`, `/tsreward`

## 🎁 Konfiguracja nagród

Plik `config.yml` umożliwia ustawienie trzech typów nagród:

```yaml
rewards:
  enabled: true
  broadcast: true          # Ogłoszenie na chacie po odebraniu

  items:                   # Przedmioty
    enabled: true
    list:
      - "DIAMOND:5"
      - "EMERALD:3"
      - "GOLDEN_APPLE:1"

  commands:                # Komendy z konsoli
    enabled: false
    list:
      - "give {player} diamond_sword 1"
      - "eco give {player} 500"

  money:                   # Pieniądze (wymaga Vault)
    enabled: false
    amount: 100.0
```

## 💬 Customizacja wiadomości

Wszystkie wiadomości można dowolnie zmieniać w `config.yml`. Obsługiwane placeholdery:

| Placeholder | Opis |
|-------------|------|
| `{player}` | Nick gracza |
| `{command}` | Pełna komenda (np. `/ts odbierz`) |
| `{server}` | Nazwa serwera z API |
| `{seconds}` | Sekundy cooldownu |
| `{error}` | Treść błędu |
| `{amount}` | Kwota pieniędzy |
| `{api_message}` | Wiadomość z API |

> **Tip:** Aby wyłączyć konkretną wiadomość, ustaw jej wartość na `""` lub `false`.

## 🔌 API

Plugin korzysta z oficjalnego API TopServer.pl. Komunikacja odbywa się asynchronicznie, aby nie blokować głównego wątku serwera.



## 📄 Licencja

Projekt open-source.

---

<p align="center">
  Stworzony z ❤️ do użytku z <a href="https://topserver.pl/">TopServer.pl</a>
</p>
