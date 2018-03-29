## Deprecation Notice

Ideal-Postcodes.co.uk CLI will be deprecated on May 1st 2018

# Ideal-Postcodes.co.uk CLI

Ideal Postcodes is a simple JSON API to query UK postcodes and addresses. Find out more at [Ideal-Postcodes.co.uk](https://ideal-postcodes.co.uk/)

This module provides a CLI which allows real-time log streaming and key information lookup.

The CLI requires global installation (potentially with sudo privileges, depending on your setup).

```bash
$ npm install -g ideal-postcodes-cli
```

The `idealpostcodes` script will be available in your $PATH, allowing you to perform tasks in your terminal. E.g.

```bash
$ idealpostcodes logstream -k <your_key> -s <your_secret>
```

Typically the CLI will require you to enter your api_key and secret_key. You can store your keys as environment variables to save you from having to look them up everytime.

```bash
$ export IDEALPOSTCODES_KEY="<your_key>"
$ export IDEALPOSTCODES_SECRET="<your_secret>"
$ idealpostcodes <command>
```

### Real-Time Log Streaming

The CLI allows you to listen for requests on your key in real-time, which details the request type and what kind of response was provided. This is ideal for integration and debugging.

Start listening to for incoming requests on your key with:

```bash
$ idealpostcodes logstream -k <your_key> -s <your_secret>

# -k and -s flags can be omitted if your environment variables are defined
```

Available options for `$ idealpostcodes logstream`

```bash
$ idealpostcodes logstream --json # Output logs as single line JSON objects
$ idealpostcodes logstream --quiet # Stops meta information such as connection, reconnection or disconnect messages from being written to stdout
```

Since the CLI writes to stdout, you can pipe the output to perform a range of tasks in your terminal. Some examples...

```bash
$ idealpostcodes logstream > idealpostcodes.log # Write the output to a file
$ idealpostcodes logstream | grep 'IP Address' # Write the IP address of incoming requests to console
$ idealpostcodes logstream --json --quiet | script.sh # Process raw JSON logs in a script
```

### Lookup Key Details

You can also quickly check information on your key via your terminal.

```bash
$ idealpostcodes info -k <your_key> -s <your_secret>
```

## Documentation
More documentation can be found [here](https://ideal-postcodes.co.uk/documentation/node-js)

## License

MIT