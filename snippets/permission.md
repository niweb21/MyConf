### change permission only directory

    find . -type d -exec chmod 775 {} +

### change permission only file

    find . -type f -exec chmod 664 {} +

### change permission only directory

    chown www-data:www-data -R .
