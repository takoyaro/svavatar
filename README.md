# Svavatar

[![Svavatar](https://svgshare.com/i/Lfq.svg)](https://nodesource.com/products/nsolid)

Svavatar is a [Svelte](https://svelte.dev) component wrapping [Dicebear's Avatars](https://avatars.dicebear.com)

  - "*Code*" and "*Avataaars*" avatars not included because of compatibility issues (feel free to pull!)
  - All options are available and kept in the same format as the original package

# How to use?

  - Import the component in your application
    - ```js
      import Svavatar from {svavatar}
       ```
  - Use the component like any Svelte component and pass the mandatory `type` parameter, a `seed` and `options` as separate, individual parameters. Example:
    - ```js
      <Svavatar type="human" mood="happy" seed="tako"/>
      ```
      or
    - ```js
      <Svavatar type="initials" bold={true} seed="John Doe"/>
      ```

## Type of Avatars
| type | `male` | `female` | `human` | `identicon` | `initials` | `bottts` | `jdenticon` | `gridy` |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
|PREVIEW|![male](https://avatars.dicebear.com/api/male/seed.svg)|![female](https://avatars.dicebear.com/api/female/seed.svg)|![human](https://avatars.dicebear.com/api/human/seed.svg)|![identicon](https://avatars.dicebear.com/api/identicon/seed.svg)|![initials](https://avatars.dicebear.com/api/initials/seed.svg)|![bottts](https://avatars.dicebear.com/api/bottts/seed.svg)|![jdenticon](https://avatars.dicebear.com/api/jdenticon/seed.svg)|![gridy](https://avatars.dicebear.com/api/gridy/seed.svg)|

## More Info
For more information about the different types of avatars and their individual parameters, visit [Dicebear's Avatars](https://avatars.dicebear.com)