---
title: Installation
description: NexT User Docs – Starting to Use – Detailed Installation
---

### Go to Hexo dir

Change dir to {% label info@site root directory %}. There must be `node_modules`, `source`, `themes` and other directories:

```bash
$ cd hexo-site
$ ls
_config.yml  node_modules  package.json  public  scaffolds  source  themes
```

### Select Version

A new version of NexT will be released every month. You can choose to install the latest version or choose a stable old version.

{% tabs download-next %}
<!-- tab {% label success@Latest Master Branch %} -->
**Option 1: Download the [Latest Master Branch](https://github.com/next-theme/hexo-theme-next/archive/master.zip)**

May be **unstable**, but includes **latest features**. At most cases useful and recommended for advanced users and for developers.
<!-- endtab -->

<!-- tab Latest Release Version -->
**Option 2: Download the [Latest Release Version](https://github.com/next-theme/hexo-theme-next/releases/latest)**

At most cases **stable**. Recommended for beginners.
<!-- endtab -->

<!-- tab Specific Release Version -->
**Option 3: Download the [Specific Release Version](https://github.com/next-theme/hexo-theme-next/releases)**

In rare cases useful, but not recommended.
You must define version. Let's take `v8.0.0` as an example. Replace it with any version from [tags list](https://github.com/next-theme/hexo-theme-next/tags).
<!-- endtab -->
{% endtabs %}

### Get NexT

There are **3 ways** to download NexT: `npm`, `git` and download zip from GitHub. You need to **choose only one** of them.

#### Using `npm`

If you're using Hexo 5.0 or later, you can install `hexo-theme-next` through npm.

{% tabs using-npm %}
<!-- tab Latest Release Version -->
```bash
$ npm install hexo-theme-next@latest
```

This variant will install the **latest release version**.
<!-- endtab -->

<!-- tab Specific Release Version -->
```bash
$ npm install hexo-theme-next@8.0.0
```

This variant will install the **specific release version**.
<!-- endtab -->
{% endtabs %}

#### Using `git`

{% tabs using-git %}
<!-- tab Latest Master Branch -->
```bash
$ git clone https://github.com/next-theme/hexo-theme-next themes/next
```

Or download via mirror on GitLab:

```bash
$ git clone https://gitlab.com/hexo-theme-next/hexo-theme-next themes/next
```

This variant will install the **whole repository** (with `.git` directory inside).
And in any time you can update current version with git (instructions below) and switch to any tagged release or on latest master or any other branch.

Get tags list:

```bash
$ cd themes/next
$ git tag -l
...
v8.0.0-rc.1
v8.0.0-rc.2
v8.0.0-rc.3
...
```

For example, you want to switch on `v8.0.0` tagged release version. Input the following command:

```bash
$ git checkout tags/v8.0.0
Note: switching to 'tags/v8.0.0'.
...
HEAD is now at f27e45b Release v8.0.0
```

If you want to switch on latest release version without defining tag (optional)

```bash
$ git checkout $(git describe --tags $(git rev-list --tags --max-count=1))
```

And if you want to switch back on master branch, input this command:

```bash
$ git checkout master
```
<!-- endtab -->

<!-- tab Specific Release Version -->
```bash
$ git clone --branch v8.0.0 https://github.com/next-theme/hexo-theme-next themes/next
```

Or download via mirror on GitLab:

```bash
$ git clone --branch v8.0.0 https://gitlab.com/hexo-theme-next/hexo-theme-next themes/next
```

This variant will install the **specific release version** (with `.git` directory inside).
And in any time you can switch to any tagged release, but with limit to specific version.
<!-- endtab -->
{% endtabs %}

**Update**
You can update to the latest master branch by the following command:

```bash
$ cd themes/next
$ git pull origin master
```

And if you see any error message during update (something like **«Commit your changes or stash them before you can merge»**), recommended to learn [Alternate Theme Config](/docs/getting-started/configuration.html) feature. Howbeit, you can bypass update errors by `Commit`, `Stash` or `Discard` local changes. See [here](https://stackoverflow.com/a/15745424/5861495) how to do it.

#### Download zip

Download zip from GitHub without `.git` directory inside. So, it is impossible to update this version with `git` later.
Instead you always can use separate configuration (e.g. [Alternate Theme Config](/docs/getting-started/configuration.html)) and download new version inside old directory (or create new directory and redefine `theme` in {% label info@site config file %}), without losing your old configuration.

{% tabs curl-tar %}
<!-- tab Latest Master Branch -->
```bash
$ mkdir themes/next
$ curl -L https://api.github.com/repos/next-theme/hexo-theme-next/tarball | tar -zxv -C themes/next --strip-components=1
```

This variant will install the **latest master branch**.
<!-- endtab -->

<!-- tab Latest Release Version -->
```bash
$ mkdir themes/next
$ curl -s https://api.github.com/repos/next-theme/hexo-theme-next/releases/latest | grep tarball_url | cut -d '"' -f 4 | wget -i - -O- | tar -zx -C themes/next --strip-components=1
```

This variant will install the **latest release version**.
<!-- endtab -->

<!-- tab Specific Release Version -->
```bash
$ mkdir themes/next
$ curl -L https://api.github.com/repos/next-theme/hexo-theme-next/tarball/v8.0.0 | tar -zxv -C themes/next --strip-components=1
```

This variant will install the **specific release version**.
<!-- endtab -->
{% endtabs %}

### Set It Up

When NexT download will complete, we must go back to previous guide and follow [Enabling NexT](/docs/getting-started/#Enabling-NexT) instructions.
