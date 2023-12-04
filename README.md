<center>

### react-share-lite

react-share-lite is a simple and easy-to-use library for adding social media share buttons to your React & Next applications. With react-share-lite, you can quickly integrate share buttons for popular social media platforms such as Facebook, Twitter, LinkedIn, and more.

[![downloads](https://img.shields.io/npm/dm/react-share-lite.svg?label=monthly%20downloads)](https://www.npmjs.com/package/react-share-lite) [![downloads](https://img.shields.io/npm/dt/react-share-lite.svg?label=total%20downloads)](https://www.npmjs.com/package/react-share-lite)

[![NPM](https://img.shields.io/npm/v/react-share-lite.svg)](https://www.npmjs.com/package/react-share-lite) ![npm bundle size](https://img.shields.io/bundlephobia/min/react-share-lite) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

![Share buttons screenshot](https://github.com/ayda-tech/react-share-lite/blob/main/react-share-lite.png?raw=true)

</center>

---

### Table of Contents

- [Installation](#installation)
- [📕 Share Button Global Props](#-share-button-global-props)
- [💡 Usage of ShareButtons](#-usage-of-sharebuttons)
  - [Facebook Share](#facebook-share)
  - [Twitter Share](#twitter-share)
  - [Linkedin Share](#linkedin-share)
  - [Whatsapp Share](#whatsapp-share)
  - [Telegram Share](#telegram-share)
  - [FacebookMessenger Share](#facebookmessenger-share)
  - [Email Share](#email-share)
  - [VK Share](#vk-share)
  - [Pinterest Share](#pinterest-share)
  - [Reddit Share](#reddit-share)
  - [Line Share](#line-share)
  - [Tumblr Share](#tumblr-share)
  - [Viber Share](#viber-share)
  - [Weibo Share](#weibo-share)
  - [Mailru Share](#mailru-share)
  - [LiveJournal Share](#livejournal-share)
  - [Workplace Share](#workplace-share)
  - [Pocket Share](#pocket-share)
  - [Instapaper Share](#instapaper-share)
  - [Hatena Share](#hatena-share)
  - [Gab Share](#gab-share)
- [License](#license)

## Installation

To install react-share-lite, simply run:

```bash
npm install react-share-lite
```

or

```bash
yarn add react-share-lite
```

## 📕 Share Button Global Props

Each button supports a set of global props that are consistent across all buttons. However, in addition to these global props, each button also possesses its own unique set of specific properties. These specific properties are tailored to the individual functionality and customization options of each button.

| Props        | Type    | Default       | Description                                                                                       | Required |
| :----------- | :------ | :------------ | :------------------------------------------------------------------------------------------------ | :------- |
| url          | string  |               | The URL of the shared page.                                                                       | TRUE     |
| title        | string  |               | The title of the shared page.                                                                     | FALSE    |
| windowWidth  | number  | 550           | Opened window width.                                                                              | FALSE    |
| windowHeight | number  | 400           | Opened window height.                                                                             | FALSE    |
| blankTarget  | boolean | false         | Open share window in a new tab if set to `true`.                                                  | FALSE    |
| bgColor      | string  | related color | Icon background color.                                                                            | FALSE    |
| round        | boolean | false         | The "round" attribute creates a fully circular button shape, giving it a 100% rounded appearance. | FALSE    |
| borderRadius | number  | 0px           | Custom round share.                                                                               | FALSE    |
| size         | number  | 64px          | The button size.                                                                                  | FALSE    |
| buttonTitle  | string  |               | The title of button used instead of icon.                                                         | FALSE    |

👨‍💻 <b>Example</b>

```jsx
import React from 'react'
import { FacebookShare } from 'react-share-lite'

const ShareButtons = () => {
  const shareUrl = 'https://github.com/ayda-tech/react-share-lite'
  const title = 'Check out this awesome website!'

  return <FacebookShare url={shareUrl} quote={title} />
}
```

## 💡 Usage of ShareButtons

### Facebook Share

👨‍💻 <b>Example</b>

```js
import { FacebookShare } from 'react-share-lite'
;<FacebookShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  quote={'react-share-lite - social share buttons for next & react apps.'}
  hashtag={'#react-share-lite'}
/>
```

📕 <b>Props</b>: Supports only on Facebook

| Props   | Type   | Default | Description           | Required |
| :------ | :----- | :------ | :-------------------- | :------- |
| quote   | string |         | A quote to be shared. | FALSE    |
| hashtag | string |         | Hashtag to be shared. | FALSE    |

### Twitter Share

👨‍💻 <b>Example</b>

```js
import {
  TwitterShare
} from 'react-share-lite'

<TwitterShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  hashtags=["#react-share-lite", "#front-end"]
/>
```

📕 <b>Props</b>: Supports only on Twitter

| Props    | Type   | Default | Description | Required |
| :------- | :----- | :------ | :---------- | :------- |
| via      | string |         | A screen name to associate with the Tweet. | FALSE    |
| hashtags | array  |         | A comma-separated list of hashtags to be appended to default Tweet text. | FALSE    |
| related  | array  |         | A comma-separated list of accounts related to the content of the shared URI. | FALSE    |

### Linkedin Share

👨‍💻 <b>Example</b>

```js
import { LinkedinShare } from 'react-share-lite'
;<LinkedinShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Whatsapp Share

👨‍💻 <b>Example</b>

```js
import { WhatsappShare } from 'react-share-lite'
;<WhatsappShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  separator=":: "
/>
```

📕 <b>Props</b>: Supports only on WhatsApp

| Props     | Type   | Default | Description | Required |
| :-------- | :----- | :------ | :---------- | :------- |
| separator | string |         |             | FALSE    |

### Telegram Share

👨‍💻 <b>Example</b>

```js
import { TelegramShare } from 'react-share-lite'
;<TelegramShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### FacebookMessenger Share

👨‍💻 <b>Example</b>

```js
import { FacebookMessengerShareButton } from 'react-share-lite'
;<FacebookMessengerShareButton
  url="https://github.com/ayda-tech/react-share-lite"
  redirectUri="https://github.com/ayda-tech/react-share-lite"
  appId={'dmm4kj9djk203k4liuf994p'}
/>
```

📕 <b>Props</b>: Supports only on Facebook Messenger

| Props       | Type   | Default | Description                                                                                                 | Required |
| :---------- | :----- | :------ | :---------------------------------------------------------------------------------------------------------- | :------- |
| appId       | string |         | Facebook application id.                                                                                    | TRUE     |
| redirectUri | string |         | The URL to redirect to after sharing (default: the shared url).                                             | FALSE    |
| to          | string |         | A user ID of a recipient. Once the dialog comes up, the sender can specify additional people as recipients. | FALSE    |

### Email Share

👨‍💻 <b>Example</b>

```js
import { EmailShare } from 'next-share'
;<EmailShare
  url={'https://github.com/next-share'}
  subject={'Next Share'}
  body="body"
/>
```

📕 <b>Props</b>: Supports only on Email

| Props       | Type    | Default | Description                                      | Required |
| :---------- | :------ | :------ | :----------------------------------------------- | :------- |
| children    | node    |         | React component, HTML element or string.         | TRUE     |
| url         | string  |         | The URL of the shared page.                      | TRUE     |
| subject     | string  |         | The subject of the email.                        | FALSE    |
| body        | string  |         | The body of the email.                           | FALSE    |
| separator   | string  |         | A separator to be shared.                        | FALSE    |
| blankTarget | boolean | false   | Open share window in a new tab if set to `true`. | FALSE    |

### VK Share

👨‍💻 <b>Example</b>

```js
import { VKShare } from 'react-share-lite'
;<VKShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  image={'./react-share.png'}
/>
```

📕 <b>Props</b>: Supports only on VK

| Props     | Type    | Default | Description                                                                                                  | Required |
| :-------- | :------ | :------ | :----------------------------------------------------------------------------------------------------------- | :------- |
| image     | string  |         | An absolute link to the image that will be shared.                                                           | FALSE    |
| noParse   | boolean |         | If true is passed, VK will not retrieve URL information.                                                     | FALSE    |
| noVkLinks | boolean |         | If true is passed, there will be no links to the user's profile in the open window. Only for mobile devices. | FALSE    |

### Pinterest Share

👨‍💻 <b>Example</b>

```js
import { PinterestShare } from 'react-share-lite'
;<PinterestShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  media={'react-share-lite - social share buttons for next & react apps.'}
/>
```

📕 <b>Props</b>: Supports only on Pinterest

| Props       | Type   | Default | Description                          | Required |
| :---------- | :----- | :------ | :----------------------------------- | :------- |
| media       | string |         | The image URL that will be pinned.   | TRUE     |
| description | string |         | The description of the shared media. | FALSE    |

### Reddit Share

👨‍💻 <b>Example</b>

```js
import { RedditShare } from 'react-share-lite'
;<RedditShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Line Share

👨‍💻 <b>Example</b>

```js
import { LineShare } from 'react-share-lite'
;<LineShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Tumblr Share

👨‍💻 <b>Example</b>

```js
import { TumblrShare } from 'react-share-lite'
;<TumblrShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  caption="react-share-lite - social share buttons for next & react apps."
/>
```

📕 <b>Props</b>: Supports only on Tumblr

| Props    | Type                             | Default           | Description                         | Required |
| :------- | :------------------------------- | :---------------- | :---------------------------------- | :------- |
| tags     | <code>Array&lt;string&gt;</code> |                   | An array of tags to be shared.      | FALSE    |
| caption  | string                           |                   | The description of the shared page. | FALSE    |
| posttype | string                           | <code>link</code> | The type of the post.               | FALSE    |

### Viber Share

👨‍💻 <b>Example</b>

```js
import { ViberShare } from 'react-share-lite'
;<ViberShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
/>
```

📕 <b>Props</b>: Supports only on Viber

| Props     | Type   | Default | Description | Required |
| :-------- | :----- | :------ | :---------- | :------- |
| separator | string |         |             | FALSE    |

### Weibo Share

👨‍💻 <b>Example</b>

```js
import { WeiboShare } from 'react-share-lite'
;<WeiboShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  image={`${String(window.location)}/${example - image}`}
/>
```

📕 <b>Props</b>: Supports only on Weibo

| Props | Type   | Default | Description                        | Required |
| :---- | :----- | :------ | :--------------------------------- | :------- |
| image | string |         | The image URL that will be shared. | FALSE    |

### Mailru Share

👨‍💻 <b>Example</b>

```js
import { MailruShare } from 'react-share-lite'
;<MailruShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

📕 <b>Props</b>: Supports only on Mail-Ru

| Props       | Type   | Default | Description                     | Required |
| :---------- | :----- | :------ | :------------------------------ | :------- |
| description | string |         | Description of the shared page. | FALSE    |
| imageUrl    | string |         | Image url of the shared page.   | FALSE    |

### LiveJournal Share

👨‍💻 <b>Example</b>

```js
import { LiveJournalShare } from 'react-share-lite'
;<LiveJournalShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

📕 <b>Props</b>: Supports only on Live Journal

| Props       | Type   | Default | Description                     | Required |
| :---------- | :----- | :------ | :------------------------------ | :------- |
| description | string |         | Description of the shared page. | FALSE    |

### Workplace Share

👨‍💻 <b>Example</b>

```js
import { WorkplaceShare } from 'react-share-lite'
;<WorkplaceShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  quote={'React Share Lite'}
/>
```

📕 <b>Props</b>: Supports only on Workspace

| Props   | Type   | Default | Description | Required |
| :------ | :----- | :------ | :---------- | :------- |
| quote   | string |         | A quote to be shared. | FALSE    |
| hashtag | string |         | Hashtags to be shared.   | FALSE    |

### Pocket Share

👨‍💻 <b>Example</b>

```js
import {
  PocketShare
} from 'react-share-lite'

<PocketShare url={'https://github.com/ayda-tech/react-share-lite' />
```

### Instapaper Share

👨‍💻 <b>Example</b>

```js
import { InstapaperShare } from 'react-share-lite'
;<InstapaperShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

📕 <b>Props</b>: Supports only on Instapaper

| Props       | Type   | Default | Description                     | Required |
| :---------- | :----- | :------ | :------------------------------ | :------- |
| description | string |         | Description of the shared page. | FALSE    |

### Hatena Share

👨‍💻 <b>Example</b>

```js
import {
  HatenaShare
} from 'react-share-lite'

<HatenaShare url={'https://github.com/ayda-tech/react-share-lite' />
```

### Gab Share

👨‍💻 <b>Example</b>

```js
import { GabShare } from 'react-share-lite'
;<GabShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

## License

react-share-lite is licensed under the MIT License. See the [LICENSE](https://github.com/ayda-tech/react-share-lite/blob/main/LICENSE) file for more details.
