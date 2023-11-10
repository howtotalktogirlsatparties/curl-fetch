# curl-fetch
A recursive bash script that fetches `curl` using `wget` which is another UNIX tool to fetch outside binaries and other things.

## What is `curl-fetch` 
It's simple, it's a bash script that fetches curl, using wget. It can't get anymore recursive than this. It also has a `reversal` mode, where you can fetch wget with curl. 

## Usage

Open up a terminal and run: 

```bash
chmod +x ./curl_fetch.sh
./curl_fetch.sh
```

## Reversal method 

Sometimes fetching curl using wget may not work, in this scenario you'll want to try using wget to fetch curl, then again retrying fetching curl using wget to the latest version:

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

## Flowchart 

![curl-fetch](https://github.com/Montana/curl-fetch/assets/20936398/8cceb847-32cd-46f5-acde-3d8441954cbe)


## Upcoming features in `curl-fetch v2.0`

* More recursiveness, so for example:

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

I'm in the process of making a newsletter to keeping you up-to-date on all the updates! 
