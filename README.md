# formik-paste

Super-charged [Paste](https://paste.twilio.design) components using [Formik](https://github.com/jaredpalmer/Formik) to handle form state.

This library lightly wraps Paste components with a required `name: string` prop that connects them to a Formik form field. Simply change form component imports from `@twilio-paste/core` to `formik-paste`, and set their `name` prop. Doing so will link the Paste component with a `Formik` field under the hood!

## Getting started

```bash
npm install formik-paste
```

## Usage

```tsx
import { Button, FormLabel, FormHelpText } from '@twilio-paste/core';
import { Theme } from '@twilio-paste/theme';
import { Formik } from 'formik';
import { FormInput } from 'formik-paste';
import * as React from 'react';

function App() {
  return (
    <Theme.Provider theme="default">
      <Formik
        initialValues={{ emailAddress: '' }}
        onSubmit={(values) => {
          window.alert(JSON.stringify(values));
        }}
      >
        {({ handleSubmit }) => (
          <form onSubmit={handleSubmit}>
            <FormLabel htmlFor="emailAddress">Email Address</FormLabel>
            <FormInput id="emailAddress" name="emailAddress" type="email" placeholder="example@twilio.com" />

            <Button variant="primary" type="submit">
              Submit
            </Button>
          </form>
        )}
      </Formik>
    </Theme.Provider>
  );
}
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Acknowledgements

Heavily inspired by [formik-antd](https://github.com/jannikbuschke/formik-antd/).

## License

[MIT](https://choosealicense.com/licenses/mit/)
