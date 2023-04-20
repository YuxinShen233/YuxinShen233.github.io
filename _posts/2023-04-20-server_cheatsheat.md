---
layout: post
title: Remote Server Cheatsheet
date: 2023-04-20 
description: Cheatsheet of jupyter, tmux, etc.
tags: ['python', 'tmux']
categories: codes
---

## Jupyter Notebook

1. Login your remote server.

    ```bash
    ssh username@server
    ```

2. Create a remote jupyter notebook on the server.

    ```shell
    jupyter notebook -no-browser --port=8080
    ```

3. Connect to the remote jupyter notebook in a new terminal.

    ```shell
    ssh -L 8080:localhost:8080 username@server
    ```

4. Open <https://localhost:8080> in your browser.

## Tmux

Tmux is a "terminal multiplexer", it enables a number of terminals (or windows) to be accessed and controlled from a single terminal.

1. Install [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm).
2. Install [Tmux Resurrect](https://github.com/tmux-plugins/tmux-resurrect).
3. Start a new session with the name *mysession*.

    ```shell
    tmux new -s mysession
    ```

4. Save session `Ctrl-b+Ctrl-s` and restore session `Ctrl-b+Crtl-r`.
5. Show all sessions.

   ```shell
   tmux ls
   ```

6. Kill session *mysession*.

    ```shell
    tmux kill-session -t mysession
    ```
