# spiral23's Kometa Configuration File

Kometa uses a YAML configuration file to set its behavior and define connection details for Plex Media Server, Radarr, Sonarr, and other third-party services. By default, Kometa looks for the config file at `/config/config.yml`. A template configuration file is available in the [GitHub Repo](link).

## Supported Services

The following services can be configured in the `config.yml` file:

| Attribute       | Required                         |
| --------------- | -------------------------------- |
| libraries       | Yes                              |
| playlist\_files | Yes                              |
| settings        | Yes                              |
| webhooks        | No                               |
| plex            | Yes (either here or per library) |
| tmdb            | Yes                              |
| tautulli        | No                               |
| github          | No                               |
| omdb            | No                               |
| mdblist         | No                               |
| notifiarr       | No                               |
| gotify          | No                               |
| anidb           | No                               |
| radarr          | No                               |
| sonarr          | No                               |
| trakt           | No                               |
| mal             | No                               |

## Example Configuration (`config.yml`)

Below is an example of a "standard" configuration file:

```yaml
## This file is a template remove the .template to use the file

libraries:                           # This is called out once within the config.yml file
  Movies:                            # These are names of libraries in your Plex
    remove_overlays: false           # Set this to true to remove all overlays
    collection_files:
      - default: basic               # This is a file within Kometa's defaults folder
      - default: imdb                # This is a file within Kometa's defaults folder
      # see the wiki for how to use local files, folders, URLs, or files from git
    overlay_files:
      - default: ribbon              # This is a file within Kometa's defaults folder
      # see the wiki for how to use local files, folders, URLs, or files from git
  TV Shows:
    remove_overlays: false           # Set this to true to remove all overlays
    collection_files:
      - default: basic               # This is a file within Kometa's defaults folder
      - default: imdb                # This is a file within Kometa's defaults folder
      # see the wiki for how to use local files, folders, URLs, or files from git
    overlay_files:
      - default: ribbon              # This is a file within Kometa's defaults folder
      # see the wiki for how to use local files, folders, URLs, or files from git
  Anime:
    collection_files:
      - default: basic               # This is a file within Kometa's defaults folder
      - default: anilist             # This is a file within Kometa's defaults folder
      # see the wiki for how to use local files, folders, URLs, or files from git
  Music:
    collection_files:
      - file: config/Music.yml       # This is a local file THAT YOU MIGHT CREATE
playlist_files:
  - default: playlist                # This is a file within Kometa's defaults folder
    template_variables:
      libraries: Movies, TV Shows    # list of libraries that you want the Kometa Defaults playlists to look at
  # see the wiki for how to use local files, folders, URLs, or files from git
settings:
  run_order:
  - operations
  - metadata
  - collections
  - overlays
  cache: true
  cache_expiration: 60
  asset_directory: config/assets
  asset_folders: true
  asset_depth: 0
  create_asset_folders: false
  prioritize_assets: false
  dimensional_asset_rename: false
  download_url_assets: false
  show_missing_season_assets: false
  show_missing_episode_assets: false
  show_asset_not_needed: true
  sync_mode: append
  minimum_items: 1
  default_collection_order:
  delete_below_minimum: true
  delete_not_scheduled: false
  run_again_delay: 2
  missing_only_released: false
  only_filter_missing: false
  show_unmanaged: true
  show_unconfigured: true
  show_filtered: false
  show_options: true
  show_missing: true
  show_missing_assets: true
  save_report: false
  tvdb_language: eng
  ignore_ids:
  ignore_imdb_ids:
  item_refresh_delay: 0
  playlist_sync_to_users: all
  playlist_exclude_users:
  playlist_report: false
  verify_ssl: true
  custom_repo:
  overlay_artwork_filetype: jpg
  overlay_artwork_quality: 75
webhooks:                            # Can be individually specified per library as well
  error:
  version:
  run_start:
  run_end:
  changes:
plex:                                # Can be individually specified per library as well; REQUIRED for the script to run
  url: http://192.168.1.12:32400
  token: ####################
  timeout: 60
  db_cache:
  clean_bundles: false
  empty_trash: false
  optimize: false
  verify_ssl:
tmdb:                                # REQUIRED for the script to run
  apikey: ################################
  language: en
tautulli:                            # Can be individually specified per library as well
  url: http://192.168.1.12:8181
  apikey: ################################
github:
  token: ################################
omdb:
  apikey: ########
  cache_expiration: 60
mdblist:
  apikey: #########################
  cache_expiration: 60
notifiarr:
  apikey: ####################################
gotify:
  url: http://192.168.1.12:80
  token: ####################################
anidb:                               # Not required for AniDB builders unless you want mature content
  username: ######
  password: ######
radarr:                              # Can be individually specified per library as well
  url: http://192.168.1.12:7878
  token: ################################
  add_missing: false
  add_existing: false
  upgrade_existing: false
  monitor_existing: false
  root_folder_path: "S:/Movies"
  monitor: true
  availability: announced
  quality_profile: HD-1080p
  tag:
  search: false
  radarr_path:
  plex_path:
sonarr:                              # Can be individually specified per library as well
  url: http://192.168.1.12:8989
  token: ################################
  add_missing: false
  add_existing: false
  upgrade_existing: false
  monitor_existing: false
  root_folder_path: "S:/TV Shows"
  monitor: all
  quality_profile: HD-1080p
  language_profile: English
  series_type: standard
  season_folder: true
  tag:
  search: false
  cutoff_search: false
  sonarr_path:
  plex_path:
trakt:
  client_id: ####################
  client_secret: ####################
  pin:
  authorization:
    # everything below is autofilled by the script
    access_token:
    token_type:
    expires_in:
    refresh_token:
    scope: public
    created_at:
mal:
  client_id: ####################
  client_secret: ####################
  authorization:
    # everything below is autofilled by the script
    access_token:
    token_type:
    expires_in:
    refresh_token:
```

### Notes

- Replace `####################` with your actual tokens or API keys.
- Detailed instructions for configuring each service can be found in the [Kometa documentation](link).

