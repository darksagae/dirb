# dirb
Dirb is a command-line tool in Kali Linux used for web content scanning and directory brute-forcing. It helps security professionals find hidden resources on web servers. Here’s how to use Dirb, along with examples and expected outputs.

### Installation

Dirb is typically pre-installed in Kali Linux. If it’s not installed, you can use the following command to install it:

```bash
sudo apt update
sudo apt install dirb
```

### Basic Usage

The basic syntax for using Dirb is:

```bash
dirb <URL> [wordlist]
```

- `<URL>`: The target website URL.
- `[wordlist]`: An optional custom wordlist file to use for the scan.

### Examples

#### Example 1: Basic Directory Scan

To perform a basic directory scan using the default wordlist:

```bash
dirb http://example.com
```

**Expected Output**:
The command will scan `http://example.com` and output any found directories or files. The output might look like this:

```
---- Scanning URL: http://example.com/ ----
==> DIRECTORY: http://example.com/images/  
==> DIRECTORY: http://example.com/css/  
==> FILE: http://example.com/index.html  
```

#### Example 2: Using a Custom Wordlist

You can specify a custom wordlist for more targeted scanning. For example, using a wordlist named `custom.txt`:

```bash
dirb http://example.com /path/to/custom.txt
```

**Expected Output**:
The scan will return results based on the provided wordlist, similar to the output in Example 1, but potentially with different results depending on the contents of `custom.txt`.

#### Example 3: Using a Different User-Agent

To change the user-agent string sent in the requests (useful for bypassing certain security measures):

```bash
dirb http://example.com -u "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3"
```

**Expected Output**:
The output will show found directories, similar to previous examples, but using the specified user-agent.

#### Example 4: Recursive Scanning

To perform a recursive scan to find directories within found directories, you can use:

```bash
dirb http://example.com -r
```

**Expected Output**:
It will scan not only the base URL but also the directories found, providing a more in-depth exploration:

```
---- Scanning URL: http://example.com/images/ ----
==> DIRECTORY: http://example.com/images/thumbnails/  
```

### Conclusion

Dirb is a powerful tool for discovering hidden files and directories on web servers. By using various options and custom wordlists, you can tailor your scans to fit specific needs in your security assessments. Always ensure you have permission to scan the target website to avoid legal issues. 



                   ALTERNATIVE
Certainly, I'd be happy to provide information about how to use the dirb tool in Kali Linux, along with examples and expected outputs.

### What is dirb?

dirb is a web content scanner and discovery tool that is included in the Kali Linux distribution. It is used to find hidden web directories and files on web servers by brute-forcing URLs.

### Installation

dirb is typically pre-installed in Kali Linux, but if it's not, you can install it using the following command:

```bash
sudo apt update
sudo apt install dirb
```

### Basic Usage

The basic syntax for using dirb is:

```
dirb <url> [wordlist file(s)]
```

- `<url>`: The target URL you want to scan.
- `[wordlist file(s)]`: The wordlist(s) you want to use for the brute-force scan.

### Examples

#### Example 1: Basic Scan of a Website

```
dirb http://example.com
```

**Expected Output:**
```
-----------------
DIRB v2.22
By The Dark Raver
-----------------

START_TIME: Thu Feb 26 10:00:00 2025
URL_BASE: http://example.com/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4612

---- Scanning URL: http://example.com/ ----
+ http://example.com/index.html (CODE:200|SIZE:1270)
+ http://example.com/robots.txt (CODE:200|SIZE:17)
+ http://example.com/server-status (CODE:403|SIZE:299)

DONE - FOUND: 3 - GENERATED: 4612 - TIME_TAKEN: 0.02 seconds
```

This basic scan uses the default wordlist (`/usr/share/dirb/wordlists/common.txt`) to search for hidden directories and files on the `http://example.com` website.

#### Example 2: Scan with a Custom Wordlist

```
dirb http://example.com /path/to/custom/wordlist.txt
```

**Expected Output:**
```
-----------------
DIRB v2.22
By The Dark Raver
-----------------

START_TIME: Thu Feb 26 10:00:00 2025
URL_BASE: http://example.com/
WORDLIST_FILES: /path/to/custom/wordlist.txt

-----------------

GENERATED WORDS: 8192

---- Scanning URL: http://example.com/ ----
+ http://example.com/admin (CODE:301|SIZE:315)
+ http://example.com/backup (CODE:200|SIZE:1024)
+ http://example.com/dev (CODE:403|SIZE:296)
+ http://example.com/images (CODE:301|SIZE:312)

DONE - FOUND: 4 - GENERATED: 8192 - TIME_TAKEN: 0.05 seconds
```

This scan uses a custom wordlist located at `/path/to/custom/wordlist.txt` to search for hidden directories and files on the `http://example.com` website.

#### Example 3: Scan with Extensions

```
dirb http://example.com /usr/share/dirb/wordlists/extensions_common.txt
```

**Expected Output:**
```
-----------------
DIRB v2.22
By The Dark Raver
-----------------

START_TIME: Thu Feb 26 10:00:00 2025
URL_BASE: http://example.com/
WORDLIST_FILES: /usr/share/dirb/wordlists/extensions_common.txt

-----------------

GENERATED WORDS: 1647

---- Scanning URL: http://example.com/ ----
+ http://example.com/index.php (CODE:200|SIZE:2048)
+ http://example.com/info.php (CODE:200|SIZE:4096)
+ http://example.com/login.aspx (CODE:200|SIZE:1024)
+ http://example.com/admin.jsp (CODE:403|SIZE:299)

DONE - FOUND: 4 - GENERATED: 1647 - TIME_TAKEN: 0.03 seconds
```

This scan uses the `extensions_common.txt` wordlist, which contains common web application file extensions, to search for hidden files on the `http://example.com` website.

### Additional Options

dirb supports various other options, such as:

- `-a <agent>`: Specifies the user agent to use.
- `-r`: Follows redirects.
- `-o <output_file>`: Writes the output to a specified file.
- `-s <codes>`: Only shows specific HTTP response codes.
- `-p <proxy:port>`: Specifies a proxy to use.
- `-H <header>`: Adds a custom HTTP header.

You can find more information about the available options by running `dirb --help` in the terminal.




                                   ALTERNATIVE
### DIRB: Directory Buster Tool in Kali Linux

DIRB is a command-line tool used for brute-forcing directories and files on web servers. It is particularly useful for discovering hidden resources that may not be linked on the site.

### Installation

DIRB is usually pre-installed in Kali Linux. If it’s not available, you can install it using:

```bash
sudo apt update
sudo apt install dirb
```

### Basic Usage

The basic syntax for using DIRB is:

```bash
dirb <URL> [wordlist]
```

- `<URL>`: The target URL to scan (must include `http://` or `https://`).
- `[wordlist]`: Optional wordlist to use for directory brute-forcing. If not specified, it uses the default wordlist located in `/usr/share/dirb/wordlists/common.txt`.

### Examples

#### Example 1: Basic Directory Scan

To perform a basic directory scan on a target website:

```bash
dirb http://example.com
```

**Expected Output**: DIRB will scan the website using the default wordlist and display any found directories or files. Sample output might look like:

```
---- Scanning URL: http://example.com/ ----
==> DIRECTORY: http://example.com/admin/
==> DIRECTORY: http://example.com/images/
==> FILE: http://example.com/index.php
```

#### Example 2: Using a Custom Wordlist

To use a custom wordlist for more targeted scanning:

```bash
dirb http://example.com /path/to/your/wordlist.txt
```

**Expected Output**: Similar to the basic scan, but results will depend on the contents of the specified wordlist.

#### Example 3: Recursive Scanning

To enable recursive scanning, which will look for directories within found directories:

```bash
dirb http://example.com -r
```

**Expected Output**: This will show additional layers of directories if they are found. For example:

```
---- Scanning URL: http://example.com/ ----
==> DIRECTORY: http://example.com/admin/
==> DIRECTORY: http://example.com/admin/settings/
```

#### Example 4: Specifying HTTP Method

You can specify the HTTP method to use (GET or HEAD):

```bash
dirb http://example.com -X GET
```

**Expected Output**: Similar to the basic scan but specifically using the GET method.

### Conclusion

DIRB is a powerful tool for discovering hidden directories and files on web servers. By using different wordlists and options, you can tailor your scans to uncover valuable information for security assessments. Always ensure you have permission before scanning any web application.



                            ALTERNATIVE
Dirb is a web content scanner that looks for existing and/or hidden Web Objects (scripts, directories, files, etc.). It's a command-line tool that's part of Kali Linux. Here's how to use it along with some examples and expected outputs:

### Installation

Dirb is usually pre-installed in Kali Linux. If it's not installed, you can install it using:
```bash
sudo apt update
sudo apt install dirb
```

### Basic Usage

The basic syntax for using Dirb is:
```bash
dirb <url> [options]
```
Where `<url>` is the URL of the website you want to scan.

### Options

* `-h` or `--help`: Displays help and usage information.
* `-v` or `--verbose`: Increases the verbosity of the output.
* `-r` or `--recursive`: Recursively scans directories.
* `-X` or `--exclude`: Excludes specific file extensions from the scan.
* `-o` or `--output`: Specifies the output file name.

### Examples

#### Example 1: Basic Scan

Scan the website `http://example.com` for existing and hidden files and directories:
```bash
dirb http://example.com
```
**Expected Output:**
The command will display a list of found files and directories, including hidden ones.

#### Example 2: Recursive Scan

Recursively scan the website `http://example.com` for files and directories:
```bash
dirb http://example.com -r
```
**Expected Output:**
The command will display a list of found files and directories, including hidden ones, recursively scanned from the specified URL.

#### Example 3: Exclude Specific File Extensions

Exclude `.jpg` and `.png` files from the scan:
```bash
dirb http://example.com -X .jpg,.png
```
**Expected Output:**
The command will display a list of found files and directories, excluding `.jpg` and `.png` files.

#### Example 4: Output to a File

Scan the website `http://example.com` and save the output to a file named `scan_output.txt`:
```bash
dirb http://example.com -o scan_output.txt
```
**Expected Output:**
The command will save the scan results to the file `scan_output.txt` in the current directory.

Remember to always use Dirb with caution and respect website owners' rights and policies. Be sure to have permission to scan the website you're targeting.


                                 ALTERNATIVE
DIRB is a web content scanner used in Kali Linux to discover existing (and sometimes hidden) directories and files on a web server. It works by launching a dictionary-based attack against a web server and analyzing the HTTP responses.

### Installation

DIRB is usually pre-installed in Kali Linux. If it is not, you can install it using:

```bash
sudo apt update
sudo apt install dirb
```

### Basic Usage

The basic syntax for using DIRB is:

```bash
dirb <url> [wordlist(s)] [options]
```

*   `<url>`: The target URL you want to scan.
*   `[wordlist(s)]`: The wordlist file(s) containing common directory and file names.  If not specified, DIRB uses its internal wordlist.
*   `[options]` : Various options to customize the scan.

### Options

*   `-a <user agent>`:  Specify a custom User-Agent string.
*   `-f`: Force option. Force full TCP connections (useful when the server is slow or has connection problems).
*   `-i`:  Use case-insensitive search.
*   `-l`: Print the same URL in the output as found (useful for grep).
*   `-N <number>`:  Ignore responses with HTTP code <number>.
*   `-o <file>`:  Save output to this file.
*   `-p <proxy>`: Use this proxy.  Example: `http://[IP:port]`
*   `-r`: Don't show "Connection Refused" errors.
*   `-R`:  Recursive scan.
*   `-S`:  Silent mode. For reducing verbosity.
*   `-t <threads>`: Number of threads. Default value: 10
*   `-v`: Show also not existing pages.
*   `-w`: Don't wait between requests.
*   `-X <extensions>`: Add extension list to search (separated by slash /). Example: `-X .php/.txt/.html`
*   `-z <milliseconds>`: Add a milliseconds delay to each thread.

### Examples and Output

1.  **Basic Scan with Default Wordlist**

    To perform a basic scan using DIRB's default wordlist:

    ```bash
    dirb http://example.com
    ```

    **Example Output:**

    ```
    DIRB v2.22
    By The Dark Raver
    
    Scanning URL: http://example.com/
    
    
    + http://example.com/index.php (CODE:200|SIZE:1234)
    + http://example.com/robots.txt (CODE:200|SIZE:456)
    + http://example.com/images/ (CODE:301|SIZE:317)
    ==> DIRECTORY: http://example.com/images/
    + http://example.com/css/ (CODE:301|SIZE:317)
    ==> DIRECTORY: http://example.com/css/
    
    
    -- Scanning URL: http://example.com/images/ --
    + http://example.com/images/logo.png (CODE:200|SIZE:789)
    
    
    -- Scanning URL: http://example.com/css/ --
    + http://example.com/css/style.css (CODE:200|SIZE:1011)
    
    
    ---------------------
    END_TIME: Wed Feb 26 07:39:00 2025
    DOWNLOADED: 3637 - FOUND: 6
    ```

    This output shows that DIRB found `index.php`, `robots.txt`, `images/`, and `css/` on the target server.  It also shows the size and HTTP code of the responses.  The `==> DIRECTORY` indicates that a directory was found, and DIRB proceeds to scan that directory.
2.  **Scan with a Custom Wordlist**

    To use a custom wordlist:

    ```bash
    dirb http://example.com /usr/share/wordlists/dirb/common.txt
    ```

    This command uses the `common.txt` wordlist to scan the target. The output will be similar to the basic scan, but the results may vary depending on the contents of the wordlist.
3.  **Scan with Extensions**

    To specify file extensions to search for:

    ```bash
    dirb http://example.com -X .php/.txt/.html
    ```

    This command searches for files with the `.php`, `.txt`, and `.html` extensions.
4.  **Recursive Scan**

    To perform a recursive scan:

    ```bash
    dirb http://example.com -R
    ```

    This command tells DIRB to scan all found directories recursively. Be cautious when using this option, as it can generate a lot of traffic and take a long time to complete.
5.  **Saving Output to a File**

    To save the output to a file:

    ```bash
    dirb http://example.com -o output.txt
    ```

    This command saves the scan results to `output.txt`.
6.  **Using Multiple Threads**

    To increase the number of threads for faster scanning:

    ```bash
    dirb http://example.com -t 20
    ```

    This command uses 20 threads to perform the scan. Be careful when increasing the number of threads, as it can put a strain on the target server and potentially lead to detection.

### Notes

*   DIRB relies on wordlists, so the effectiveness of the scan depends on the quality and relevance of the wordlist used.
*   Always ensure you have permission to scan a target before running DIRB. Unauthorized scanning can be illegal.
*   DIRB generates HTTP requests, so it can be detected by intrusion detection systems (IDS) and firewalls.  Use it responsibly and ethically.
*   The output provides valuable information about the discovered directories and files, including their HTTP status codes and sizes.  Analyze this information carefully to identify potential vulnerabilities or sensitive information.
