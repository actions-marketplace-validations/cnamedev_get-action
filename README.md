# `@cnamedev/get-action`

This GitHub Action retrieves record information from [cname.dev](https://cname.dev)

It returns the IP address and port number for a given domain.

## Inputs

### `domain`

**Required** The domain name to look up.

### `token`

**Required** Your cname.dev API token.

## Outputs

### `ip`

The IP address from the record.

### `port`

The port number from the record.

### `ip_port`

The combined IP:PORT string from the record.

## Example usage

```yaml
steps:
  - uses: cnamedev/get-action@v1.0.1
    id: cnamedev
    with:
      domain: "your-domain.example.com"
      token: ${{ secrets.CNAMED_TOKEN }}

  - name: Use the information
    run: |
      echo "IP Address: ${{ steps.cnamedev.outputs.ip }}"
      echo "Port: ${{ steps.cnamedev.outputs.port }}"
      echo "IP:Port: ${{ steps.cnamedev.outputs.ip_port }}"
```
