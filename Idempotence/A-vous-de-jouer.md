# A vous de jouer

[vagrant@ansible ~]$ cd ansible/projets/ema/
[vagrant@ansible ema]$ ansible all -m package -a "name=tree"
suse | CHANGED => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following NEW packages will be installed:\n  tree\n0 upgraded, 1 newly installed, 0 to remove and 2 not upgraded.\nNeed to get 47.9 kB of archives.\nAfter this operation, 116 kB of additional disk space will be used.\nGet:1 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 tree amd64 2.0.2-1 [47.9 kB]\nFetched 47.9 kB in 0s (96.8 kB/s)\nSelecting previously unselected package tree.\r\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45823 files and directories currently installed.)\r\nPreparing to unpack .../tree_2.0.2-1_amd64.deb ...\r\nUnpacking tree (2.0.2-1) ...\r\nSetting up tree (2.0.2-1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n\nRunning kernel seems to be up-to-date.\n\nNo services need to be restarted.\n\nNo containers need to be restarted.\n\nNo user sessions are running outdated binaries.\n\nNo VM guests are running outdated hypervisor (qemu) binaries on this host.\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following NEW packages will be installed:",
        "  tree",
        "0 upgraded, 1 newly installed, 0 to remove and 2 not upgraded.",
        "Need to get 47.9 kB of archives.",
        "After this operation, 116 kB of additional disk space will be used.",
        "Get:1 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 tree amd64 2.0.2-1 [47.9 kB]",
        "Fetched 47.9 kB in 0s (96.8 kB/s)",
        "Selecting previously unselected package tree.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45823 files and directories currently installed.)",
        "Preparing to unpack .../tree_2.0.2-1_amd64.deb ...",
        "Unpacking tree (2.0.2-1) ...",
        "Setting up tree (2.0.2-1) ...",
        "Processing triggers for man-db (2.10.2-1) ...",
        "",
        "Running kernel seems to be up-to-date.",
        "",
        "No services need to be restarted.",
        "",
        "No containers need to be restarted.",
        "",
        "No user sessions are running outdated binaries.",
        "",
        "No VM guests are running outdated hypervisor (qemu) binaries on this host."
    ]
}
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
debian | CHANGED => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following NEW packages will be installed:\n  tree\n0 upgraded, 1 newly installed, 0 to remove and 2 not upgraded.\nNeed to get 47.9 kB of archives.\nAfter this operation, 116 kB of additional disk space will be used.\nGet:1 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 tree amd64 2.0.2-1 [47.9 kB]\nFetched 47.9 kB in 1s (38.3 kB/s)\nSelecting previously unselected package tree.\r\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45823 files and directories currently installed.)\r\nPreparing to unpack .../tree_2.0.2-1_amd64.deb ...\r\nUnpacking tree (2.0.2-1) ...\r\nSetting up tree (2.0.2-1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n\nRunning kernel seems to be up-to-date.\n\nNo services need to be restarted.\n\nNo containers need to be restarted.\n\nNo user sessions are running outdated binaries.\n\nNo VM guests are running outdated hypervisor (qemu) binaries on this host.\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following NEW packages will be installed:",
        "  tree",
        "0 upgraded, 1 newly installed, 0 to remove and 2 not upgraded.",
        "Need to get 47.9 kB of archives.",
        "After this operation, 116 kB of additional disk space will be used.",
        "Get:1 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 tree amd64 2.0.2-1 [47.9 kB]",
        "Fetched 47.9 kB in 1s (38.3 kB/s)",
        "Selecting previously unselected package tree.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45823 files and directories currently installed.)",
        "Preparing to unpack .../tree_2.0.2-1_amd64.deb ...",
        "Unpacking tree (2.0.2-1) ...",
        "Setting up tree (2.0.2-1) ...",
        "Processing triggers for man-db (2.10.2-1) ...",
        "",
        "Running kernel seems to be up-to-date.",
        "",
        "No services need to be restarted.",
        "",
        "No containers need to be restarted.",
        "",
        "No user sessions are running outdated binaries.",
        "",
        "No VM guests are running outdated hypervisor (qemu) binaries on this host."
    ]
}


[vagrant@ansible ema]$ ansible all -m package -a "name=tree"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
debian | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
suse | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}

[vagrant@ansible ema]$ ansible all -m package -a "name=git"
debian | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
suse | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
rocky | CHANGED => {
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Installed: perl-lib-0.65-481.1.el9_6.x86_64",
        "Installed: perl-TermReadKey-2.38-11.el9.x86_64",
        "Installed: perl-DynaLoader-1.47-481.1.el9_6.x86_64",
        "Installed: perl-Error-1:0.17029-7.el9.noarch",
        "Installed: git-core-doc-2.47.3-1.el9_6.noarch",
        "Installed: perl-Git-2.47.3-1.el9_6.noarch",
        "Installed: git-2.47.3-1.el9_6.x86_64",
        "Installed: git-core-2.47.3-1.el9_6.x86_64",
        "Installed: perl-File-Find-1.37-481.1.el9_6.noarch"
    ]
}

[vagrant@ansible ema]$ ansible all -m package -a "name=git"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
suse | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
debian | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}

[vagrant@ansible ema]$ ansible all -m package -a "name=nmap"
rocky | CHANGED => {
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Installed: nmap-3:7.92-3.el9.x86_64"
    ]
}
suse | CHANGED => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following additional packages will be installed:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common\nSuggested packages:\n  liblinear-tools liblinear-dev ncat ndiff zenmap\nThe following NEW packages will be installed:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap nmap-common\n0 upgraded, 6 newly installed, 0 to remove and 2 not upgraded.\nNeed to get 6113 kB of archives.\nAfter this operation, 26.8 MB of additional disk space will be used.\nGet:1 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 libblas3 amd64 3.10.0-2ubuntu1 [228 kB]\nGet:2 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 liblinear4 amd64 2.3.0+dfsg-5 [41.4 kB]\nGet:3 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 liblua5.3-0 amd64 5.3.6-1build1 [140 kB]\nGet:4 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 lua-lpeg amd64 1.0.2-1 [31.4 kB]\nGet:5 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap-common all 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [3940 kB]\nGet:6 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap amd64 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [1731 kB]\nFetched 6113 kB in 2s (2574 kB/s)\nSelecting previously unselected package libblas3:amd64.\r\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45831 files and directories currently installed.)\r\nPreparing to unpack .../0-libblas3_3.10.0-2ubuntu1_amd64.deb ...\r\nUnpacking libblas3:amd64 (3.10.0-2ubuntu1) ...\r\nSelecting previously unselected package liblinear4:amd64.\r\nPreparing to unpack .../1-liblinear4_2.3.0+dfsg-5_amd64.deb ...\r\nUnpacking liblinear4:amd64 (2.3.0+dfsg-5) ...\r\nSelecting previously unselected package liblua5.3-0:amd64.\r\nPreparing to unpack .../2-liblua5.3-0_5.3.6-1build1_amd64.deb ...\r\nUnpacking liblua5.3-0:amd64 (5.3.6-1build1) ...\r\nSelecting previously unselected package lua-lpeg:amd64.\r\nPreparing to unpack .../3-lua-lpeg_1.0.2-1_amd64.deb ...\r\nUnpacking lua-lpeg:amd64 (1.0.2-1) ...\r\nSelecting previously unselected package nmap-common.\r\nPreparing to unpack .../4-nmap-common_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_all.deb ...\r\nUnpacking nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSelecting previously unselected package nmap.\r\nPreparing to unpack .../5-nmap_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_amd64.deb ...\r\nUnpacking nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSetting up lua-lpeg:amd64 (1.0.2-1) ...\r\nSetting up libblas3:amd64 (3.10.0-2ubuntu1) ...\r\nupdate-alternatives: using /usr/lib/x86_64-linux-gnu/blas/libblas.so.3 to provide /usr/lib/x86_64-linux-gnu/libblas.so.3 (libblas.so.3-x86_64-linux-gnu) in auto mode\r\nSetting up nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSetting up liblua5.3-0:amd64 (5.3.6-1build1) ...\r\nSetting up liblinear4:amd64 (2.3.0+dfsg-5) ...\r\nSetting up nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\nProcessing triggers for libc-bin (2.35-0ubuntu3.11) ...\r\n\nRunning kernel seems to be up-to-date.\n\nNo services need to be restarted.\n\nNo containers need to be restarted.\n\nNo user sessions are running outdated binaries.\n\nNo VM guests are running outdated hypervisor (qemu) binaries on this host.\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following additional packages will be installed:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Suggested packages:",
        "  liblinear-tools liblinear-dev ncat ndiff zenmap",
        "The following NEW packages will be installed:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap nmap-common",
        "0 upgraded, 6 newly installed, 0 to remove and 2 not upgraded.",
        "Need to get 6113 kB of archives.",
        "After this operation, 26.8 MB of additional disk space will be used.",
        "Get:1 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 libblas3 amd64 3.10.0-2ubuntu1 [228 kB]",
        "Get:2 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 liblinear4 amd64 2.3.0+dfsg-5 [41.4 kB]",
        "Get:3 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 liblua5.3-0 amd64 5.3.6-1build1 [140 kB]",
        "Get:4 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 lua-lpeg amd64 1.0.2-1 [31.4 kB]",
        "Get:5 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap-common all 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [3940 kB]",
        "Get:6 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap amd64 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [1731 kB]",
        "Fetched 6113 kB in 2s (2574 kB/s)",
        "Selecting previously unselected package libblas3:amd64.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45831 files and directories currently installed.)",
        "Preparing to unpack .../0-libblas3_3.10.0-2ubuntu1_amd64.deb ...",
        "Unpacking libblas3:amd64 (3.10.0-2ubuntu1) ...",
        "Selecting previously unselected package liblinear4:amd64.",
        "Preparing to unpack .../1-liblinear4_2.3.0+dfsg-5_amd64.deb ...",
        "Unpacking liblinear4:amd64 (2.3.0+dfsg-5) ...",
        "Selecting previously unselected package liblua5.3-0:amd64.",
        "Preparing to unpack .../2-liblua5.3-0_5.3.6-1build1_amd64.deb ...",
        "Unpacking liblua5.3-0:amd64 (5.3.6-1build1) ...",
        "Selecting previously unselected package lua-lpeg:amd64.",
        "Preparing to unpack .../3-lua-lpeg_1.0.2-1_amd64.deb ...",
        "Unpacking lua-lpeg:amd64 (1.0.2-1) ...",
        "Selecting previously unselected package nmap-common.",
        "Preparing to unpack .../4-nmap-common_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_all.deb ...",
        "Unpacking nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Selecting previously unselected package nmap.",
        "Preparing to unpack .../5-nmap_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_amd64.deb ...",
        "Unpacking nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Setting up lua-lpeg:amd64 (1.0.2-1) ...",
        "Setting up libblas3:amd64 (3.10.0-2ubuntu1) ...",
        "update-alternatives: using /usr/lib/x86_64-linux-gnu/blas/libblas.so.3 to provide /usr/lib/x86_64-linux-gnu/libblas.so.3 (libblas.so.3-x86_64-linux-gnu) in auto mode",
        "Setting up nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Setting up liblua5.3-0:amd64 (5.3.6-1build1) ...",
        "Setting up liblinear4:amd64 (2.3.0+dfsg-5) ...",
        "Setting up nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Processing triggers for man-db (2.10.2-1) ...",
        "Processing triggers for libc-bin (2.35-0ubuntu3.11) ...",
        "",
        "Running kernel seems to be up-to-date.",
        "",
        "No services need to be restarted.",
        "",
        "No containers need to be restarted.",
        "",
        "No user sessions are running outdated binaries.",
        "",
        "No VM guests are running outdated hypervisor (qemu) binaries on this host."
    ]
}
debian | CHANGED => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following additional packages will be installed:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common\nSuggested packages:\n  liblinear-tools liblinear-dev ncat ndiff zenmap\nThe following NEW packages will be installed:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap nmap-common\n0 upgraded, 6 newly installed, 0 to remove and 2 not upgraded.\nNeed to get 6113 kB of archives.\nAfter this operation, 26.8 MB of additional disk space will be used.\nGet:1 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 libblas3 amd64 3.10.0-2ubuntu1 [228 kB]\nGet:2 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 liblinear4 amd64 2.3.0+dfsg-5 [41.4 kB]\nGet:3 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 liblua5.3-0 amd64 5.3.6-1build1 [140 kB]\nGet:4 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 lua-lpeg amd64 1.0.2-1 [31.4 kB]\nGet:5 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap-common all 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [3940 kB]\nGet:6 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap amd64 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [1731 kB]\nFetched 6113 kB in 3s (1952 kB/s)\nSelecting previously unselected package libblas3:amd64.\r\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45831 files and directories currently installed.)\r\nPreparing to unpack .../0-libblas3_3.10.0-2ubuntu1_amd64.deb ...\r\nUnpacking libblas3:amd64 (3.10.0-2ubuntu1) ...\r\nSelecting previously unselected package liblinear4:amd64.\r\nPreparing to unpack .../1-liblinear4_2.3.0+dfsg-5_amd64.deb ...\r\nUnpacking liblinear4:amd64 (2.3.0+dfsg-5) ...\r\nSelecting previously unselected package liblua5.3-0:amd64.\r\nPreparing to unpack .../2-liblua5.3-0_5.3.6-1build1_amd64.deb ...\r\nUnpacking liblua5.3-0:amd64 (5.3.6-1build1) ...\r\nSelecting previously unselected package lua-lpeg:amd64.\r\nPreparing to unpack .../3-lua-lpeg_1.0.2-1_amd64.deb ...\r\nUnpacking lua-lpeg:amd64 (1.0.2-1) ...\r\nSelecting previously unselected package nmap-common.\r\nPreparing to unpack .../4-nmap-common_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_all.deb ...\r\nUnpacking nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSelecting previously unselected package nmap.\r\nPreparing to unpack .../5-nmap_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_amd64.deb ...\r\nUnpacking nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSetting up lua-lpeg:amd64 (1.0.2-1) ...\r\nSetting up libblas3:amd64 (3.10.0-2ubuntu1) ...\r\nupdate-alternatives: using /usr/lib/x86_64-linux-gnu/blas/libblas.so.3 to provide /usr/lib/x86_64-linux-gnu/libblas.so.3 (libblas.so.3-x86_64-linux-gnu) in auto mode\r\nSetting up nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nSetting up liblua5.3-0:amd64 (5.3.6-1build1) ...\r\nSetting up liblinear4:amd64 (2.3.0+dfsg-5) ...\r\nSetting up nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\nProcessing triggers for libc-bin (2.35-0ubuntu3.11) ...\r\n\nRunning kernel seems to be up-to-date.\n\nNo services need to be restarted.\n\nNo containers need to be restarted.\n\nNo user sessions are running outdated binaries.\n\nNo VM guests are running outdated hypervisor (qemu) binaries on this host.\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following additional packages will be installed:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Suggested packages:",
        "  liblinear-tools liblinear-dev ncat ndiff zenmap",
        "The following NEW packages will be installed:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap nmap-common",
        "0 upgraded, 6 newly installed, 0 to remove and 2 not upgraded.",
        "Need to get 6113 kB of archives.",
        "After this operation, 26.8 MB of additional disk space will be used.",
        "Get:1 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 libblas3 amd64 3.10.0-2ubuntu1 [228 kB]",
        "Get:2 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 liblinear4 amd64 2.3.0+dfsg-5 [41.4 kB]",
        "Get:3 http://us.archive.ubuntu.com/ubuntu jammy/main amd64 liblua5.3-0 amd64 5.3.6-1build1 [140 kB]",
        "Get:4 http://us.archive.ubuntu.com/ubuntu jammy/universe amd64 lua-lpeg amd64 1.0.2-1 [31.4 kB]",
        "Get:5 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap-common all 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [3940 kB]",
        "Get:6 http://us.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 nmap amd64 7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1 [1731 kB]",
        "Fetched 6113 kB in 3s (1952 kB/s)",
        "Selecting previously unselected package libblas3:amd64.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45831 files and directories currently installed.)",
        "Preparing to unpack .../0-libblas3_3.10.0-2ubuntu1_amd64.deb ...",
        "Unpacking libblas3:amd64 (3.10.0-2ubuntu1) ...",
        "Selecting previously unselected package liblinear4:amd64.",
        "Preparing to unpack .../1-liblinear4_2.3.0+dfsg-5_amd64.deb ...",
        "Unpacking liblinear4:amd64 (2.3.0+dfsg-5) ...",
        "Selecting previously unselected package liblua5.3-0:amd64.",
        "Preparing to unpack .../2-liblua5.3-0_5.3.6-1build1_amd64.deb ...",
        "Unpacking liblua5.3-0:amd64 (5.3.6-1build1) ...",
        "Selecting previously unselected package lua-lpeg:amd64.",
        "Preparing to unpack .../3-lua-lpeg_1.0.2-1_amd64.deb ...",
        "Unpacking lua-lpeg:amd64 (1.0.2-1) ...",
        "Selecting previously unselected package nmap-common.",
        "Preparing to unpack .../4-nmap-common_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_all.deb ...",
        "Unpacking nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Selecting previously unselected package nmap.",
        "Preparing to unpack .../5-nmap_7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1_amd64.deb ...",
        "Unpacking nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Setting up lua-lpeg:amd64 (1.0.2-1) ...",
        "Setting up libblas3:amd64 (3.10.0-2ubuntu1) ...",
        "update-alternatives: using /usr/lib/x86_64-linux-gnu/blas/libblas.so.3 to provide /usr/lib/x86_64-linux-gnu/libblas.so.3 (libblas.so.3-x86_64-linux-gnu) in auto mode",
        "Setting up nmap-common (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Setting up liblua5.3-0:amd64 (5.3.6-1build1) ...",
        "Setting up liblinear4:amd64 (2.3.0+dfsg-5) ...",
        "Setting up nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Processing triggers for man-db (2.10.2-1) ...",
        "Processing triggers for libc-bin (2.35-0ubuntu3.11) ...",
        "",
        "Running kernel seems to be up-to-date.",
        "",
        "No services need to be restarted.",
        "",
        "No containers need to be restarted.",
        "",
        "No user sessions are running outdated binaries.",
        "",
        "No VM guests are running outdated hypervisor (qemu) binaries on this host."
    ]
}

[vagrant@ansible ema]$ ansible all -m package -a "name=nmap"
rocky | SUCCESS => {
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
debian | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}
suse | SUCCESS => {
    "cache_update_time": 1761258323,
    "cache_updated": false,
    "changed": false
}


rocky | CHANGED => {
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Removed: nmap-3:7.92-3.el9.x86_64"
    ]
}
suse | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  nmap\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 4341 kB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 46717 files and directories currently installed.)\r\nRemoving nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  nmap",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 4341 kB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 46717 files and directories currently installed.)",
        "Removing nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Processing triggers for man-db (2.10.2-1) ..."
    ]
}
debian | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  nmap\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 4341 kB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 46717 files and directories currently installed.)\r\nRemoving nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  libblas3 liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  nmap",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 4341 kB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 46717 files and directories currently installed.)",
        "Removing nmap (7.91+dfsg1+really7.80+dfsg1-2ubuntu0.1) ...",
        "Processing triggers for man-db (2.10.2-1) ..."
    ]
}


[vagrant@ansible ema]$ ansible all -m package -a "name=git state=absent"
rocky | CHANGED => {
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Removed: git-2.47.3-1.el9_6.x86_64",
        "Removed: perl-Git-2.47.3-1.el9_6.noarch"
    ]
}
debian | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  git\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 18.9 MB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 46690 files and directories currently installed.)\r\nRemoving git (1:2.34.1-1ubuntu1.15) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  git",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 18.9 MB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 46690 files and directories currently installed.)",
        "Removing git (1:2.34.1-1ubuntu1.15) ..."
    ]
}
suse | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  git\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 18.9 MB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 46690 files and directories currently installed.)\r\nRemoving git (1:2.34.1-1ubuntu1.15) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  git",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 18.9 MB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 46690 files and directories currently installed.)",
        "Removing git (1:2.34.1-1ubuntu1.15) ..."
    ]
}


[vagrant@ansible ema]$ ansible all -m package -a "name=tree state=absent"
rocky | CHANGED => {
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Removed: tree-1.8.0-10.el9.x86_64"
    ]
}
suse | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  tree\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 116 kB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45898 files and directories currently installed.)\r\nRemoving tree (2.0.2-1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  tree",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 116 kB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45898 files and directories currently installed.)",
        "Removing tree (2.0.2-1) ...",
        "Processing triggers for man-db (2.10.2-1) ..."
    ]
}
debian | CHANGED => {
    "changed": true,
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Reading package lists...\nBuilding dependency tree...\nReading state information...\nThe following packages were automatically installed and are no longer required:\n  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common\nUse 'sudo apt autoremove' to remove them.\nThe following packages will be REMOVED:\n  tree\n0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.\nAfter this operation, 116 kB disk space will be freed.\n(Reading database ... \r(Reading database ... 5%\r(Reading database ... 10%\r(Reading database ... 15%\r(Reading database ... 20%\r(Reading database ... 25%\r(Reading database ... 30%\r(Reading database ... 35%\r(Reading database ... 40%\r(Reading database ... 45%\r(Reading database ... 50%\r(Reading database ... 55%\r(Reading database ... 60%\r(Reading database ... 65%\r(Reading database ... 70%\r(Reading database ... 75%\r(Reading database ... 80%\r(Reading database ... 85%\r(Reading database ... 90%\r(Reading database ... 95%\r(Reading database ... 100%\r(Reading database ... 45898 files and directories currently installed.)\r\nRemoving tree (2.0.2-1) ...\r\nProcessing triggers for man-db (2.10.2-1) ...\r\n",
    "stdout_lines": [
        "Reading package lists...",
        "Building dependency tree...",
        "Reading state information...",
        "The following packages were automatically installed and are no longer required:",
        "  git-man libblas3 liberror-perl liblinear4 liblua5.3-0 lua-lpeg nmap-common",
        "Use 'sudo apt autoremove' to remove them.",
        "The following packages will be REMOVED:",
        "  tree",
        "0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.",
        "After this operation, 116 kB disk space will be freed.",
        "(Reading database ... ",
        "(Reading database ... 5%",
        "(Reading database ... 10%",
        "(Reading database ... 15%",
        "(Reading database ... 20%",
        "(Reading database ... 25%",
        "(Reading database ... 30%",
        "(Reading database ... 35%",
        "(Reading database ... 40%",
        "(Reading database ... 45%",
        "(Reading database ... 50%",
        "(Reading database ... 55%",
        "(Reading database ... 60%",
        "(Reading database ... 65%",
        "(Reading database ... 70%",
        "(Reading database ... 75%",
        "(Reading database ... 80%",
        "(Reading database ... 85%",
        "(Reading database ... 90%",
        "(Reading database ... 95%",
        "(Reading database ... 100%",
        "(Reading database ... 45898 files and directories currently installed.)",
        "Removing tree (2.0.2-1) ...",
        "Processing triggers for man-db (2.10.2-1) ..."
    ]
}


[vagrant@ansible ema]$ cp /etc/fstab /tmp/test3.txt
[vagrant@ansible ema]$ cat /tmp/test3.txt

#
# /etc/fstab
# Created by anaconda on Fri Oct 24 19:39:48 2025
#
# Accessible filesystems, by reference, are maintained under '/dev/disk/'.
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info.
#
# After editing this file, run 'systemctl daemon-reload' to update systemd
# units generated from this file.
#
UUID=857c800e-4079-4023-b9be-38c4dc944806 /                       xfs     defaults        0 0
UUID=2635f2a2-b00d-4ea8-b7ae-83a0dbab13b1 none                    swap    defaults        0 0
#VAGRANT-BEGIN
# The contents below are automatically generated by Vagrant. Do not modify.
vagrant /vagrant vboxsf uid=1000,gid=1000,_netdev 0 0
#VAGRANT-END


[vagrant@ansible ema]$ ansible all -m copy -a "src=/etc/fstab dest=/tmp/test3.txt"
suse | CHANGED => {
    "changed": true,
    "checksum": "0fe1d6fcaf1695fb3ef9d8a42d45d04e5e0c11c2",
    "dest": "/tmp/test3.txt",
    "gid": 0,
    "group": "root",
    "md5sum": "31623c38118cbe8247061a6bd3f239a4",
    "mode": "0644",
    "owner": "root",
    "size": 679,
    "src": "/home/vagrant/.ansible/tmp/ansible-tmp-1762426739.8168974-6533-180721024625888/source",
    "state": "file",
    "uid": 0
}
debian | CHANGED => {
    "changed": true,
    "checksum": "0fe1d6fcaf1695fb3ef9d8a42d45d04e5e0c11c2",
    "dest": "/tmp/test3.txt",
    "gid": 0,
    "group": "root",
    "md5sum": "31623c38118cbe8247061a6bd3f239a4",
    "mode": "0644",
    "owner": "root",
    "size": 679,
    "src": "/home/vagrant/.ansible/tmp/ansible-tmp-1762426740.120951-6532-78956637237697/source",
    "state": "file",
    "uid": 0
}
rocky | CHANGED => {
    "changed": true,
    "checksum": "0fe1d6fcaf1695fb3ef9d8a42d45d04e5e0c11c2",
    "dest": "/tmp/test3.txt",
    "gid": 0,
    "group": "root",
    "md5sum": "31623c38118cbe8247061a6bd3f239a4",
    "mode": "0644",
    "owner": "root",
    "secontext": "unconfined_u:object_r:user_home_t:s0",
    "size": 679,
    "src": "/home/vagrant/.ansible/tmp/ansible-tmp-1762426739.5054822-6531-224572500724794/source",
    "state": "file",
    "uid": 0
}

[vagrant@ansible ema]$ ansible all -m file -a "path=/tmp/test3.txt state=absent"
suse | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}
rocky | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}
debian | CHANGED => {
    "changed": true,
    "path": "/tmp/test3.txt",
    "state": "absent"
}

[vagrant@ansible ema]$ ansible all -m command -a "df -h /"
suse | CHANGED | rc=0 >>
Filesystem                         Size  Used Avail Use% Mounted on
/dev/mapper/ubuntu--vg-ubuntu--lv   31G  5.0G   24G  18% /
rocky | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        61G  2.0G   59G   4% /
debian | CHANGED | rc=0 >>
Filesystem                         Size  Used Avail Use% Mounted on
/dev/mapper/ubuntu--vg-ubuntu--lv   31G  5.0G   24G  18% /

