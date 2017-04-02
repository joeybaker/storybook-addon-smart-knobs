# Smart knobs addon for Storybook

This Storybook plugin uses storybook-addon-knobs but creates the knobs automatically based on PropTypes.

This fork is compatible with [@kadira/react-storybook-addon-info](https://github.com/kadirahq/react-storybook-addon-info).

## Installation:

```
npm i storybook-addon-smart-knobs --save-dev
```

## Usage:

```js
import React, { PropTypes } from 'react'
import { storiesOf } from '@kadira/storybook'
import { withKnobs } from '@kadira/storybook-addon-knobs'
import { withSmartKnobs } from 'storybook-addon-smart-knobs'

const Button = ({ children, onClick }) => (
  <button onClick={ onClick }>{ children }</button>
)

Button.propTypes = {
  children: PropTypes.node,
  onClick: PropTypes.func
}

storiesOf('Button')
  .addDecorator(withSmartKnobs)
  .addDecorator(withKnobs)
  .add('simple', () => <Button>Smart knobed button</Button>)

```
