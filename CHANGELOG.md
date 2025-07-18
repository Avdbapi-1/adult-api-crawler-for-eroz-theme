# Changelog - Adult API Crawler For Eroz Theme

## [2.0.0] - 2024-01-XX

### Added
- **Full compatibility with Eroz Theme**
- **Accurate meta fields mapping**:
  - `poster_url` → `eroz_meta_src` (Poster image)
  - `embed` → `embed` (Video embed - keep as is)
  - `original_name` → `video_optional_1` + `original_name_1`
  - `movie_code` → `movie_code_1`, `movie_code_2`, `movie_code_3`
  - `description` → `eroz_post_desc`
  - `duration` → `duration`
  - `trailer_url` → `trailer_url`

### Enhanced
- **Added multiple additional meta fields**:
  - `year` → `year`
  - `director` → `director`
  - `quality` → `quality`
  - `release_date` → `release_date`
  - `country` → `country`
  - `language` → `language`
  - `studio` → `studio`
  - `series` → `series`
  - `episode_number` → `episode_number`
  - `total_episodes` → `total_episodes`
  - `rating` → `rating`
  - `views` → `views`
  - `likes` → `likes`
  - `dislikes` → `dislikes`
  - `download_links` → `eroz_ads_link`
  - `subtitle_links` → `subtitle_links`
  - `video_sources` → `video_optional_2`, `video_optional_3`, `video_optional_4`
  - `movie_codes` → `movie_code_1`, `movie_code_2`, `movie_code_3`

### Changed
- **Updated plugin name**: "Adult API Crawler For Eroz Theme"
- **Updated description**: Compatible with Eroz Theme
- **Updated menu**: "Adult API Crawler For Eroz Theme Tools"
- **Removed wp-script specific fields**: `thumb`, `poster_url` meta fields
- **Optimized for Eroz Theme**: Use `eroz_meta_src` for poster images

### Fixed
- **Accurate meta fields mapping** for Eroz Theme
- **Compatibility with Eroz structure**: Use correct meta field names
- **Full support for Eroz features**: Original name, movie codes, description

### Documentation
- **Updated README.md**: Detailed guide for Eroz Theme
- **Created EROZ_THEME_SETUP.md**: Detailed setup guide
- **Created CHANGELOG.md**: Record of changes

### Technical Details
- **Preserved crawling mechanism**: No changes to crawling logic
- **Preserved API compatibility**: Support all API providers
- **Preserved cronjob functionality**: Cronjob works as before
- **Preserved admin interface**: Admin interface unchanged

### Compatibility
- **WordPress**: 5.0+
- **PHP**: 7.4+
- **Theme**: Eroz Theme
- **API Providers**: AVDBAPI, XVIDAPI, and other compatible APIs

### Migration Notes
- **From wp-script**: Plugin has been optimized for Eroz Theme
- **Meta fields**: Have been remapped to suit Eroz
- **Backward compatibility**: No impact on existing data
- **Performance**: Improved performance with Eroz Theme

---

## [1.x.x] - Previous versions (wp-script compatibility)

### Legacy Features
- Compatible with wp-script theme
- Used `thumb`, `poster_url` meta fields
- Basic mapping for wp-script structure

---

**Note**: Version 2.0.0 is the official version compatible with Eroz Theme. Previous versions were designed for wp-script theme.