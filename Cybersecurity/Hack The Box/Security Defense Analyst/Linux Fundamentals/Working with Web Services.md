### 🧠 ADHD-Friendly Web Server and Command-Line Notes 🧠

---

### 🖥️ **Apache Web Server** – Your Web Traffic Controller 🚦
- **What it does:** Apache is like a **conductor** for web traffic, managing and serving web pages.
- **Why it's cool:** With Apache, you can **host websites**, secure connections with SSL, and even play around with URLs like a web wizard using **mod_rewrite** (goodbye, ugly URLs 👋).
- **How to install:**  
  ```bash
  sudo apt install apache2 -y
  ```
- **Check if it’s running:** Just hop on your browser and type **http://localhost** to see if your Apache server is live.

Imagine Apache as the **bus driver** of the web, taking your data safely from one stop (your server) to another (the client’s browser)! 🚍

---

### 🌍 **cURL** – Your Web Spyglass 🔍
- **What it does:** cURL is like having a **Swiss army knife** for data transfers. It can talk to web servers, fetch files, and **test websites** directly from the command line. 
- **How to use it:** 
  ```bash
  curl http://localhost
  ```
  This command shows you the **raw HTML code** of the page just like magic! 🎩✨

Why it rocks: It’s like a **digital magnifying glass** into the server and client’s communication. Peek under the hood without leaving your terminal. 🚀

---

### 📥 **Wget** – Your Web Download Superhero 🦸‍♂️
- **What it does:** Wget is like cURL’s sibling, but it loves **downloading** files directly to your computer.
- **How to use it:**
  ```bash
  wget http://localhost
  ```
  This grabs the file from your web server and **saves it locally**. Now you've got the entire web page stored in your system like a web collector.

Think of Wget as your trusty sidekick for **downloading files at super-speed**! 🛠️

---

### 🐍 **Python3 Web Server** – Instant Web Power ⚡
- **What it does:** With Python, you can spin up a **quick web server** in no time. It’s perfect for **quick file sharing**.
- **How to start it:**  
  ```bash
  python3 -m http.server
  ```
  This starts your own web server on port **8000**! 🎉 Perfect for **quick tests** and showing off projects.

Python's web server is like setting up your **pop-up shop** on the internet. Fast and simple! 🏪

---

These tools and commands help you **control and manipulate the web** like a pro from your terminal! Whether you're hosting websites, downloading files, or peeking into server-client conversations, you're now equipped to **master the web** in the Linux world! 🌐💻


#### Questions

Answer the question(s) below to complete this Section and earn cubes!



+ 1  Find a way to start a simple HTTP server inside Pwnbox or your local VM using "npm". Submit the command that starts the web server on port 8080 (use the short argument to specify the port number).


### "Find a way to start a simple HTTP server inside Pwnbox or your local VM using "npm". Submit the command that starts the web server on port 8080 (use the short argument to specify the port number)."

Students first need to attain the `http-server` package from [npmjs](https://www.npmjs.com/package/http-server) (the `--global` flag allows `http-server` to be run from the command line anywhere):

Code: shell

```shell
sudo npm install --global http-server
```

  Working with Web Services

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ sudo npm install --global http-server

added 11 packages, removed 1 package, changed 28 packages,
and audited 40 packages in 4s
found 0 vulnerabilities
```

Then, students can use the package and specify port 8080 to start an HTTP server with it:

Code: shell

```shell
http-server -p 8080
```

  Working with Web Services

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ http-server -p 8080

Starting up http-server, serving ./

http-server version: 14.1.0
<SNIP>
```

Answer: {hidden}


+ 0  Find a way to start a simple HTTP server inside Pwnbox or your local VM using "php". Submit the command that starts the web server on the localhost (127.0.0.1) on port 8080.

## Question 2

### "Find a way to start a simple HTTP server inside Pwnbox or your local VM using "php". Submit the command that starts the web server on the localhost (127.0.0.1) on port 8080."

Students need to either consult the man page of PHP or use the `--help` flag to find out that a web server can be started using the `-S` flag:

Code: shell

```shell
php --help | grep 'server'
```

  Working with Web Services

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ php --help | grep 'server'

  -S <addr>:<port> Run with built-in web server.
  -t <docroot>     Specify document root <docroot> for built-in web server.
```

Subsequently, students can run the server by specifying 127.0.0.1 as the address and 8080 for the port:

Code: shell

```shell
php -S 127.0.0.1:8080
```

  Working with Web Services

```shell-session
┌─[eu-academy-2]─[10.10.14.46]─[htb-ac413848@pwnbox-base]─[~]
└──╼ [★]$ php -S 127.0.0.1:8080

[Wed Mar 30 07:46:17 2022] PHP 7.4.21 Development Server
(http://127.0.0.1:8080) started
```

Answer: {hidden}