# NOTE

Atom Editor is being [sunset](https://github.blog/2022-06-08-sunsetting-atom/) by GitHub devs. And as such this plugin won't be recieving any updates.
I know it was slow & buggy, and nearly freezed atom while using the key combination. While making this extension I looked into source code of many clipboard based extensions & copy pasted it together to bring it into working form. 
It was too much of an hacky solution considering that I still didn't understand much of Atom Editor's API.

And after the sunset news, I won't have to update it. 

If you still wish to update this, you may submit a pull request or publish your own fork.

# atom-picgo

Atom Plugin for PicGo Uploader

Provide full path to the `config.json` file in settings. By default it will look for `picgo.json` in project directory.
File name can be anything, as long as the extension is `.json`.

When no config is provided, PicGo will default to `smms`

Use `ctrl + alt + v` to paste image link

View Changelogs [here](CHANGELOG.md)

## PicGo config

Generate a PicGo config by referring this [guide](https://picgo.github.io/PicGo-Core-Doc/zh/guide/config.html)

Here is a rough English translation from the guide. (I do not know chinese, but I could figure out the parameters. I mostly used Google Translate to understand stuff)

The config must be in given json format:

```json
{
  "picBed": {
    "uploader": "smms", //select among given different uploaders.

    //uploader config
    "smms": {
      "token": ""
    }
  }
}
```

### Uploaders

Default is [smms](https://sm.ms/), even without providing any config file in package settings, as per what I observed during tests.

Multiple uploader configurations can be set. But PicGo will only use whatever is set in `uploader` field value.

#### SM.MS

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#sm-ms)

```json
{
  "picBed": {
    "uploader": "smms",
    "smms": {
       "token": ""                                 // your api token
    }
  }
}
```

#### Qiniu

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#qiuniu-img)

```json
{
  "picBed": {
    "uploader": "qiniu",
    "qiniu": {
      "accessKey": "",
      "secretKey": "",
      "bucket": "",                               // storage bucket
      "url": "",                                  // customized domain
      "area": "z0" | "z1" | "z2" | "na0" | "as0", // storage area
      "options": "",                              // URL suffix
      "path": ""                                  // storage path
    }
  }
}
```

#### Upyun

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#upyun-cloud)

```json
{
  "picBed": {
    "uploader": "upyun",
    "upyun": {
      "bucket": "",                               // storage bucket, note that v4 is different from v5
      "operator": "",                             // operator
      "password": "",                             // password
      "options": "",                              // URL suffix
      "path": ""                                  // storage path
      "url": "",                                  // customized domain
    }
  }
}
```

#### Tencent Cloud COS

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#tencent-cloud-cos)

```json
{
  "picBed": {
    "uploader": "tcyun",
    "tcyun": {
      "secretId": "",
      "secretKey": "",
      "bucket": "",                               // storage bucket, note that v4 is different from v5
      "appId": "",
      "area": "",                                 // storage area
      "path": ""                                  // storage path
      "customUrl": "", 														// customized domain
      "version": "v5" | "v4" 											// COS version
    }
  }
}
```

#### GitHub

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#github-img)

```json
{
  "picBed": {
    "uploader": "github",
    "github": {
      "repo": "",                                 // user/repo
      "token": "",                                // github token
      "path": ""                                  // storage path
      "customUrl": "", 														// customized domain
      "branch": ""                                // branch, main by default
    }
  }
}
```

#### Alibaba Cloud OSS

[Config guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#aliyun-oss)

```json
{
  "picBed": {
    "uploader": "aliyun",
    "aliyun": {
      "accessKeyId": "",
      "accessKeySecret": "",
      "bucket": "",                               // storage bucket
      "area": "",                                 // storage area
      "path": ""                                  // storage path
      "customUrl": "", 														// customized domain
    }
  }
}
```

#### Imgur

[Config Guide](https://picgo.github.io/PicGo-Doc/en/guide/config.html#imgur-img)

```json
{
  "picBed": {
    "uploader": "imgur",
    "imgur": {
      "clientId": "",                             // your clientId
      "proxy": ""                                 // proxy address, only http supported
    }
  }
}
```

#### HTTP proxy

[Config Guide](https://picgo.github.io/PicGo-Core-Doc/zh/guide/config.html#picbed-proxy)

```json
{
  "picBed": {
    "uploader": "proxy",
    "proxy": {
      "proxy": ""                                 // proxy address, only http supported
    }
  }
}
```

## Licence

[MIT](./LICENSE)
