## React-Share-Lite

react-share-lite is a simple and easy-to-use library for adding social media share buttons to your React, Next and Preact applications. With react-share-lite, you can quickly integrate share buttons for popular social media platforms such as Facebook, X (formerly Twitter), LinkedIn, and more.

react-share-lite ships share buttons only — it does not include share-count components. If you want share count functionality in your React, Next.js, or Preact projects built with JavaScript and TypeScript, [react-share-kit](https://www.npmjs.com/package/react-share-kit) is the solution. It seamlessly enhances your applications, allowing users to easily track the popularity of your content.

[![downloads](https://img.shields.io/npm/dm/react-share-lite.svg?label=monthly%20downloads)](https://www.npmjs.com/package/react-share-lite) [![downloads](https://img.shields.io/npm/dt/react-share-lite.svg?label=total%20downloads)](https://www.npmjs.com/package/react-share-lite)

[![NPM](https://img.shields.io/npm/v/react-share-lite.svg)](https://www.npmjs.com/package/react-share-lite) ![npm bundle size](https://img.shields.io/bundlephobia/min/react-share-lite) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

![Share buttons screenshot](https://github.com/ayda-tech/react-share-lite/blob/main/react-share-lite.png?raw=true)


---

### ✨ What's new in v2.0.0

- ⚛️ React 19 ready — works with React 17, 18 and 19, including Next.js App Router server components.
- 🆕 New networks: `XShare` (the canonical X/Twitter button), `BlueskyShare` and `ThreadsShare`.
- 🎨 Styleable at last — `className`, `style` and all other standard button attributes are forwarded to the underlying `<button>`.
- 🧹 Dead networks removed: `PocketShare` (Pocket was shut down in July 2025) and `WorkplaceShare` (Meta Workplace was discontinued).

See the [CHANGELOG](./CHANGELOG.md) for the full list, including breaking changes.

**Requirements:** React 17, 18 or 19.

---

### Table of Contents

- [React-Share-Lite](#react-share-lite)
  - [✨ What's new in v2.0.0](#-whats-new-in-v200)
  - [Table of Contents](#table-of-contents)
- [Installation](#installation)
- [📕 Share Button Global Props](#-share-button-global-props)
- [💡 Usage of ShareButtons](#-usage-of-sharebuttons)
  - [Facebook Share](#facebook-share)
  - [X Share](#x-share)
  - [Twitter Share (Deprecated)](#twitter-share-deprecated)
  - [Bluesky Share](#bluesky-share)
  - [Threads Share](#threads-share)
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
  - [Instapaper Share](#instapaper-share)
  - [Hatena Share](#hatena-share)
  - [Gab Share](#gab-share)
- [FAQ](#faq)
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

| Props                  | Type          | Default          | Description                                                                                       | Required |
| :--------------------- | :------------ | :--------------- | :------------------------------------------------------------------------------------------------ | :------- |
| url                    | string        |                  | The URL of the shared page.                                                                       | TRUE     |
| title                  | string        |                  | The title of the shared page.                                                                     | FALSE    |
| windowWidth            | number        | 550              | Opened window width.                                                                              | FALSE    |
| windowHeight           | number        | 400              | Opened window height.                                                                             | FALSE    |
| windowPosition         | string        | windowCenter     | Position of the share window: `windowCenter` or `screenCenter`.                                   | FALSE    |
| blankTarget            | boolean       | false            | Open share window in a new tab if set to `true` (opened with `noopener,noreferrer`).              | FALSE    |
| bgColor                | string        | related color    | Icon background color.                                                                            | FALSE    |
| round                  | boolean       | false            | The "round" attribute creates a fully circular button shape, giving it a 100% rounded appearance. | FALSE    |
| borderRadius           | number        | 0px              | Custom round share.                                                                               | FALSE    |
| size                   | number        | 64px             | The button size.                                                                                  | FALSE    |
| buttonTitle            | string        |                  | The title of button used instead of icon.                                                         | FALSE    |
| style                  | CSSProperties |                  | Custom style for the underlying `button` element.                                                 | FALSE    |
| iconStyle              | CSSProperties |                  | Custom style for the icon.                                                                        | FALSE    |
| iconFillColor          | string        |                  | Icon fill color.                                                                                  | FALSE    |
| disabled               | boolean       | false            | Disables the click action and applies `disabledStyle`.                                            | FALSE    |
| disabledStyle          | CSSProperties | { opacity: 0.6 } | Style applied to the button when `disabled` is `true`.                                            | FALSE    |
| openShareDialogOnClick | boolean       | true             | Open the share dialog on click.                                                                   | FALSE    |
| onClick                | function      |                  | Custom click handler, called with `(event, shareLink)`.                                           | FALSE    |
| beforeOnClick          | function      |                  | Takes a function that returns a Promise to be fulfilled before opening the share dialog.          | FALSE    |
| onShareWindowClose     | function      |                  | Takes a function to be called after closing the share dialog.                                     | FALSE    |
| resetButtonStyle       | boolean       | true             | Set to `false` to keep the browser's default `button` styling.                                    | FALSE    |
| forwardedRef           | Ref           |                  | Ref forwarded to the underlying `button` element.                                                 | FALSE    |

💅 <b>Styling</b>: All standard button HTML attributes — `className`, `style`, `aria-*`, `data-*`, event handlers, etc. — are forwarded to the underlying `<button>` element, so you can style the buttons with your own CSS classes:

```jsx
<FacebookShare url={shareUrl} className="my-share-button" data-testid="fb-share" />
```

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
import { FacebookShare } from 'react-share-lite';
<FacebookShare
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

### X Share

👨‍💻 <b>Example</b>

```js
import { XShare } from 'react-share-lite'

<XShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  hashtags={['react-share-lite', 'front-end']}
/>
```

📕 <b>Props</b>: Supports only on X

| Props    | Type   | Default | Description | Required |
| :------- | :----- | :------ | :---------- | :------- |
| via      | string |         | A username to attribute the post to. | FALSE    |
| hashtags | array  |         | An array of hashtags to be appended to the default post text. | FALSE    |
| related  | array  |         | An array of accounts related to the content of the shared URI. | FALSE    |

### Twitter Share (Deprecated)

> ⚠️ **Deprecated**: Twitter is now X. `TwitterShare` is kept as an alias of [`XShare`](#x-share) — it renders the X logo and opens the X post intent (`x.com/intent/post`). Use `XShare` in new code.

👨‍💻 <b>Example</b>

```js
import { TwitterShare } from 'react-share-lite'

<TwitterShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  hashtags={['react-share-lite', 'front-end']}
/>
```

📕 <b>Props</b>: Same as [X Share](#x-share).

### Bluesky Share

👨‍💻 <b>Example</b>

```js
import { BlueskyShare } from 'react-share-lite'

<BlueskyShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  separator=":: "
/>
```

📕 <b>Props</b>: Supports only on Bluesky

| Props     | Type   | Default | Description                                | Required |
| :-------- | :----- | :------ | :----------------------------------------- | :------- |
| separator | string |         | A separator between the title and the URL. | FALSE    |

### Threads Share

👨‍💻 <b>Example</b>

```js
import { ThreadsShare } from 'react-share-lite'

<ThreadsShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
/>
```

### Linkedin Share

👨‍💻 <b>Example</b>

```js
import { LinkedinShare } from 'react-share-lite'

<LinkedinShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Whatsapp Share

👨‍💻 <b>Example</b>

```js
import { WhatsappShare } from 'react-share-lite'

<WhatsappShare
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

<TelegramShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### FacebookMessenger Share

👨‍💻 <b>Example</b>

```js
import { FacebookMessengerShare } from 'react-share-lite'

<FacebookMessengerShare
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
import { EmailShare } from 'react-share-lite'

<EmailShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  subject={'React Share Lite'}
  body="body"
/>
```

📕 <b>Props</b>: Supports only on Email

| Props     | Type   | Default | Description                                        | Required |
| :-------- | :----- | :------ | :------------------------------------------------- | :------- |
| subject   | string |         | The subject of the email.                          | FALSE    |
| body      | string |         | The body of the email.                             | FALSE    |
| separator | string |         | A separator between the email body and the URL.    | FALSE    |

### VK Share

👨‍💻 <b>Example</b>

```js
import { VKShare } from 'react-share-lite'

<VKShare
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

<PinterestShare
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

<RedditShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Line Share

👨‍💻 <b>Example</b>

```js
import { LineShare } from 'react-share-lite'

<LineShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Tumblr Share

👨‍💻 <b>Example</b>

```js
import { TumblrShare } from 'react-share-lite'

<TumblrShare
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

<ViberShare
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

<WeiboShare
  url={'https://github.com/ayda-tech/react-share-lite'}
  title={'react-share-lite - social share buttons for next & react apps.'}
  image={'https://github.com/ayda-tech/react-share-lite/blob/main/react-share-lite.png?raw=true'}
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

<MailruShare url={'https://github.com/ayda-tech/react-share-lite'} />
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

<LiveJournalShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

📕 <b>Props</b>: Supports only on Live Journal

| Props       | Type   | Default | Description                     | Required |
| :---------- | :----- | :------ | :------------------------------ | :------- |
| description | string |         | Description of the shared page. | FALSE    |

### Instapaper Share

👨‍💻 <b>Example</b>

```js
import { InstapaperShare } from 'react-share-lite'

<InstapaperShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

📕 <b>Props</b>: Supports only on Instapaper

| Props       | Type   | Default | Description                     | Required |
| :---------- | :----- | :------ | :------------------------------ | :------- |
| description | string |         | Description of the shared page. | FALSE    |

### Hatena Share

👨‍💻 <b>Example</b>

```js
import { HatenaShare } from 'react-share-lite'

<HatenaShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

### Gab Share

👨‍💻 <b>Example</b>

```js
import { GabShare } from 'react-share-lite'

<GabShare url={'https://github.com/ayda-tech/react-share-lite'} />
```

## FAQ

<b>Why doesn't my shared link show an image preview?</b>

Link previews (image, title, description) are generated by the social network from the Open Graph / Twitter Card meta tags of the <b>shared page</b> itself — not by this library. If a preview is missing or wrong, add the proper `og:*` / `twitter:*` meta tags to the page you are sharing.

## License

react-share-lite is licensed under the MIT License. See the [LICENSE](https://github.com/ayda-tech/react-share-lite/blob/main/LICENSE) file for more details.
