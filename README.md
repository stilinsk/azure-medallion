# azure-medallion
```
SELECT * 
FROM INFORMATION_SCHEMA.TABLES 
WHERE TABLE_SCHEMA = 'SalesLT' 
AND TABLE_TYPE = 'BASE TABLE';
```
```
dbutils.fs.mount(
    source='wasbs://@medalionytazure.blob.core.windows.net',
    mount_point='/mnt/bronze',
    extra_configs = {'fs.azure.account.key.medalionytazure.blob.core.windows.net': dbutils.secrets.get(scope = "data", key = "dataa")}
)

dbutils.fs.mount(
    source='wasbs://@medalionytazure.blob.core.windows.net',
    mount_point='/mnt/silver',
    extra_configs = {'fs.azure.account.key.medalionytazure.blob.core.windows.net': dbutils.secrets.get(scope = "data", key = "dataa")}
)

dbutils.fs.mount(
    source='wasbs://@medalionytazure.blob.core.windows.net',
    mount_point='/mnt/gold',
    extra_configs = {'fs.azure.account.key.medalionytazure.blob.core.windows.net': dbutils.secrets.get(scope = "data", key = "dataa")}
)
```
