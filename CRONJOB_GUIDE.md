# Auto-Crawling (Cronjob) Feature Guide

## 🎯 Overview

The Auto-Crawling feature allows your WordPress site to automatically import videos from your chosen API at scheduled intervals. This eliminates the need for manual crawling and keeps your site updated with fresh content automatically.

## ⚡ Quick Start

1. **Enable Auto-Crawling**
   - Go to **Adult API Crawler** in your WordPress admin
   - Check the "Enable Auto-Crawling" checkbox
   - Configure your settings (see details below)
   - Click "Save Settings"

2. **Recommended Setup**
   - **API URL**: `https://avdbapi.com/api.php/provide/vod/?ac=detail`
   - **Crawling Method**: Collect Recent Videos
   - **Schedule**: Twice Daily
   - **Image Downloading**: Disabled (to save storage)

3. **Test Your Setup**
   - Click "Test Now" to verify everything works
   - Check the status indicators for confirmation

## 🔧 Configuration Options

### API URL
- **AVDBAPI**: `https://avdbapi.com/api.php/provide/vod/?ac=detail`
- **XVIDAPI**: `https://xvidapi.com/api.php/provide/vod/?ac=detail`
- **Custom API**: Your own API endpoint

### Crawling Methods

#### 1. Collect Recent Videos (Recommended)
- **What it does**: Imports videos from the first 5 pages
- **Best for**: Regular content updates
- **Server load**: Low
- **Use case**: Keeping your site fresh with latest content

#### 2. Collect Selected Pages
- **What it does**: Imports videos from specific page ranges
- **Best for**: Targeted content collection
- **Server load**: Medium
- **Use case**: Importing specific categories or content types

#### 3. Collect All Videos
- **What it does**: Imports videos from all available pages
- **Best for**: Initial site setup or bulk imports
- **Server load**: High
- **Use case**: Complete content migration (use with caution)

### Schedule Options

| Schedule | Frequency | Best For | Server Impact |
|----------|-----------|----------|---------------|
| Every 30 Minutes | Very frequent | High-traffic sites | High |
| Every Hour | Frequent | Active sites | Medium-High |
| Every 2 Hours | Moderate | Most sites | Medium |
| Every 6 Hours | Less frequent | Moderate sites | Low-Medium |
| Twice Daily | Low frequency | Standard sites | Low |
| Once Daily | Minimal | Small sites | Very Low |

## 📊 Monitoring Your Auto-Crawling

### Status Indicators
- **Status**: Shows if auto-crawling is enabled/disabled
- **Next Run**: When the next automatic crawl will occur
- **Last Run**: When the last crawl was performed
- **Total Runs**: How many times auto-crawling has run
- **Last Status**: Results of the most recent crawl

### Understanding Status Messages
- ✅ **Success**: Videos were imported successfully
- ❌ **Error**: Something went wrong (check the message for details)
- ⏸️ **Paused**: Auto-crawling is temporarily disabled
- 🔄 **Running**: Currently processing videos

## 🚀 Best Practices

### For New Sites
1. Start with "Collect Recent Videos" and "Twice Daily"
2. Test the setup before enabling
3. Monitor server performance
4. Gradually increase frequency if needed

### For Established Sites
1. Use "Collect Selected Pages" for targeted updates
2. Schedule during low-traffic hours
3. Monitor "Last Status" regularly
4. Adjust settings based on performance

### Storage Optimization
- **Leave image downloading disabled** (recommended)
- Uses thumbnail URLs directly from API
- Saves significant server storage space
- Speeds up crawling process

## 🔍 Troubleshooting

### Auto-Crawling Not Working?

#### 1. Check WordPress Cron
WordPress cronjobs require site traffic to trigger. If your site has low traffic:
- Consider using a real cronjob service
- Install WP-Cron Control plugin
- Use external cron services

#### 2. Verify Settings
- Ensure auto-crawling is enabled
- Check API URL is correct and accessible
- Verify crawling method is appropriate
- Confirm schedule is set correctly

#### 3. Test API Connection
- Use the "Test Now" button
- Check if API returns valid JSON
- Verify API is not rate-limited

#### 4. Check Server Resources
- Monitor server CPU and memory usage
- Ensure sufficient disk space
- Check PHP execution time limits

#### 5. Review Error Logs
- Check "Last Status" for error messages
- Review WordPress error logs
- Monitor server error logs

### Common Issues and Solutions

#### Issue: "API connection failed"
**Solution**: 
- Verify API URL is correct
- Check if API is accessible from your server
- Try different API providers (AVDBAPI, XVIDAPI)

#### Issue: "No videos found"
**Solution**:
- Check if API returns valid JSON
- Verify API response format
- Test with different page ranges

#### Issue: "Server timeout"
**Solution**:
- Reduce crawling frequency
- Use "Collect Recent Videos" instead of "All"
- Increase PHP execution time limits

#### Issue: "Storage full"
**Solution**:
- Disable image downloading
- Use thumbnail URLs instead
- Clean up old media files

## 🔧 Advanced Configuration

### Custom Cron Schedules
If you need more control, you can add custom schedules by editing your theme's `functions.php`:

```php
// Add custom cron schedule
add_filter('cron_schedules', function($schedules) {
    $schedules['every_15_minutes'] = array(
        'interval' => 900,
        'display'  => 'Every 15 Minutes'
    );
    return $schedules;
});
```

### External Cron Services
For more reliable scheduling, consider these services:
- **EasyCron**: https://www.easycron.com/
- **Cron-job.org**: https://cron-job.org/
- **WP-Cron Control**: WordPress plugin

### Manual Cron Setup
For advanced users, you can set up a real cronjob:

```bash
# Add to your server's crontab
*/30 * * * * wget -q -O /dev/null "https://yoursite.com/wp-cron.php?doing_wp_cron"
```

## 📈 Performance Tips

### Optimize for Speed
1. Use "Collect Recent Videos" for regular updates
2. Disable image downloading
3. Schedule during low-traffic hours
4. Monitor server resources

### Optimize for Storage
1. Leave image downloading disabled
2. Use thumbnail URLs from API
3. Regularly clean up old media
4. Monitor disk space usage

### Optimize for Reliability
1. Test before enabling
2. Start with conservative settings
3. Monitor status regularly
4. Have backup plans ready

## 🆘 Support

If you need help with the auto-crawling feature:

1. **Check this guide first** - Most issues are covered here
2. **Review the main README** - For general plugin information
3. **Test with different settings** - Try different APIs and methods
4. **Monitor your server logs** - For detailed error information

### Getting Help
- Check "Last Status" for specific error messages
- Review WordPress error logs
- Test with different API providers
- Verify server requirements are met

---

**Remember**: Auto-crawling is a powerful feature that can significantly improve your site's content freshness. Start conservatively and adjust based on your needs and server capabilities. 