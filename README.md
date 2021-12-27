# DevOps-Challenge
This repo contains the source code used as part of the interview assessment for Platform (DevOps) Engineer role.

The application code itself has been sourced from https://github.com/laravel/laravel

For more information about the content about the challenge itself, please reach out to your hiring manager.

## Requirement to success

Environment = WSL2 + Docker Desktop

Tools = git, curl, terraform (if using cloud), docker, docker-compose

## Step-Step

root@xnb135-wsl:/home# git clone https://github.com/mukmin85/DevOps-Challenge.git
Cloning into 'DevOps-Challenge'...
remote: Enumerating objects: 123, done.
remote: Counting objects: 100% (123/123), done.
remote: Compressing objects: 100% (95/95), done.
remote: Total 123 (delta 9), reused 120 (delta 9), pack-reused 0
Receiving objects: 100% (123/123), 49.28 KiB | 1.82 MiB/s, done.
Resolving deltas: 100% (9/9), done.

root@xnb135-wsl:/home# cd DevOps-Challenge

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose up --build -d
Creating network "devops-challenge_app-network" with driver "bridge"
Building app
Sending build context to Docker daemon  216.1kB
Step 1/15 : FROM php:7.4-fpm
7.4-fpm: Pulling from library/php
a2abf6c4d29d: Already exists
c5608244554d: Pull complete
2d07066487a0: Pull complete
1b6dfaf1958c: Pull complete
4810cc4e8244: Pull complete
4ec287290423: Pull complete
b6ae9e23cd59: Pull complete
37c34eb562c0: Pull complete
19e84bf7fd0c: Pull complete
4fa88293240f: Pull complete
Digest: sha256:def6bdad9c31a723b903204ab2ec7f013765930026c3203bfdabf81b24b0aedf
Status: Downloaded newer image for php:7.4-fpm
 ---> 854be5bd67a6
Step 2/15 : COPY composer.json /var/www/
 ---> f08cd9284273
Step 3/15 : WORKDIR /var/www/
 ---> Running in e8782a0b5480
Removing intermediate container e8782a0b5480
 ---> 46077123fc9a
Step 4/15 : RUN apt-get update && apt-get install -y     build-essential     libpng-dev     libjpeg62-turbo-dev     libfreetype6-dev     locales     zip     jpegoptim optipng pngquant gifsicle     vim     unzip     git     curl
 ---> Running in 87358bba62c1
Get:1 http://security.debian.org/debian-security bullseye-security InRelease [44.1 kB]
Get:2 http://security.debian.org/debian-security bullseye-security/main amd64 Packages [102 kB]
Get:3 http://deb.debian.org/debian bullseye InRelease [116 kB]
Get:4 http://deb.debian.org/debian bullseye-updates InRelease [39.4 kB]
Get:5 http://deb.debian.org/debian bullseye/main amd64 Packages [8183 kB]
Get:6 http://deb.debian.org/debian bullseye-updates/main amd64 Packages [2592 B]
Fetched 8487 kB in 11s (745 kB/s)
Reading package lists...
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
  git-man less libbrotli-dev libbsd0 libc-l10n libcbor0 libcurl3-gnutls
  libcurl4 libedit2 liberror-perl libexpat1 libfido2-1 libfreetype-dev
  libfreetype6 libgpm2 libimagequant0 libjpeg62-turbo libmd0 libpng-tools
  libpng16-16 libx11-6 libx11-data libxau6 libxcb1 libxdmcp6 libxext6 libxmuu1
  openssh-client vim-common vim-runtime xauth xxd zlib1g-dev
Suggested packages:
  gettext-base git-daemon-run | git-daemon-sysvinit git-doc git-el git-email
  git-gui gitk gitweb git-cvs git-mediawiki git-svn freetype2-doc gpm keychain
  libpam-ssh monkeysphere ssh-askpass ctags vim-doc vim-scripts
The following NEW packages will be installed:
  git-man less libbrotli-dev libbsd0 libc-l10n libcbor0 libcurl3-gnutls
  libcurl4 libedit2 liberror-perl libexpat1 libfido2-1 libfreetype-dev
  libfreetype6 libgpm2 libimagequant0 libjpeg62-turbo libmd0 libpng-tools
  libpng16-16 libx11-6 libx11-data libxau6 libxcb1 libxdmcp6 libxext6 libxmuu1
  openssh-client vim-common vim-runtime xauth xxd zlib1g-dev
Suggested packages:
  gettext-base git-daemon-run | git-daemon-sysvinit git-doc git-el git-email
  git-gui gitk gitweb git-cvs git-mediawiki git-svn freetype2-doc gpm keychain
  libpam-ssh monkeysphere ssh-askpass ctags vim-doc vim-scripts
The following NEW packages will be installed:
  build-essential gifsicle git git-man jpegoptim less libbrotli-dev libbsd0
  libc-l10n libcbor0 libcurl3-gnutls libedit2 liberror-perl libexpat1
  libfido2-1 libfreetype-dev libfreetype6 libfreetype6-dev libgpm2
  libimagequant0 libjpeg62-turbo libjpeg62-turbo-dev libmd0 libpng-dev
  libpng-tools libpng16-16 libx11-6 libx11-data libxau6 libxcb1 libxdmcp6
  libxext6 libxmuu1 locales openssh-client optipng pngquant unzip vim
  vim-common vim-runtime xauth xxd zip zlib1g-dev
The following packages will be upgraded:
  curl libcurl4
2 upgraded, 45 newly installed, 0 to remove and 4 not upgraded.
Need to get 27.7 MB of archives.
After this operation, 116 MB of additional disk space will be used.
Get:1 http://deb.debian.org/debian bullseye/main amd64 less amd64 551-2 [133 kB]
Get:2 http://deb.debian.org/debian bullseye/main amd64 xxd amd64 2:8.2.2434-3+deb11u1 [192 kB]
Get:3 http://deb.debian.org/debian bullseye/main amd64 vim-common all 2:8.2.2434-3+deb11u1 [226 kB]
Get:4 http://deb.debian.org/debian bullseye/main amd64 libc-l10n all 2.31-13+deb11u2 [863 kB]
Get:5 http://deb.debian.org/debian bullseye/main amd64 locales all 2.31-13+deb11u2 [4082 kB]
Get:6 http://deb.debian.org/debian bullseye/main amd64 libmd0 amd64 1.0.3-3 [28.0 kB]
Get:7 http://deb.debian.org/debian bullseye/main amd64 libbsd0 amd64 0.11.3-1 [108 kB]
Get:8 http://deb.debian.org/debian bullseye/main amd64 libedit2 amd64 3.1-20191231-2+b1 [96.7 kB]
Get:9 http://deb.debian.org/debian bullseye/main amd64 libcbor0 amd64 0.5.0+dfsg-2 [24.0 kB]
Get:10 http://deb.debian.org/debian bullseye/main amd64 libfido2-1 amd64 1.6.0-2 [53.3 kB]
Get:11 http://deb.debian.org/debian bullseye/main amd64 openssh-client amd64 1:8.4p1-5 [929 kB]
Get:12 http://deb.debian.org/debian bullseye/main amd64 build-essential amd64 12.9 [7704 B]
Get:13 http://deb.debian.org/debian bullseye/main amd64 curl amd64 7.74.0-1.3+deb11u1 [267 kB]
Get:14 http://deb.debian.org/debian bullseye/main amd64 libcurl4 amd64 7.74.0-1.3+deb11u1 [341 kB]
Get:15 http://deb.debian.org/debian bullseye/main amd64 libxau6 amd64 1:1.0.9-1 [19.7 kB]
Get:16 http://deb.debian.org/debian bullseye/main amd64 libxdmcp6 amd64 1:1.1.2-3 [26.3 kB]
Get:17 http://deb.debian.org/debian bullseye/main amd64 libxcb1 amd64 1.14-3 [140 kB]
Get:18 http://deb.debian.org/debian bullseye/main amd64 libx11-data all 2:1.7.2-1 [311 kB]
Get:19 http://deb.debian.org/debian bullseye/main amd64 libx11-6 amd64 2:1.7.2-1 [772 kB]
Get:20 http://deb.debian.org/debian bullseye/main amd64 gifsicle amd64 1.92-2+b1 [150 kB]
Get:21 http://deb.debian.org/debian bullseye/main amd64 libcurl3-gnutls amd64 7.74.0-1.3+deb11u1 [338 kB]
Get:22 http://deb.debian.org/debian bullseye/main amd64 libexpat1 amd64 2.2.10-2 [96.9 kB]
Get:23 http://deb.debian.org/debian bullseye/main amd64 liberror-perl all 0.17029-1 [31.0 kB]
Get:24 http://deb.debian.org/debian bullseye/main amd64 git-man all 1:2.30.2-1 [1827 kB]
Get:25 http://deb.debian.org/debian bullseye/main amd64 git amd64 1:2.30.2-1 [5527 kB]
Get:26 http://deb.debian.org/debian bullseye/main amd64 libjpeg62-turbo amd64 1:2.0.6-4 [151 kB]
Get:27 http://deb.debian.org/debian bullseye/main amd64 jpegoptim amd64 1.4.6-1 [19.6 kB]
Get:28 http://deb.debian.org/debian bullseye/main amd64 libbrotli-dev amd64 1.0.9-2+b2 [288 kB]
Get:29 http://deb.debian.org/debian bullseye/main amd64 libpng16-16 amd64 1.6.37-3 [294 kB]
Get:30 http://deb.debian.org/debian bullseye/main amd64 libfreetype6 amd64 2.10.4+dfsg-1 [418 kB]
Get:31 http://deb.debian.org/debian bullseye/main amd64 zlib1g-dev amd64 1:1.2.11.dfsg-2 [190 kB]
Get:32 http://deb.debian.org/debian bullseye/main amd64 libpng-dev amd64 1.6.37-3 [298 kB]
Get:33 http://deb.debian.org/debian bullseye/main amd64 libfreetype-dev amd64 2.10.4+dfsg-1 [571 kB]
Get:34 http://deb.debian.org/debian bullseye/main amd64 libfreetype6-dev amd64 2.10.4+dfsg-1 [82.4 kB]
Get:35 http://deb.debian.org/debian bullseye/main amd64 libgpm2 amd64 1.20.7-8 [35.6 kB]
Get:36 http://deb.debian.org/debian bullseye/main amd64 libimagequant0 amd64 2.12.2-1.1 [32.5 kB]
Get:37 http://deb.debian.org/debian bullseye/main amd64 libjpeg62-turbo-dev amd64 1:2.0.6-4 [278 kB]
Get:38 http://deb.debian.org/debian bullseye/main amd64 libpng-tools amd64 1.6.37-3 [141 kB]
Get:39 http://deb.debian.org/debian bullseye/main amd64 libxext6 amd64 2:1.3.3-1.1 [52.7 kB]
Get:40 http://deb.debian.org/debian bullseye/main amd64 libxmuu1 amd64 2:1.1.2-2+b3 [23.9 kB]
Get:41 http://deb.debian.org/debian bullseye/main amd64 optipng amd64 0.7.7-1+b1 [84.7 kB]
Get:42 http://deb.debian.org/debian bullseye/main amd64 pngquant amd64 2.13.1-1 [22.1 kB]
Get:43 http://deb.debian.org/debian bullseye/main amd64 unzip amd64 6.0-26 [171 kB]
Get:44 http://deb.debian.org/debian bullseye/main amd64 vim-runtime all 2:8.2.2434-3+deb11u1 [6226 kB]
Get:45 http://deb.debian.org/debian bullseye/main amd64 vim amd64 2:8.2.2434-3+deb11u1 [1494 kB]
Get:46 http://deb.debian.org/debian bullseye/main amd64 xauth amd64 1:1.1-1 [40.5 kB]
Get:47 http://deb.debian.org/debian bullseye/main amd64 zip amd64 3.0-12 [232 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 27.7 MB in 28s (981 kB/s)
Selecting previously unselected package less.
(Reading database ... 13156 files and directories currently installed.)
Preparing to unpack .../00-less_551-2_amd64.deb ...
Unpacking less (551-2) ...
Selecting previously unselected package xxd.
Preparing to unpack .../01-xxd_2%3a8.2.2434-3+deb11u1_amd64.deb ...
Unpacking xxd (2:8.2.2434-3+deb11u1) ...
Selecting previously unselected package vim-common.
Preparing to unpack .../02-vim-common_2%3a8.2.2434-3+deb11u1_all.deb ...
Unpacking vim-common (2:8.2.2434-3+deb11u1) ...
Selecting previously unselected package libc-l10n.
Preparing to unpack .../03-libc-l10n_2.31-13+deb11u2_all.deb ...
Unpacking libc-l10n (2.31-13+deb11u2) ...
Selecting previously unselected package locales.
Preparing to unpack .../04-locales_2.31-13+deb11u2_all.deb ...
Unpacking locales (2.31-13+deb11u2) ...
Selecting previously unselected package libmd0:amd64.
Preparing to unpack .../05-libmd0_1.0.3-3_amd64.deb ...
Unpacking libmd0:amd64 (1.0.3-3) ...
Selecting previously unselected package libbsd0:amd64.
Preparing to unpack .../06-libbsd0_0.11.3-1_amd64.deb ...
Unpacking libbsd0:amd64 (0.11.3-1) ...
Selecting previously unselected package libedit2:amd64.
Preparing to unpack .../07-libedit2_3.1-20191231-2+b1_amd64.deb ...
Unpacking libedit2:amd64 (3.1-20191231-2+b1) ...
Selecting previously unselected package libcbor0:amd64.
Preparing to unpack .../08-libcbor0_0.5.0+dfsg-2_amd64.deb ...
Unpacking libcbor0:amd64 (0.5.0+dfsg-2) ...
Selecting previously unselected package libfido2-1:amd64.
Preparing to unpack .../09-libfido2-1_1.6.0-2_amd64.deb ...
Unpacking libfido2-1:amd64 (1.6.0-2) ...
Selecting previously unselected package openssh-client.
Preparing to unpack .../10-openssh-client_1%3a8.4p1-5_amd64.deb ...
Unpacking openssh-client (1:8.4p1-5) ...
Selecting previously unselected package build-essential.
Preparing to unpack .../11-build-essential_12.9_amd64.deb ...
Unpacking build-essential (12.9) ...
Preparing to unpack .../12-curl_7.74.0-1.3+deb11u1_amd64.deb ...
Unpacking curl (7.74.0-1.3+deb11u1) over (7.74.0-1.3+b1) ...
Preparing to unpack .../13-libcurl4_7.74.0-1.3+deb11u1_amd64.deb ...
Unpacking libcurl4:amd64 (7.74.0-1.3+deb11u1) over (7.74.0-1.3+b1) ...
Selecting previously unselected package libxau6:amd64.
Preparing to unpack .../14-libxau6_1%3a1.0.9-1_amd64.deb ...
Unpacking libxau6:amd64 (1:1.0.9-1) ...
Selecting previously unselected package libxdmcp6:amd64.
Preparing to unpack .../15-libxdmcp6_1%3a1.1.2-3_amd64.deb ...
Unpacking libxdmcp6:amd64 (1:1.1.2-3) ...
Selecting previously unselected package libxcb1:amd64.
Preparing to unpack .../16-libxcb1_1.14-3_amd64.deb ...
Unpacking libxcb1:amd64 (1.14-3) ...
Selecting previously unselected package libx11-data.
Preparing to unpack .../17-libx11-data_2%3a1.7.2-1_all.deb ...
Unpacking libx11-data (2:1.7.2-1) ...
Selecting previously unselected package libx11-6:amd64.
Preparing to unpack .../18-libx11-6_2%3a1.7.2-1_amd64.deb ...
Unpacking libx11-6:amd64 (2:1.7.2-1) ...
Selecting previously unselected package gifsicle.
Preparing to unpack .../19-gifsicle_1.92-2+b1_amd64.deb ...
Unpacking gifsicle (1.92-2+b1) ...
Selecting previously unselected package libcurl3-gnutls:amd64.
Preparing to unpack .../20-libcurl3-gnutls_7.74.0-1.3+deb11u1_amd64.deb ...
Unpacking libcurl3-gnutls:amd64 (7.74.0-1.3+deb11u1) ...
Selecting previously unselected package libexpat1:amd64.
Preparing to unpack .../21-libexpat1_2.2.10-2_amd64.deb ...
Unpacking libexpat1:amd64 (2.2.10-2) ...
Selecting previously unselected package liberror-perl.
Preparing to unpack .../22-liberror-perl_0.17029-1_all.deb ...
Unpacking liberror-perl (0.17029-1) ...
Selecting previously unselected package git-man.
Preparing to unpack .../23-git-man_1%3a2.30.2-1_all.deb ...
Unpacking git-man (1:2.30.2-1) ...
Selecting previously unselected package git.
Preparing to unpack .../24-git_1%3a2.30.2-1_amd64.deb ...
Unpacking git (1:2.30.2-1) ...
Selecting previously unselected package libjpeg62-turbo:amd64.
Preparing to unpack .../25-libjpeg62-turbo_1%3a2.0.6-4_amd64.deb ...
Unpacking libjpeg62-turbo:amd64 (1:2.0.6-4) ...
Selecting previously unselected package jpegoptim.
Preparing to unpack .../26-jpegoptim_1.4.6-1_amd64.deb ...
Unpacking jpegoptim (1.4.6-1) ...
Selecting previously unselected package libbrotli-dev:amd64.
Preparing to unpack .../27-libbrotli-dev_1.0.9-2+b2_amd64.deb ...
Unpacking libbrotli-dev:amd64 (1.0.9-2+b2) ...
Selecting previously unselected package libpng16-16:amd64.
Preparing to unpack .../28-libpng16-16_1.6.37-3_amd64.deb ...
Unpacking libpng16-16:amd64 (1.6.37-3) ...
Selecting previously unselected package libfreetype6:amd64.
Preparing to unpack .../29-libfreetype6_2.10.4+dfsg-1_amd64.deb ...
Unpacking libfreetype6:amd64 (2.10.4+dfsg-1) ...
Selecting previously unselected package zlib1g-dev:amd64.
Preparing to unpack .../30-zlib1g-dev_1%3a1.2.11.dfsg-2_amd64.deb ...
Unpacking zlib1g-dev:amd64 (1:1.2.11.dfsg-2) ...
Selecting previously unselected package libpng-dev:amd64.
Preparing to unpack .../31-libpng-dev_1.6.37-3_amd64.deb ...
Unpacking libpng-dev:amd64 (1.6.37-3) ...
Selecting previously unselected package libfreetype-dev:amd64.
Preparing to unpack .../32-libfreetype-dev_2.10.4+dfsg-1_amd64.deb ...
Unpacking libfreetype-dev:amd64 (2.10.4+dfsg-1) ...
Selecting previously unselected package libfreetype6-dev:amd64.
Preparing to unpack .../33-libfreetype6-dev_2.10.4+dfsg-1_amd64.deb ...
Unpacking libfreetype6-dev:amd64 (2.10.4+dfsg-1) ...
Selecting previously unselected package libgpm2:amd64.
Preparing to unpack .../34-libgpm2_1.20.7-8_amd64.deb ...
Unpacking libgpm2:amd64 (1.20.7-8) ...
Selecting previously unselected package libimagequant0:amd64.
Preparing to unpack .../35-libimagequant0_2.12.2-1.1_amd64.deb ...
Unpacking libimagequant0:amd64 (2.12.2-1.1) ...
Selecting previously unselected package libjpeg62-turbo-dev:amd64.
Preparing to unpack .../36-libjpeg62-turbo-dev_1%3a2.0.6-4_amd64.deb ...
Unpacking libjpeg62-turbo-dev:amd64 (1:2.0.6-4) ...
Selecting previously unselected package libpng-tools.
Preparing to unpack .../37-libpng-tools_1.6.37-3_amd64.deb ...
Unpacking libpng-tools (1.6.37-3) ...
Selecting previously unselected package libxext6:amd64.
Preparing to unpack .../38-libxext6_2%3a1.3.3-1.1_amd64.deb ...
Unpacking libxext6:amd64 (2:1.3.3-1.1) ...
Selecting previously unselected package libxmuu1:amd64.
Preparing to unpack .../39-libxmuu1_2%3a1.1.2-2+b3_amd64.deb ...
Unpacking libxmuu1:amd64 (2:1.1.2-2+b3) ...
Selecting previously unselected package optipng.
Preparing to unpack .../40-optipng_0.7.7-1+b1_amd64.deb ...
Unpacking optipng (0.7.7-1+b1) ...
Selecting previously unselected package pngquant.
Preparing to unpack .../41-pngquant_2.13.1-1_amd64.deb ...
Unpacking pngquant (2.13.1-1) ...
Selecting previously unselected package unzip.
Preparing to unpack .../42-unzip_6.0-26_amd64.deb ...
Unpacking unzip (6.0-26) ...
Selecting previously unselected package vim-runtime.
Preparing to unpack .../43-vim-runtime_2%3a8.2.2434-3+deb11u1_all.deb ...
Adding 'diversion of /usr/share/vim/vim82/doc/help.txt to /usr/share/vim/vim82/doc/help.txt.vim-tiny by vim-runtime'
Adding 'diversion of /usr/share/vim/vim82/doc/tags to /usr/share/vim/vim82/doc/tags.vim-tiny by vim-runtime'
Unpacking vim-runtime (2:8.2.2434-3+deb11u1) ...
Selecting previously unselected package vim.
Preparing to unpack .../44-vim_2%3a8.2.2434-3+deb11u1_amd64.deb ...
Unpacking vim (2:8.2.2434-3+deb11u1) ...
Selecting previously unselected package xauth.
Preparing to unpack .../45-xauth_1%3a1.1-1_amd64.deb ...
Unpacking xauth (1:1.1-1) ...
Selecting previously unselected package zip.
Preparing to unpack .../46-zip_3.0-12_amd64.deb ...
Unpacking zip (3.0-12) ...
Setting up libexpat1:amd64 (2.2.10-2) ...
Setting up libxau6:amd64 (1:1.0.9-1) ...
Setting up libc-l10n (2.31-13+deb11u2) ...
Setting up libgpm2:amd64 (1.20.7-8) ...
Setting up unzip (6.0-26) ...
Setting up libcbor0:amd64 (0.5.0+dfsg-2) ...
Setting up less (551-2) ...
Setting up libcurl3-gnutls:amd64 (7.74.0-1.3+deb11u1) ...
Setting up locales (2.31-13+deb11u2) ...
debconf: unable to initialize frontend: Dialog
debconf: (TERM is not set, so the dialog frontend is not usable.)
debconf: falling back to frontend: Readline
Generating locales (this might take a while)...
Generation complete.
Setting up xxd (2:8.2.2434-3+deb11u1) ...
Setting up liberror-perl (0.17029-1) ...
Setting up zip (3.0-12) ...
Setting up vim-common (2:8.2.2434-3+deb11u1) ...
Setting up libjpeg62-turbo:amd64 (1:2.0.6-4) ...
Setting up libx11-data (2:1.7.2-1) ...
Setting up libjpeg62-turbo-dev:amd64 (1:2.0.6-4) ...
Setting up libimagequant0:amd64 (2.12.2-1.1) ...
Setting up libpng16-16:amd64 (1.6.37-3) ...
Setting up zlib1g-dev:amd64 (1:1.2.11.dfsg-2) ...
Setting up libmd0:amd64 (1.0.3-3) ...
Setting up build-essential (12.9) ...
Setting up libcurl4:amd64 (7.74.0-1.3+deb11u1) ...
Setting up git-man (1:2.30.2-1) ...
Setting up curl (7.74.0-1.3+deb11u1) ...
Setting up vim-runtime (2:8.2.2434-3+deb11u1) ...
Setting up libfido2-1:amd64 (1.6.0-2) ...
Setting up libbsd0:amd64 (0.11.3-1) ...
Setting up libbrotli-dev:amd64 (1.0.9-2+b2) ...
Setting up libxdmcp6:amd64 (1:1.1.2-3) ...
Setting up libxcb1:amd64 (1.14-3) ...
Setting up vim (2:8.2.2434-3+deb11u1) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/vi.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/vi.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/vi.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/vi.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/vi.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/vi.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/vi.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/vi.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/view.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/view.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/view.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/view.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/view.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/view.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/view.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/view.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/ex.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/ex.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/ex.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/ex.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/ex.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/ex.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/ex.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/ex.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/editor (editor) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/editor.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/editor.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/editor.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/editor.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/editor.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/editor.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/editor.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/editor.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group editor) doesn't exist
Setting up libpng-tools (1.6.37-3) ...
Setting up libedit2:amd64 (3.1-20191231-2+b1) ...
Setting up libpng-dev:amd64 (1.6.37-3) ...
Setting up pngquant (2.13.1-1) ...
Setting up jpegoptim (1.4.6-1) ...
Setting up libfreetype6:amd64 (2.10.4+dfsg-1) ...
Setting up optipng (0.7.7-1+b1) ...
Setting up git (1:2.30.2-1) ...
Setting up libx11-6:amd64 (2:1.7.2-1) ...
Setting up libxmuu1:amd64 (2:1.1.2-2+b3) ...
Setting up openssh-client (1:8.4p1-5) ...
Setting up libxext6:amd64 (2:1.3.3-1.1) ...
Setting up libfreetype-dev:amd64 (2.10.4+dfsg-1) ...
Setting up xauth (1:1.1-1) ...
Setting up gifsicle (1.92-2+b1) ...
Setting up libfreetype6-dev:amd64 (2.10.4+dfsg-1) ...
Processing triggers for libc-bin (2.31-13+deb11u2) ...
Removing intermediate container 87358bba62c1
 ---> f964cb265586
Step 5/15 : RUN apt-get clean && rm -rf /var/lib/apt/lists/*
 ---> Running in a6783d4f7bd1
Removing intermediate container a6783d4f7bd1
 ---> 0cf36d34f11a
Step 6/15 : RUN docker-php-ext-install pdo_mysql exif pcntl
 ---> Running in 7b66db12adb9
Configuring for:
PHP Api Version:         20190902
Zend Module Api No:      20190902
Zend Extension Api No:   320190902
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for a sed that does not truncate output... /bin/sed
checking for pkg-config... /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking for cc... cc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables...
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether cc accepts -g... yes
checking for cc option to accept ISO C89... none needed
checking how to run the C preprocessor... cc -E
checking for icc... no
checking for suncc... no
checking for system library directory... lib
checking if compiler supports -R... no
checking if compiler supports -Wl,-rpath,... yes
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking target system type... x86_64-pc-linux-gnu
checking for PHP prefix... /usr/local
checking for PHP includes... -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib
checking for PHP extension directory... /usr/local/lib/php/extensions/no-debug-non-zts-20190902
checking for PHP installed headers prefix... /usr/local/include/php
checking if debug is enabled... no
checking if zts is enabled... no
checking for gawk... no
checking for nawk... nawk
checking if nawk is broken... no
checking for MySQL support for PDO... yes, shared
checking for the location of libz... no
checking for MySQL UNIX socket location...
checking for PDO includes... /usr/local/include/php/ext
checking for a sed that does not truncate output... /bin/sed
checking for ld used by cc... /usr/bin/ld
checking if the linker (/usr/bin/ld) is GNU ld... yes
checking for /usr/bin/ld option to reload object files... -r
checking for BSD-compatible nm... /usr/bin/nm -B
checking whether ln -s works... yes
checking how to recognize dependent libraries... pass_all
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking dlfcn.h usability... yes
checking dlfcn.h presence... yes
checking for dlfcn.h... yes
checking the maximum length of command line arguments... 1572864
checking command to parse /usr/bin/nm -B output from cc object... ok
checking for objdir... .libs
checking for ar... ar
checking for ranlib... ranlib
checking for strip... strip
checking if cc supports -fno-rtti -fno-exceptions... no
checking for cc option to produce PIC... -fPIC
^[[Bchecking if cc PIC flag -fPIC works... yes
checking if cc static flag -static works... yes
checking if cc supports -c -o file.o... yes
checking whether the cc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... no

creating libtool
appending configuration tag "CXX" to libtool
configure: patching config.h.in
configure: creating ./config.status
config.status: creating config.h
/bin/bash /usr/src/php/ext/pdo_mysql/libtool --mode=compile cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/pdo_mysql/pdo_mysql.c -o pdo_mysql.lo
mkdir .libs
 cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/pdo_mysql/pdo_mysql.c  -fPIC -DPIC -o .libs/pdo_mysql.o
/bin/bash /usr/src/php/ext/pdo_mysql/libtool --mode=compile cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/pdo_mysql/mysql_driver.c -o mysql_driver.lo
 cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/pdo_mysql/mysql_driver.c  -fPIC -DPIC -o .libs/mysql_driver.o
/bin/bash /usr/src/php/ext/pdo_mysql/libtool --mode=compile cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/pdo_mysql/mysql_statement.c -o mysql_statement.lo
 cc -I/usr/local/include/php/ext -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pdo_mysql -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/pdo_mysql/mysql_statement.c  -fPIC -DPIC -o .libs/mysql_statement.o
/bin/bash /usr/src/php/ext/pdo_mysql/libtool --mode=link cc -DPHP_ATOM_INC -I/usr/src/php/ext/pdo_mysql/include -I/usr/src/php/ext/pdo_mysql/main -I/usr/src/php/ext/pdo_mysql -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64  -Wl,-O1 -pie  -o pdo_mysql.la -export-dynamic -avoid-version -prefer-pic -module -rpath /usr/src/php/ext/pdo_mysql/modules  pdo_mysql.lo mysql_driver.lo mysql_statement.lo
cc -shared  .libs/pdo_mysql.o .libs/mysql_driver.o .libs/mysql_statement.o   -Wl,-O1 -Wl,-soname -Wl,pdo_mysql.so -o .libs/pdo_mysql.so
creating pdo_mysql.la
(cd .libs && rm -f pdo_mysql.la && ln -s ../pdo_mysql.la pdo_mysql.la)
/bin/bash /usr/src/php/ext/pdo_mysql/libtool --mode=install cp ./pdo_mysql.la /usr/src/php/ext/pdo_mysql/modules
cp ./.libs/pdo_mysql.so /usr/src/php/ext/pdo_mysql/modules/pdo_mysql.so
cp ./.libs/pdo_mysql.lai /usr/src/php/ext/pdo_mysql/modules/pdo_mysql.la
PATH="$PATH:/sbin" ldconfig -n /usr/src/php/ext/pdo_mysql/modules
----------------------------------------------------------------------
Libraries have been installed in:
   /usr/src/php/ext/pdo_mysql/modules

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,--rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------

Build complete.
Don't forget to run 'make test'.

+ strip --strip-all modules/pdo_mysql.so
Installing shared extensions:     /usr/local/lib/php/extensions/no-debug-non-zts-20190902/
find . -name \*.gcno -o -name \*.gcda | xargs rm -f
find . -name \*.lo -o -name \*.o | xargs rm -f
find . -name \*.la -o -name \*.a | xargs rm -f
find . -name \*.so | xargs rm -f
find . -name .libs -a -type d|xargs rm -rf
rm -f libphp.la      modules/* libs/*
Configuring for:
PHP Api Version:         20190902
Zend Module Api No:      20190902
Zend Extension Api No:   320190902
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for a sed that does not truncate output... /bin/sed
checking for pkg-config... /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking for cc... cc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables...
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether cc accepts -g... yes
checking for cc option to accept ISO C89... none needed
checking how to run the C preprocessor... cc -E
checking for icc... no
checking for suncc... no
checking for system library directory... lib
checking if compiler supports -R... no
checking if compiler supports -Wl,-rpath,... yes
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking target system type... x86_64-pc-linux-gnu
checking for PHP prefix... /usr/local
checking for PHP includes... -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib
checking for PHP extension directory... /usr/local/lib/php/extensions/no-debug-non-zts-20190902
checking for PHP installed headers prefix... /usr/local/include/php
checking if debug is enabled... no
checking if zts is enabled... no
checking for gawk... no
checking for nawk... nawk
checking if nawk is broken... no
checking whether to enable EXIF (metadata from images) support... yes, shared
checking for a sed that does not truncate output... /bin/sed
checking for ld used by cc... /usr/bin/ld
checking if the linker (/usr/bin/ld) is GNU ld... yes
checking for /usr/bin/ld option to reload object files... -r
checking for BSD-compatible nm... /usr/bin/nm -B
checking whether ln -s works... yes
checking how to recognize dependent libraries... pass_all
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking dlfcn.h usability... yes
checking dlfcn.h presence... yes
checking for dlfcn.h... yes
checking the maximum length of command line arguments... 1572864
checking command to parse /usr/bin/nm -B output from cc object... ok
checking for objdir... .libs
checking for ar... ar
checking for ranlib... ranlib
checking for strip... strip
checking if cc supports -fno-rtti -fno-exceptions... no
checking for cc option to produce PIC... -fPIC
checking if cc PIC flag -fPIC works... yes
checking if cc static flag -static works... yes
checking if cc supports -c -o file.o... yes
checking whether the cc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... no

creating libtool
appending configuration tag "CXX" to libtool
configure: patching config.h.in
configure: creating ./config.status
config.status: creating config.h
/bin/bash /usr/src/php/ext/exif/libtool --mode=compile cc -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/exif -DPHP_ATOM_INC -I/usr/src/php/ext/exif/include -I/usr/src/php/ext/exif/main -I/usr/src/php/ext/exif -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/exif/exif.c -o exif.lo
mkdir .libs
 cc -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/exif -DPHP_ATOM_INC -I/usr/src/php/ext/exif/include -I/usr/src/php/ext/exif/main -I/usr/src/php/ext/exif -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/exif/exif.c  -fPIC -DPIC -o .libs/exif.o
/bin/bash /usr/src/php/ext/exif/libtool --mode=link cc -DPHP_ATOM_INC -I/usr/src/php/ext/exif/include -I/usr/src/php/ext/exif/main -I/usr/src/php/ext/exif -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64  -Wl,-O1 -pie  -o exif.la -export-dynamic -avoid-version -prefer-pic -module -rpath /usr/src/php/ext/exif/modules  exif.lo
cc -shared  .libs/exif.o   -Wl,-O1 -Wl,-soname -Wl,exif.so -o .libs/exif.so
creating exif.la
(cd .libs && rm -f exif.la && ln -s ../exif.la exif.la)
/bin/bash /usr/src/php/ext/exif/libtool --mode=install cp ./exif.la /usr/src/php/ext/exif/modules
cp ./.libs/exif.so /usr/src/php/ext/exif/modules/exif.so
cp ./.libs/exif.lai /usr/src/php/ext/exif/modules/exif.la
PATH="$PATH:/sbin" ldconfig -n /usr/src/php/ext/exif/modules
----------------------------------------------------------------------
Libraries have been installed in:
   /usr/src/php/ext/exif/modules

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,--rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------

Build complete.
Don't forget to run 'make test'.

+ strip --strip-all modules/exif.so
Installing shared extensions:     /usr/local/lib/php/extensions/no-debug-non-zts-20190902/
find . -name \*.gcno -o -name \*.gcda | xargs rm -f
find . -name \*.lo -o -name \*.o | xargs rm -f
find . -name \*.la -o -name \*.a | xargs rm -f
find . -name \*.so | xargs rm -f
find . -name .libs -a -type d|xargs rm -rf
rm -f libphp.la      modules/* libs/*
Configuring for:
PHP Api Version:         20190902
Zend Module Api No:      20190902
Zend Extension Api No:   320190902
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for a sed that does not truncate output... /bin/sed
checking for pkg-config... /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking for cc... cc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables...
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether cc accepts -g... yes
checking for cc option to accept ISO C89... none needed
checking how to run the C preprocessor... cc -E
checking for icc... no
checking for suncc... no
checking for system library directory... lib
checking if compiler supports -R... no
checking if compiler supports -Wl,-rpath,... yes
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking target system type... x86_64-pc-linux-gnu
checking for PHP prefix... /usr/local
checking for PHP includes... -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib
checking for PHP extension directory... /usr/local/lib/php/extensions/no-debug-non-zts-20190902
checking for PHP installed headers prefix... /usr/local/include/php
checking if debug is enabled... no
checking if zts is enabled... no
checking for gawk... no
checking for nawk... nawk
checking if nawk is broken... no
checking whether to enable pcntl support... yes, shared
checking for fork... yes
checking for waitpid... yes
checking for sigaction... yes
checking for getpriority... yes
checking for setpriority... yes
checking for wait3... yes
checking for wait4... yes
checking for sigwaitinfo... yes
checking for sigtimedwait... yes
checking for unshare... yes
checking for siginfo_t... yes
checking for a sed that does not truncate output... /bin/sed
checking for ld used by cc... /usr/bin/ld
checking if the linker (/usr/bin/ld) is GNU ld... yes
checking for /usr/bin/ld option to reload object files... -r
checking for BSD-compatible nm... /usr/bin/nm -B
checking whether ln -s works... yes
checking how to recognize dependent libraries... pass_all
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking dlfcn.h usability... yes
checking dlfcn.h presence... yes
checking for dlfcn.h... yes
checking the maximum length of command line arguments... 1572864
checking command to parse /usr/bin/nm -B output from cc object... ok
checking for objdir... .libs
checking for ar... ar
checking for ranlib... ranlib
checking for strip... strip
checking if cc supports -fno-rtti -fno-exceptions... no
checking for cc option to produce PIC... -fPIC
checking if cc PIC flag -fPIC works... yes
checking if cc static flag -static works... yes
checking if cc supports -c -o file.o... yes
checking whether the cc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... no

creating libtool
appending configuration tag "CXX" to libtool
configure: patching config.h.in
configure: creating ./config.status
config.status: creating config.h
/bin/bash /usr/src/php/ext/pcntl/libtool --mode=compile cc -DHAVE_STRUCT_SIGINFO_T -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pcntl -DPHP_ATOM_INC -I/usr/src/php/ext/pcntl/include -I/usr/src/php/ext/pcntl/main -I/usr/src/php/ext/pcntl -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/pcntl/pcntl.c -o pcntl.lo
mkdir .libs
 cc -DHAVE_STRUCT_SIGINFO_T -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pcntl -DPHP_ATOM_INC -I/usr/src/php/ext/pcntl/include -I/usr/src/php/ext/pcntl/main -I/usr/src/php/ext/pcntl -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/pcntl/pcntl.c  -fPIC -DPIC -o .libs/pcntl.o
/bin/bash /usr/src/php/ext/pcntl/libtool --mode=compile cc -DHAVE_STRUCT_SIGINFO_T -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pcntl -DPHP_ATOM_INC -I/usr/src/php/ext/pcntl/include -I/usr/src/php/ext/pcntl/main -I/usr/src/php/ext/pcntl -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64   -c /usr/src/php/ext/pcntl/php_signal.c -o php_signal.lo
 cc -DHAVE_STRUCT_SIGINFO_T -DZEND_ENABLE_STATIC_TSRMLS_CACHE=1 -I. -I/usr/src/php/ext/pcntl -DPHP_ATOM_INC -I/usr/src/php/ext/pcntl/include -I/usr/src/php/ext/pcntl/main -I/usr/src/php/ext/pcntl -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -c /usr/src/php/ext/pcntl/php_signal.c  -fPIC -DPIC -o .libs/php_signal.o
/bin/bash /usr/src/php/ext/pcntl/libtool --mode=link cc -DPHP_ATOM_INC -I/usr/src/php/ext/pcntl/include -I/usr/src/php/ext/pcntl/main -I/usr/src/php/ext/pcntl -I/usr/local/include/php -I/usr/local/include/php/main -I/usr/local/include/php/TSRM -I/usr/local/include/php/Zend -I/usr/local/include/php/ext -I/usr/local/include/php/ext/date/lib  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64 -DHAVE_CONFIG_H  -fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64  -Wl,-O1 -pie  -o pcntl.la -export-dynamic -avoid-version -prefer-pic -module -rpath /usr/src/php/ext/pcntl/modules  pcntl.lo php_signal.lo
cc -shared  .libs/pcntl.o .libs/php_signal.o   -Wl,-O1 -Wl,-soname -Wl,pcntl.so -o .libs/pcntl.so
creating pcntl.la
(cd .libs && rm -f pcntl.la && ln -s ../pcntl.la pcntl.la)
/bin/bash /usr/src/php/ext/pcntl/libtool --mode=install cp ./pcntl.la /usr/src/php/ext/pcntl/modules
cp ./.libs/pcntl.so /usr/src/php/ext/pcntl/modules/pcntl.so
cp ./.libs/pcntl.lai /usr/src/php/ext/pcntl/modules/pcntl.la
PATH="$PATH:/sbin" ldconfig -n /usr/src/php/ext/pcntl/modules
----------------------------------------------------------------------
Libraries have been installed in:
   /usr/src/php/ext/pcntl/modules

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,--rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------

Build complete.
Don't forget to run 'make test'.

+ strip --strip-all modules/pcntl.so
Installing shared extensions:     /usr/local/lib/php/extensions/no-debug-non-zts-20190902/
find . -name \*.gcno -o -name \*.gcda | xargs rm -f
find . -name \*.lo -o -name \*.o | xargs rm -f
find . -name \*.la -o -name \*.a | xargs rm -f
find . -name \*.so | xargs rm -f
find . -name .libs -a -type d|xargs rm -rf
rm -f libphp.la      modules/* libs/*
Removing intermediate container 7b66db12adb9
 ---> a9886c90eb5d
Step 7/15 : RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
 ---> Running in 7c660ba3282f
All settings correct for using Composer
Downloading...

Composer (version 2.2.1) successfully installed to: /usr/local/bin/composer
Use it: php /usr/local/bin/composer

Removing intermediate container 7c660ba3282f
 ---> 4234b7f43f7c
Step 8/15 : RUN groupadd -g 1000 www
 ---> Running in 17fb1a0ba776
Removing intermediate container 17fb1a0ba776
 ---> 05a43cef5371
Step 9/15 : RUN useradd -u 1000 -ms /bin/bash -g www www
 ---> Running in 70eb0ff5b63e
Removing intermediate container 70eb0ff5b63e
 ---> f76fa02e0053
Step 10/15 : COPY . /var/www/
 ---> 56a50469ca68
Step 11/15 : RUN composer install
 ---> Running in 61bc7c454a33
No composer.lock file present. Updating dependencies to latest instead of installing from lock file. See https://getcomposer.org/install for more information.
Loading composer repositories with package information
Updating dependencies
Lock file operations: 110 installs, 0 updates, 0 removals
  - Locking asm89/stack-cors (v2.0.3)
  - Locking brick/math (0.9.3)
  - Locking dflydev/dot-access-data (v3.0.1)
  - Locking doctrine/inflector (2.0.4)
  - Locking doctrine/instantiator (1.4.0)
  - Locking doctrine/lexer (1.2.1)
  - Locking dragonmantank/cron-expression (v3.1.0)
  - Locking egulias/email-validator (2.1.25)
  - Locking facade/flare-client-php (1.9.1)
  - Locking facade/ignition (2.17.3)
  - Locking facade/ignition-contracts (1.0.2)
  - Locking fakerphp/faker (v1.17.0)
  - Locking filp/whoops (2.14.4)
  - Locking fruitcake/laravel-cors (v2.0.4)
  - Locking graham-campbell/result-type (v1.0.4)
  - Locking guzzlehttp/guzzle (7.4.1)
  - Locking guzzlehttp/promises (1.5.1)
  - Locking guzzlehttp/psr7 (2.1.0)
  - Locking hamcrest/hamcrest-php (v2.0.1)
  - Locking laravel/framework (v8.77.1)
  - Locking laravel/sail (v1.12.12)
  - Locking laravel/sanctum (v2.13.0)
  - Locking laravel/serializable-closure (v1.0.5)
  - Locking laravel/tinker (v2.6.3)
  - Locking league/commonmark (2.1.0)
  - Locking league/config (v1.1.1)
  - Locking league/flysystem (1.1.9)
  - Locking league/mime-type-detection (1.9.0)
  - Locking mockery/mockery (1.4.4)
  - Locking monolog/monolog (2.3.5)
  - Locking myclabs/deep-copy (1.10.2)
  - Locking nesbot/carbon (2.55.2)
  - Locking nette/schema (v1.2.2)
  - Locking nette/utils (v3.2.6)
  - Locking nikic/php-parser (v4.13.2)
  - Locking nunomaduro/collision (v5.10.0)
  - Locking opis/closure (3.6.2)
  - Locking phar-io/manifest (2.0.3)
  - Locking phar-io/version (3.1.0)
  - Locking phpdocumentor/reflection-common (2.2.0)
  - Locking phpdocumentor/reflection-docblock (5.3.0)
  - Locking phpdocumentor/type-resolver (1.5.1)
  - Locking phpoption/phpoption (1.8.1)
  - Locking phpspec/prophecy (v1.15.0)
  - Locking phpunit/php-code-coverage (9.2.10)
  - Locking phpunit/php-file-iterator (3.0.6)
  - Locking phpunit/php-invoker (3.1.1)
  - Locking phpunit/php-text-template (2.0.4)
  - Locking phpunit/php-timer (5.0.3)
  - Locking phpunit/phpunit (9.5.11)
  - Locking psr/container (1.1.2)
  - Locking psr/event-dispatcher (1.0.0)
  - Locking psr/http-client (1.0.1)
  - Locking psr/http-factory (1.0.1)
  - Locking psr/http-message (1.0.1)
  - Locking psr/log (1.1.4)
  - Locking psr/simple-cache (1.0.1)
  - Locking psy/psysh (v0.10.12)
  - Locking ralouphie/getallheaders (3.0.3)
  - Locking ramsey/collection (1.2.2)
  - Locking ramsey/uuid (4.2.3)
  - Locking sebastian/cli-parser (1.0.1)
  - Locking sebastian/code-unit (1.0.8)
  - Locking sebastian/code-unit-reverse-lookup (2.0.3)
  - Locking sebastian/comparator (4.0.6)
  - Locking sebastian/complexity (2.0.2)
  - Locking sebastian/diff (4.0.4)
  - Locking sebastian/environment (5.1.3)
  - Locking sebastian/exporter (4.0.4)
  - Locking sebastian/global-state (5.0.3)
  - Locking sebastian/lines-of-code (1.0.3)
  - Locking sebastian/object-enumerator (4.0.4)
  - Locking sebastian/object-reflector (2.0.4)
  - Locking sebastian/recursion-context (4.0.4)
  - Locking sebastian/resource-operations (3.0.3)
  - Locking sebastian/type (2.3.4)
  - Locking sebastian/version (3.0.2)
  - Locking swiftmailer/swiftmailer (v6.3.0)
  - Locking symfony/console (v5.4.1)
  - Locking symfony/css-selector (v5.4.0)
  - Locking symfony/deprecation-contracts (v2.5.0)
  - Locking symfony/error-handler (v5.4.1)
  - Locking symfony/event-dispatcher (v5.4.0)
  - Locking symfony/event-dispatcher-contracts (v2.5.0)
  - Locking symfony/finder (v5.4.0)
  - Locking symfony/http-foundation (v5.4.1)
  - Locking symfony/http-kernel (v5.4.1)
  - Locking symfony/mime (v5.4.0)
  - Locking symfony/polyfill-ctype (v1.23.0)
  - Locking symfony/polyfill-iconv (v1.23.0)
  - Locking symfony/polyfill-intl-grapheme (v1.23.1)
  - Locking symfony/polyfill-intl-idn (v1.23.0)
  - Locking symfony/polyfill-intl-normalizer (v1.23.0)
  - Locking symfony/polyfill-mbstring (v1.23.1)
  - Locking symfony/polyfill-php72 (v1.23.0)
  - Locking symfony/polyfill-php73 (v1.23.0)
  - Locking symfony/polyfill-php80 (v1.23.1)
  - Locking symfony/polyfill-php81 (v1.23.0)
  - Locking symfony/process (v5.4.0)
  - Locking symfony/routing (v5.4.0)
  - Locking symfony/service-contracts (v2.5.0)
  - Locking symfony/string (v5.4.0)
  - Locking symfony/translation (v5.4.1)
  - Locking symfony/translation-contracts (v2.5.0)
  - Locking symfony/var-dumper (v5.4.1)
  - Locking theseer/tokenizer (1.2.1)
  - Locking tijsverkoyen/css-to-inline-styles (2.2.4)
  - Locking vlucas/phpdotenv (v5.4.1)
  - Locking voku/portable-ascii (1.5.6)
  - Locking webmozart/assert (1.10.0)
Writing lock file
Installing dependencies from lock file (including require-dev)
Package operations: 110 installs, 0 updates, 0 removals
  - Downloading doctrine/inflector (2.0.4)
  - Downloading doctrine/lexer (1.2.1)
  - Downloading symfony/polyfill-ctype (v1.23.0)
  - Downloading webmozart/assert (1.10.0)
  - Downloading dragonmantank/cron-expression (v3.1.0)
  - Downloading symfony/polyfill-php80 (v1.23.1)
  - Downloading symfony/polyfill-mbstring (v1.23.1)
  - Downloading symfony/var-dumper (v5.4.1)
  - Downloading symfony/polyfill-intl-normalizer (v1.23.0)
  - Downloading symfony/polyfill-intl-grapheme (v1.23.1)
  - Downloading symfony/string (v5.4.0)
  - Downloading symfony/deprecation-contracts (v2.5.0)
  - Downloading psr/container (1.1.2)
  - Downloading symfony/service-contracts (v2.5.0)
  - Downloading symfony/polyfill-php73 (v1.23.0)
  - Downloading symfony/console (v5.4.1)
  - Downloading psr/log (1.1.4)
  - Downloading monolog/monolog (2.3.5)
  - Downloading voku/portable-ascii (1.5.6)
  - Downloading phpoption/phpoption (1.8.1)
  - Downloading graham-campbell/result-type (v1.0.4)
  - Downloading vlucas/phpdotenv (v5.4.1)
  - Downloading symfony/css-selector (v5.4.0)
  - Downloading tijsverkoyen/css-to-inline-styles (2.2.4)
  - Downloading symfony/routing (v5.4.0)
  - Downloading symfony/process (v5.4.0)
  - Downloading symfony/polyfill-php72 (v1.23.0)
  - Downloading symfony/polyfill-intl-idn (v1.23.0)
  - Downloading symfony/mime (v5.4.0)
  - Downloading symfony/http-foundation (v5.4.1)
  - Downloading psr/event-dispatcher (1.0.0)
  - Downloading symfony/event-dispatcher-contracts (v2.5.0)
  - Downloading symfony/event-dispatcher (v5.4.0)
  - Downloading symfony/error-handler (v5.4.1)
  - Downloading symfony/http-kernel (v5.4.1)
  - Downloading symfony/finder (v5.4.0)
  - Downloading symfony/polyfill-iconv (v1.23.0)
  - Downloading egulias/email-validator (2.1.25)
  - Downloading swiftmailer/swiftmailer (v6.3.0)
  - Downloading symfony/polyfill-php81 (v1.23.0)
  - Downloading ramsey/collection (1.2.2)
  - Downloading brick/math (0.9.3)
  - Downloading ramsey/uuid (4.2.3)
  - Downloading psr/simple-cache (1.0.1)
  - Downloading opis/closure (3.6.2)
  - Downloading symfony/translation-contracts (v2.5.0)
  - Downloading symfony/translation (v5.4.1)
  - Downloading nesbot/carbon (2.55.2)
  - Downloading league/mime-type-detection (1.9.0)
  - Downloading league/flysystem (1.1.9)
  - Downloading nette/utils (v3.2.6)
  - Downloading nette/schema (v1.2.2)
  - Downloading dflydev/dot-access-data (v3.0.1)
  - Downloading league/config (v1.1.1)
  - Downloading league/commonmark (2.1.0)
  - Downloading laravel/serializable-closure (v1.0.5)
  - Downloading laravel/framework (v8.77.1)
  - Downloading facade/ignition-contracts (1.0.2)
  - Downloading facade/flare-client-php (1.9.1)
  - Downloading facade/ignition (2.17.3)
  - Downloading fakerphp/faker (v1.17.0)
  - Downloading asm89/stack-cors (v2.0.3)
  - Downloading fruitcake/laravel-cors (v2.0.4)
  - Downloading psr/http-message (1.0.1)
  - Downloading psr/http-client (1.0.1)
  - Downloading ralouphie/getallheaders (3.0.3)
  - Downloading psr/http-factory (1.0.1)
  - Downloading guzzlehttp/psr7 (2.1.0)
  - Downloading guzzlehttp/promises (1.5.1)
  - Downloading guzzlehttp/guzzle (7.4.1)
  - Downloading laravel/sail (v1.12.12)
  - Downloading laravel/sanctum (v2.13.0)
  - Downloading nikic/php-parser (v4.13.2)
  - Downloading psy/psysh (v0.10.12)
  - Downloading laravel/tinker (v2.6.3)
  - Downloading hamcrest/hamcrest-php (v2.0.1)
  - Downloading mockery/mockery (1.4.4)
  - Downloading filp/whoops (2.14.4)
  - Downloading nunomaduro/collision (v5.10.0)
  - Downloading phpdocumentor/reflection-common (2.2.0)
  - Downloading phpdocumentor/type-resolver (1.5.1)
  - Downloading phpdocumentor/reflection-docblock (5.3.0)
  - Downloading sebastian/version (3.0.2)
  - Downloading sebastian/type (2.3.4)
  - Downloading sebastian/resource-operations (3.0.3)
  - Downloading sebastian/recursion-context (4.0.4)
  - Downloading sebastian/object-reflector (2.0.4)
  - Downloading sebastian/object-enumerator (4.0.4)
  - Downloading sebastian/global-state (5.0.3)
  - Downloading sebastian/exporter (4.0.4)
  - Downloading sebastian/environment (5.1.3)
  - Downloading sebastian/diff (4.0.4)
  - Downloading sebastian/comparator (4.0.6)
  - Downloading sebastian/code-unit (1.0.8)
  - Downloading sebastian/cli-parser (1.0.1)
  - Downloading phpunit/php-timer (5.0.3)
  - Downloading phpunit/php-text-template (2.0.4)
  - Downloading phpunit/php-invoker (3.1.1)
  - Downloading phpunit/php-file-iterator (3.0.6)
  - Downloading theseer/tokenizer (1.2.1)
  - Downloading sebastian/lines-of-code (1.0.3)
  - Downloading sebastian/complexity (2.0.2)
  - Downloading sebastian/code-unit-reverse-lookup (2.0.3)
  - Downloading phpunit/php-code-coverage (9.2.10)
  - Downloading doctrine/instantiator (1.4.0)
  - Downloading phpspec/prophecy (v1.15.0)
  - Downloading phar-io/version (3.1.0)
  - Downloading phar-io/manifest (2.0.3)
  - Downloading myclabs/deep-copy (1.10.2)
  - Downloading phpunit/phpunit (9.5.11)
   0/110 [>---------------------------]   0%
   7/110 [=>--------------------------]   6%
   9/110 [==>-------------------------]   8%
  11/110 [==>-------------------------]  10%
  13/110 [===>------------------------]  11%
  16/110 [====>-----------------------]  14%
  18/110 [====>-----------------------]  16%
  21/110 [=====>----------------------]  19%
  22/110 [=====>----------------------]  20%
  25/110 [======>---------------------]  22%
  27/110 [======>---------------------]  24%
  28/110 [=======>--------------------]  25%
  29/110 [=======>--------------------]  26%
  30/110 [=======>--------------------]  27%
  33/110 [========>-------------------]  30%
  35/110 [========>-------------------]  31%
  42/110 [==========>-----------------]  38%
  44/110 [===========>----------------]  40%
  45/110 [===========>----------------]  40%
  47/110 [===========>----------------]  42%
  49/110 [============>---------------]  44%
  53/110 [=============>--------------]  48%
  54/110 [=============>--------------]  49%
  55/110 [==============>-------------]  50%
  56/110 [==============>-------------]  50%
  57/110 [==============>-------------]  51%
  58/110 [==============>-------------]  52%
  62/110 [===============>------------]  56%
  63/110 [================>-----------]  57%
  64/110 [================>-----------]  58%
  65/110 [================>-----------]  59%
  66/110 [================>-----------]  60%
  67/110 [=================>----------]  60%
  68/110 [=================>----------]  61%
  70/110 [=================>----------]  63%
  71/110 [==================>---------]  64%
  73/110 [==================>---------]  66%
  74/110 [==================>---------]  67%
  75/110 [===================>--------]  68%
  76/110 [===================>--------]  69%
  77/110 [===================>--------]  70%
  82/110 [====================>-------]  74%
  84/110 [=====================>------]  76%
  85/110 [=====================>------]  77%
  87/110 [======================>-----]  79%
  88/110 [======================>-----]  80%
  89/110 [======================>-----]  80%
  92/110 [=======================>----]  83%
  93/110 [=======================>----]  84%
  95/110 [========================>---]  86%
  96/110 [========================>---]  87%
  97/110 [========================>---]  88%
  99/110 [=========================>--]  90%
 103/110 [==========================>-]  93%
 104/110 [==========================>-]  94%
 107/110 [===========================>]  97%
 108/110 [===========================>]  98%
 109/110 [===========================>]  99%
 110/110 [============================] 100%
  - Installing doctrine/inflector (2.0.4): Extracting archive
  - Installing doctrine/lexer (1.2.1): Extracting archive
  - Installing symfony/polyfill-ctype (v1.23.0): Extracting archive
  - Installing webmozart/assert (1.10.0): Extracting archive
  - Installing dragonmantank/cron-expression (v3.1.0): Extracting archive
  - Installing symfony/polyfill-php80 (v1.23.1): Extracting archive
  - Installing symfony/polyfill-mbstring (v1.23.1): Extracting archive
  - Installing symfony/var-dumper (v5.4.1): Extracting archive
  - Installing symfony/polyfill-intl-normalizer (v1.23.0): Extracting archive
  - Installing symfony/polyfill-intl-grapheme (v1.23.1): Extracting archive
  - Installing symfony/string (v5.4.0): Extracting archive
  - Installing symfony/deprecation-contracts (v2.5.0): Extracting archive
  - Installing psr/container (1.1.2): Extracting archive
  - Installing symfony/service-contracts (v2.5.0): Extracting archive
  - Installing symfony/polyfill-php73 (v1.23.0): Extracting archive
  - Installing symfony/console (v5.4.1): Extracting archive
  - Installing psr/log (1.1.4): Extracting archive
  - Installing monolog/monolog (2.3.5): Extracting archive
  - Installing voku/portable-ascii (1.5.6): Extracting archive
  - Installing phpoption/phpoption (1.8.1): Extracting archive
  - Installing graham-campbell/result-type (v1.0.4): Extracting archive
  - Installing vlucas/phpdotenv (v5.4.1): Extracting archive
  - Installing symfony/css-selector (v5.4.0): Extracting archive
  - Installing tijsverkoyen/css-to-inline-styles (2.2.4): Extracting archive
  - Installing symfony/routing (v5.4.0): Extracting archive
  - Installing symfony/process (v5.4.0): Extracting archive
  - Installing symfony/polyfill-php72 (v1.23.0): Extracting archive
  - Installing symfony/polyfill-intl-idn (v1.23.0): Extracting archive
  - Installing symfony/mime (v5.4.0): Extracting archive
  - Installing symfony/http-foundation (v5.4.1): Extracting archive
  - Installing psr/event-dispatcher (1.0.0): Extracting archive
  - Installing symfony/event-dispatcher-contracts (v2.5.0): Extracting archive
  - Installing symfony/event-dispatcher (v5.4.0): Extracting archive
  - Installing symfony/error-handler (v5.4.1): Extracting archive
  - Installing symfony/http-kernel (v5.4.1): Extracting archive
  - Installing symfony/finder (v5.4.0): Extracting archive
  - Installing symfony/polyfill-iconv (v1.23.0): Extracting archive
  - Installing egulias/email-validator (2.1.25): Extracting archive
  - Installing swiftmailer/swiftmailer (v6.3.0): Extracting archive
  - Installing symfony/polyfill-php81 (v1.23.0): Extracting archive
  - Installing ramsey/collection (1.2.2): Extracting archive
  - Installing brick/math (0.9.3): Extracting archive
  - Installing ramsey/uuid (4.2.3): Extracting archive
  - Installing psr/simple-cache (1.0.1): Extracting archive
  - Installing opis/closure (3.6.2): Extracting archive
  - Installing symfony/translation-contracts (v2.5.0): Extracting archive
  - Installing symfony/translation (v5.4.1): Extracting archive
  - Installing nesbot/carbon (2.55.2): Extracting archive
  - Installing league/mime-type-detection (1.9.0): Extracting archive
  - Installing league/flysystem (1.1.9): Extracting archive
  - Installing nette/utils (v3.2.6): Extracting archive
  - Installing nette/schema (v1.2.2): Extracting archive
  - Installing dflydev/dot-access-data (v3.0.1): Extracting archive
  - Installing league/config (v1.1.1): Extracting archive
  - Installing league/commonmark (2.1.0): Extracting archive
  - Installing laravel/serializable-closure (v1.0.5): Extracting archive
  - Installing laravel/framework (v8.77.1): Extracting archive
  - Installing facade/ignition-contracts (1.0.2): Extracting archive
  - Installing facade/flare-client-php (1.9.1): Extracting archive
  - Installing facade/ignition (2.17.3): Extracting archive
  - Installing fakerphp/faker (v1.17.0): Extracting archive
  - Installing asm89/stack-cors (v2.0.3): Extracting archive
  - Installing fruitcake/laravel-cors (v2.0.4): Extracting archive
  - Installing psr/http-message (1.0.1): Extracting archive
  - Installing psr/http-client (1.0.1): Extracting archive
  - Installing ralouphie/getallheaders (3.0.3): Extracting archive
  - Installing psr/http-factory (1.0.1): Extracting archive
  - Installing guzzlehttp/psr7 (2.1.0): Extracting archive
  - Installing guzzlehttp/promises (1.5.1): Extracting archive
  - Installing guzzlehttp/guzzle (7.4.1): Extracting archive
  - Installing laravel/sail (v1.12.12): Extracting archive
  - Installing laravel/sanctum (v2.13.0): Extracting archive
  - Installing nikic/php-parser (v4.13.2): Extracting archive
  - Installing psy/psysh (v0.10.12): Extracting archive
  - Installing laravel/tinker (v2.6.3): Extracting archive
  - Installing hamcrest/hamcrest-php (v2.0.1): Extracting archive
  - Installing mockery/mockery (1.4.4): Extracting archive
  - Installing filp/whoops (2.14.4): Extracting archive
  - Installing nunomaduro/collision (v5.10.0): Extracting archive
  - Installing phpdocumentor/reflection-common (2.2.0): Extracting archive
  - Installing phpdocumentor/type-resolver (1.5.1): Extracting archive
  - Installing phpdocumentor/reflection-docblock (5.3.0): Extracting archive
  - Installing sebastian/version (3.0.2): Extracting archive
  - Installing sebastian/type (2.3.4): Extracting archive
  - Installing sebastian/resource-operations (3.0.3): Extracting archive
  - Installing sebastian/recursion-context (4.0.4): Extracting archive
  - Installing sebastian/object-reflector (2.0.4): Extracting archive
  - Installing sebastian/object-enumerator (4.0.4): Extracting archive
  - Installing sebastian/global-state (5.0.3): Extracting archive
  - Installing sebastian/exporter (4.0.4): Extracting archive
  - Installing sebastian/environment (5.1.3): Extracting archive
  - Installing sebastian/diff (4.0.4): Extracting archive
  - Installing sebastian/comparator (4.0.6): Extracting archive
  - Installing sebastian/code-unit (1.0.8): Extracting archive
  - Installing sebastian/cli-parser (1.0.1): Extracting archive
  - Installing phpunit/php-timer (5.0.3): Extracting archive
  - Installing phpunit/php-text-template (2.0.4): Extracting archive
  - Installing phpunit/php-invoker (3.1.1): Extracting archive
  - Installing phpunit/php-file-iterator (3.0.6): Extracting archive
  - Installing theseer/tokenizer (1.2.1): Extracting archive
  - Installing sebastian/lines-of-code (1.0.3): Extracting archive
  - Installing sebastian/complexity (2.0.2): Extracting archive
  - Installing sebastian/code-unit-reverse-lookup (2.0.3): Extracting archive
  - Installing phpunit/php-code-coverage (9.2.10): Extracting archive
  - Installing doctrine/instantiator (1.4.0): Extracting archive
  - Installing phpspec/prophecy (v1.15.0): Extracting archive
  - Installing phar-io/version (3.1.0): Extracting archive
  - Installing phar-io/manifest (2.0.3): Extracting archive
  - Installing myclabs/deep-copy (1.10.2): Extracting archive
  - Installing phpunit/phpunit (9.5.11): Extracting archive
   0/110 [>---------------------------]   0%
  10/110 [==>-------------------------]   9%
  20/110 [=====>----------------------]  18%
  30/110 [=======>--------------------]  27%
  39/110 [=========>------------------]  35%
  47/110 [===========>----------------]  42%
  49/110 [============>---------------]  44%
  55/110 [==============>-------------]  50%
  58/110 [==============>-------------]  52%
  66/110 [================>-----------]  60%
  72/110 [==================>---------]  65%
  77/110 [===================>--------]  70%
  84/110 [=====================>------]  76%
  92/110 [=======================>----]  83%
  97/110 [========================>---]  88%
 104/110 [==========================>-]  94%
 110/110 [============================] 100%
78 package suggestions were added by new dependencies, use `composer suggest` to see details.
Package swiftmailer/swiftmailer is abandoned, you should avoid using it. Use symfony/mailer instead.
Generating optimized autoload files
> Illuminate\Foundation\ComposerScripts::postAutoloadDump
> @php artisan package:discover --ansi
Discovered Package: facade/ignition
Discovered Package: fruitcake/laravel-cors
Discovered Package: laravel/sail
Discovered Package: laravel/sanctum
Discovered Package: laravel/tinker
Discovered Package: nesbot/carbon
Discovered Package: nunomaduro/collision
Package manifest generated successfully.
77 packages you are using are looking for funding.
Use the `composer fund` command to find out more!
> @php artisan vendor:publish --tag=laravel-assets --ansi
No publishable resources for tag [laravel-assets].
Publishing complete.
Removing intermediate container 61bc7c454a33
 ---> e3d7909d1b03
Step 12/15 : COPY --chown=www:www . /var/www/
 ---> f65628803ec3
Step 13/15 : USER www
 ---> Running in 431df0285a45
Removing intermediate container 431df0285a45
 ---> 79451e178abc
Step 14/15 : EXPOSE 9000
 ---> Running in d7c1b375f1e0
Removing intermediate container d7c1b375f1e0
 ---> 05947a067a1a
Step 15/15 : CMD ["php-fpm"]
 ---> Running in 6e4d101f22ac
Removing intermediate container 6e4d101f22ac
 ---> ce7ed629da0a
Successfully built ce7ed629da0a
Successfully tagged interview-assessment/php:latest
Pulling webserver (nginx:alpine)...
alpine: Pulling from library/nginx
97518928ae5f: Already exists
a4e156412037: Already exists
e0bae2ade5ec: Already exists
3f3577460f48: Already exists
e362c27513c3: Already exists
a2402c2da473: Already exists
Digest: sha256:12aa12ec4a8ca049537dd486044b966b0ba6cd8890c4c900ccb5e7e630e03df0
Status: Downloaded newer image for nginx:alpine
Creating app       ... done
Creating webserver ... done
root@xnb135-wsl:/home/DevOps-Challenge# 

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose images
Container          Repository           Tag       Image Id       Size  
-----------------------------------------------------------------------
app         interview-assessment/php   latest   ce7ed629da0a   629.8 MB
webserver   nginx                      alpine   b46db85084b8   23.2 MB 

root@xnb135-wsl:/home/DevOps-Challenge# docker-compose ps
  Name                 Command               State                    Ports                  
---------------------------------------------------------------------------------------------
app         docker-php-entrypoint php-fpm    Up      9000/tcp                                
webserver   /docker-entrypoint.sh ngin ...   Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/tcp
root@xnb135-wsl:/home/DevOps-Challenge# 
