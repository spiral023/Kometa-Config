# My personal Kometa Configuration File

Kometa uses a YAML configuration file (https://metamanager.wiki/en/latest/config/overview/) to set its behavior and define connection details for Plex Media Server, Radarr, Sonarr, and other third-party services. By default, Kometa looks for the config file at `/config/config.yml`. A template configuration file is available at https://github.com/Kometa-Team/Kometa/blob/master/config/config.yml.template. You should start with this and slowly add changes.

## Summary of my configuration changes

### Library Names
- Updated library names from English to German (e.g., "Movies" to "Filme", "TV Shows" to "Serien").

### Collection Files
- Added several award-based collection files for the library "Filme", including BAFTA, Cannes, Emmy, Golden Globes, and Oscars, each with a weekly schedule.
- Added seasonal collection settings, including custom scheduling for holidays like Easter, Valentine's Day, Halloween, and Christmas.
- Custom IMDb and Trakt lists for holiday-themed collections such as Christmas, Halloween, and 420 Day.
- Added "separator" collection files (e.g., separator_award, separator_chart) for organizational purposes.

### Overlay Files
- Added overlay settings for libraries, including "ribbon" and "ratings" overlays, with configuration for positions, fonts, and ratings.
- Overlay schedules set for daily or weekly, depending on the library.

### Language and Sorting
- Set language to German (`language: de`) for all collection templates.
- Added sorting preferences (e.g., `sort_by: random`) to disable US-specific seasonal collections.

### Webhooks
- Added Notifiarr as the webhook for error, version, run_start, run_end, and changes notifications.

### Plex Configuration
- Updated Plex server URL to `http://192.168.1.2:32400` with the new token.

### TMDb Configuration
- Set TMDb language to German (`language: de`) and region to Austria (`region: AT`).

### Sonarr and Radarr Configuration
- Updated Sonarr and Radarr URLs, tokens, and quality profiles.
- Added several custom IMDb search filters for Sonarr and Radarr collections.

### Trakt Configuration
- Updated Trakt client ID, client secret, and authorization tokens.

### Additional Collections
- Added new collections such as "BAFTA Awards & Nominees", "2022-2024 Movie Awards", and theme-based collections like "Wall Street", "Mindfuck Movies", and "Roger Ebert List of Best Movies".
- Added IMDb and Trakt lists for custom collections like "Philipps Highlights", "Königlich", and "Mixed Martial Arts Highlights".

### Settings
- Enabled caching (`cache: true`) with expiration set to 60 minutes.
- Set `save_report` to true for saving collection reports.
- Updated `tvdb_language` to German (`tvdb_language: deu`).
- Configured run order as `metadata`, `collections`, `overlays`, `operations`.

### Templates and Themes
- Added holiday-themed templates (e.g., "Holiday", "Genre") with schedules for specific time ranges.
- Defined genre collections (e.g., Action, Adventure, Horror) with posters and summaries.

### Notable Changes
- Schedules for collections and overlays have been set to either weekly or daily, depending on the specific library and type of content.
- Specific IMDb lists have been used to curate collections, including award winners and themed movie lists.

