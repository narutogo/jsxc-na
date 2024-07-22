# JavaScript XMPP Client 
# JSXC-NA
This is fork form [JSXC](https://github.com/jsxc/jsxc)， because the original jsxc project have not update except bot update locale, so I fork this project and continue to development.
branch na-dev is the jSXC-NA.
These project added new feature, such as add a css var to control css element display, like '--jsxc-show-menu'， it can set whether display main menu in bottom right coner of jsxc. You can use javascript to set the var, like below:
```
  const root = document.documentElement;
  root.style.setProperty('--jsxc-show-menu', 'none');
```
such above new vars:
```
  --jsxc-margin-top
  --jsxc-margin-right
  --jsxc-margin-left
  --jsxc-margin-bottom
  --jsxc-show-audio-button
  --jsxc-show-video--button
  --jsxc-show-offline-button
```
Other new features as:
  - add translate in conversation dialog timestamp
  - fix bug in translate in Friendship_request
  - direction open chat dialog even who is not in roster lists, use such function as
    ```
    export async function directOpenChatWindow(jid: string) {
      if (!userJid) {
        throw "user jid is empty, please initialize jsxc";
      }
      await (window as any).jsxc.getAccount(userJid).account.getConnection().getRosterService().
          addContact(new (window as any).jsxc.JID(jid), '');
      (window as any).jsxc.getAccount(userJid).getContact(jid).openChatWindow();
    }
    ```
And I also create a react app example use this library, you can find [it](https://github.com/narutogo/jsxc-react-hook) to learn how use. 

Below is same as jsxc project:

## original jsxc

[![Build Status](https://travis-ci.org/jsxc/jsxc.svg?branch=master)](https://travis-ci.org/jsxc/jsxc)
[![Code Quality: Javascript](https://img.shields.io/lgtm/grade/javascript/g/jsxc/jsxc.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/jsxc/jsxc/context:javascript)
[![Total Alerts](https://img.shields.io/lgtm/alerts/g/jsxc/jsxc.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/jsxc/jsxc/alerts)


Real-time chat app. This app requires an external XMPP server (openfire, ejabberd etc.).

## :heart_eyes: Features
JSXC provides the following features:

- Federated real-time communication with XMPP
- One-to-one conversation
- Multi-user conversation
- File transfer
- Video calls
- Internationalisation
- Desktop notifications
- End-to-end encrypted two-party communication
- Responsive layout
- Emoticons :two_hearts:
- Multi-Tab
- Screen sharing

You find a full list of features, supported protocols and browsers on [our homepage](http://www.jsxc.org).

## :camera: Screenshots

![](https://www.jsxc.org/images/v3.0.0/screenshot-example.png)
![](https://www.jsxc.org/assets/screenshot-nextcloud-latest.png)

## :rocket: Installation
If you are looking for install instructions or developer notes, please check out our [official documentation](https://jsxc.readthedocs.io/en/latest/index.html).

## :clap: Contribution
Contribution is greatly appreciated. Following a couple of ideas, how you can contribute:

- [Report a bug](https://jsxc.readthedocs.io/en/latest/contributor-guide.html#report-a-bug)
- [Contribute code](https://jsxc.readthedocs.io/en/latest/contributor-guide.html#contribute-code)
- [Translate JSXC into your language](https://jsxc.readthedocs.io/en/latest/contributor-guide.html#translate-jsxc-into-your-language)
- [Announce](https://jsxc.readthedocs.io/en/latest/contributor-guide.html#announce)

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project, you agree to abide by its terms.
