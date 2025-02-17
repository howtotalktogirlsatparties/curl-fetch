# curl-fetch
[![Build Status](https://app.travis-ci.com/Montana/curl-fetch.svg?branch=master)](https://app.travis-ci.com/Montana/curl-fetch)

A recursive bash script that fetches `curl` using `wget` which is another UNIX tool to fetch outside binaries and other things.

<br>![curl-fetch (1)](https://github.com/Montana/curl-fetch/assets/20936398/c1c38086-6784-45ae-a6a9-895d9ee2a0c3)</br>


## What is `curl-fetch` 
It's simple, it's a bash script that fetches curl, using wget. It can't get anymore recursive than this. It also has a `reversal` mode, where you can fetch wget with curl. 

## Usage

Open up a terminal and run: 

```bash
chmod +x ./curl_fetch.sh
./curl_fetch.sh # You may want to disable TLS if this fails, just add the --without-ssl conditional. 
```
If you want TLS, you can select from these conditionals to add: 

```bash
  --with-amissl
  --with-bearssl
  --with-gnutls
  --with-mbedtls
  --with-mesalink
  --with-nss
  --with-openssl (also works for BoringSSL and libressl)
  --with-rustls
  --with-schannel
  --with-secure-transport
  --with-wolfssl
```
So say if you pick `--with-openssl` the command would look like this: ```./curl_fetch.sh --with-openssl```.

## Reversal method 

Sometimes fetching `curl` using `wget` may not work, in this scenario you'll want to try using `wget` to fetch `curl`, then again retrying fetching `curl using wget` to the latest version:

```bash
 # Set the URL for downloading wget
    WGET_URL="https://ftp.gnu.org/gnu/wget/wget-latest.tar.gz"
    WGET_TARBALL="wget.tar.gz"

    if curl -o "${WGET_TARBALL}" "${WGET_URL}"; then
        echo "wget downloaded successfully with curl. The circle is complete."
    else
        echo "Failed to download wget with curl. The irony!"
    fi
}

fetch_wget
```

## Upcoming features in `curl-fetch v2.0`

* More recursion in the script, so for example:

```bash
if wget "${CURL_URL}" -O "${CURL_TARBALL}"; then
        echo "Download complete. But wait, let's download it again for good measure!"
        download_curl
    else
        echo "Error downloading curl. But maybe it'll work if we try again?"
        download_curl
    fi
}
```

I'm in the process of making a newsletter to keeping you up-to-date on all the updates. 

# Credits

<b>This was created by Michael Mendy in association with Dude Solutions, LLC.</b>
