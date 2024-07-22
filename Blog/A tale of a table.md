a feature request came along straight from the user
he wants an integration between our system and another system which is within the MainFrame
until our system came along he used export to excel from the MainFrame system then he edited the excel manually
so the most acceptable solution for him was to have the excel within our system
the 2 most popular packages for that in react are https://reactgrid.com/ and https://iddan.github.io/react-spreadsheet/ I took Idan's component since the look and feel was a better fit
integration was pretty easy and in less than an hour I already had it running (awesome work Idan! )
but than we needed to add 2 more features the first one was filters per coulmn and the second one was row selection (which will allow uploading selected rows)
it took a couple of hours to implement but I got the filters right and added a first column with checkbox for row selection
but once I added the selection part I had to make this component controlled (instead of uncontrolled) 
which made it 10 times slower and that's on my demo excel, the users excel has about 50 times more data
and that's where the sleeves rolled down, after a talk with @schniz we decided to make it uncontrolled and that means to make it a clean new component

so the cleanest way to make it uncontrolled and than upload it's data is to make the table a form element
but since I want only the selected rows the way I did it was to make to form outside the actual table and specify the form name only in the selected rows input's
which is pretty genius idea in my opinon
then to upload the data you can just add a button anywhere with the type="submit" and the form name
and it's even easier with nextjs making the form action a server action

the thing that I didn't like is that in form action you can't really get the response or a nice error handler
that's when I had to wrap the regular react form with my own form
```typescript

import { useCallback } from 'react';

export type FormProps = {
  afterSubmit?: (data?: unknown) => void;
  onError?: (error: unknown) => void;
} & React.DetailedHTMLProps<
  React.FormHTMLAttributes<HTMLFormElement>,
  HTMLFormElement
>;

export function Form(props: FormProps) {
  const { afterSubmit, action: previousAction, ...rest } = props;
  // make action run afterSubmit
  const action = useCallback(
    async (formData: FormData) => {
      let data: unknown;
      if (previousAction) {
        try {
          // @ts-expect-error-next-line -- TODO: fix
          data = await previousAction(formData);
        } catch (error) {
          if (props.onError) {
            props.onError(error);
          }
          return;
        }
      }
      if (afterSubmit) {
        afterSubmit(data);
      }
    },
    [previousAction, afterSubmit]
  );

  return <form {...rest} action={action} />;
}


```

