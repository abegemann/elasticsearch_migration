## Elasticsearch migration (v1.3 to v5.x)

A simple python script to help you migrate indices from Elasticsearch v1.3 to v5.x while maintaining the same index name. Since Elasticsearch v2.3.0 and later there is the very handy `_reindex` call which can be used to copy documents from one index to another or even recreate the whole index. However, this call doesn't support at the moment the usage of the same index name on the destination host. This script uses the `_cat` call to fetch the list of all indices and the `_reindex` call to copy them to the destination host. It also takes into account the indices that have already been migrated and may be closed.
```
usage: migrate.py [-h] -s SOURCE -d DESTINATION [-t TIMEOUT]

arguments:
  -h, --help            show this help message and exit
  -s SOURCE, --source SOURCE
                        Source host with port eg. "http://host:9200"
  -d DESTINATION, --destination DESTINATION
                        Destination host with port eg. "http://host:9200"
  -t TIMEOUT, --timeout TIMEOUT
                        Timeout in seconds - Default: 10
```
### Prerequisites

- Python 2.7 (If you prefer to run the script on CentOS 6.x [here](https://gist.github.com/dalegaspi/dec44117fa5e7597a559) is a handy guide to install Python2.7 and pip2.7)
- pandas   (https://github.com/pandas-dev/pandas)
- requests (https://github.com/requests/requests)

## License

The code is available under the [MIT license](LICENSE).
