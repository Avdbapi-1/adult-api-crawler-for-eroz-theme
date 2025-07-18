# Adult API Crawler Setup Guide for Eroz Theme

## System Requirements

- WordPress 5.0+
- PHP 7.4+
- Eroz Theme activated
- Admin permissions to install plugins

## Step 1: Install Plugin

1. Upload the `adult-api-crawler-for-wp-script-main` folder to `/wp-content/plugins/`
2. Go to WordPress Admin → Plugins
3. Activate the "Adult API Crawler For Eroz Theme" plugin

## Step 2: Initial Configuration

### 2.1 Check Eroz Theme
- Ensure Eroz theme is activated
- Check that meta fields have been created:
  - `eroz_meta_src` (poster image)
  - `embed` (video embed)
  - `original_name_1` (original name)
  - `movie_code_1`, `movie_code_2`, `movie_code_3` (movie codes)
  - `eroz_post_desc` (description)
  - `duration` (duration)

### 2.2 Configure API
1. Go to "Adult API Crawler For Eroz Theme" menu
2. Enter API URL (default: `https://avdbapi.com/api.php/provide/vod/?ac=detail`)
3. Click "Check API" to test connection

## Step 3: Meta Fields Configuration

### 3.1 Check Meta Fields in Eroz Theme
Go to WordPress Admin → Appearance → Customize → Video Settings to check:

- **Video Field**: `embed` (default)
- **Duration Field**: `duration` (default)
- **Trailer Field**: `trailer_url` (default)

### 3.2 Meta Fields Mapping
The plugin will automatically map the following fields:

| API Field | Eroz Meta Field | Description |
|-----------|----------------|-------------|
| `poster_url` | `eroz_meta_src` | Poster image URL |
| `embed` | `embed` | Video embed code |
| `original_name` | `video_optional_1` | Original name |
| `movie_code` | `movie_code_1` | Movie code |
| `description` | `eroz_post_desc` | Post description |
| `duration` | `duration` | Video duration |
| `trailer_url` | `trailer_url` | Trailer URL |

## Step 4: Test Crawling

### 4.1 Manual Test
1. Go to plugin menu
2. Select "Recent" to crawl the latest 5 pages
3. Click "Get Movies" to view the list
4. Select 1-2 videos to test
5. Click "Crawl" to import

### 4.2 Check Results
After successful crawling, check:

1. **Post Created**: Go to Posts to view
2. **Meta Fields**: Check that meta fields are filled correctly
3. **Categories**: Check that categories are created
4. **Actors**: Check actors taxonomy
5. **Tags**: Check that tags are created
6. **Featured Image**: Check that poster is set

## Step 5: Cronjob Configuration

### 5.1 Enable Cronjob
1. Go to "Cronjob Settings" tab
2. Enable "Enable Cronjob"
3. Choose appropriate schedule (recommended: "Every 2 Hours")
4. Enable "Download Images" if you want to save images locally
5. Click "Save Settings"

### 5.2 Check Cronjob
- View "Next Run" to know when the next run will occur
- View "Last Run" to check the most recent run
- View "Last Status" to check results

## Step 6: Optimization

### 6.1 Performance
- Set "Download Images" = OFF to save storage
- Use "Recent" instead of "All" to avoid crawling too much
- Set appropriate schedule based on server capacity

### 6.2 SEO
- Check permalink structure
- Ensure categories and tags are created correctly
- Check meta description

## Troubleshooting

### Common Issues

#### 1. API Connection Failed
- Check API URL
- Try different API: `https://xvidapi.com/api.php/provide/vod/?ac=detail`
- Check firewall/security plugins

#### 2. Meta Fields Not Filled
- Check that Eroz theme is activated
- Check that meta fields are created
- View error log in WordPress

#### 3. Cronjob Not Running
- Check that WordPress cron is enabled
- Try manual test
- Check server cron settings

#### 4. Images Not Displaying
- Check `eroz_meta_src` field
- Check that featured image is set
- Check theme template

### Debug Mode
Enable WP_DEBUG in wp-config.php to view detailed errors:

```php
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);
```

## Support

If you encounter issues:
1. Check error logs
2. Test with different API
3. Check theme compatibility
4. Contact support

## Changelog

### Version 2.0.0
- Full compatibility with Eroz Theme
- Accurate meta fields mapping
- Improved performance
- Added many additional meta fields 