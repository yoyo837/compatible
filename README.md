# Ant Design Compatible

[![NPM version](https://img.shields.io/npm/v/@ant-design/compatible.svg?style=flat)](https://npmjs.org/package/@ant-design/compatible)
[![NPM downloads](http://img.shields.io/npm/dm/@ant-design/compatible.svg?style=flat)](https://npmjs.org/package/@ant-design/compatible)

## Install

```bash
yarn add @ant-design/compatible
```

## Introduction

Helps you to compatible different components between v3 and v4.

For example, Form of v3 api is different with v4:

```jsx
// V3
import { Form, Input, Button } from 'antd';

class MyForm extends React.Component {
  render() {
    return (
      <Form>
        {getFieldDecorator('username')(
          <Input />,
        )}
        <Button>Submit</Button>
      </Form>
    );
  }
}

export default Form.create()(MyForm);
```

Change to:

```jsx
// V4 with compatible
import { LegacyForm as Form, Input, Button } from '@ant-design/compatible';

class MyForm extends React.Component {
  render() {
    return (
      <Form>
        {getFieldDecorator('username')(
          <Input />,
        )}
        <Button>Submit</Button>
      </Form>
    );
  }
}

export default Form.create()(MyForm);
```

Follow Component are provided compatible version:
* Form -> LegacyForm (not yet)
* Mention --> LegacyMention (not yet)
* Icon --> Icon

### Icon
Just import `Icon` from package `@ant-design/compatible` and the reset is almost same as before.

```jsx
// V3
// import { Icon, Button } from 'antd';
// V4 with compatible
import { Icon as LegacyIcon } from '@ant-design/compatible';

class MyIconList extends React.Component {
  render() {
    return (
      <div className="icons-list">
        <Button>hello button</Button>
        <LegacyIcon type="home" />
        <LegacyIcon type="setting" theme="filled" />
        <LegacyIcon type="smile" theme="outlined" />
        <LegacyIcon type="sync" spin />
        <LegacyIcon type="smile" rotate={180} />
        <LegacyIcon type="loading" />
      </div>
    );
  }
}

export default MyIconList;
```
