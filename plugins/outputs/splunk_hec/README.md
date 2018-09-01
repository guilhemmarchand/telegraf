# HTTP Output Plugin

This plugin sends metrics to Splunk Enterprise or Splunk Cloud using the http event collector (HEC)
data formats.  For data_formats that support batching, metrics are sent in batch format.

### Configuration:

```toml
# A plugin that can transmit metrics over HTTP
[[outputs.splunk_hec]]
  ## URL is the address to send metrics to
  url = "https://127.0.0.1/services/collector/raw"

  ## Timeout for HTTP message
  # timeout = "5s"

  ## HTTP method, one of: "POST" or "PUT"
  # method = "POST"

  ## Splunk HEC token
  hec_token = "Authorization: Splunk token_value"

  ## Optional TLS Config
  # tls_ca = "/etc/telegraf/ca.pem"
  # tls_cert = "/etc/telegraf/cert.pem"
  # tls_key = "/etc/telegraf/key.pem"
  ## Use TLS but skip chain & host verification
  # insecure_skip_verify = false

  ## Data format to output.
  ## Each data format has it's own unique set of configuration options, read
  ## more about them here:
  ## https://github.com/influxdata/telegraf/blob/master/docs/DATA_FORMATS_OUTPUT.md
  # data_format = "influx"
  
  ## Additional HTTP headers
  # [outputs.splunk_hec.headers]
  #   # Should be set manually to "application/json" for json data_format
  #   Content-Type = "text/plain; charset=utf-8"
```
