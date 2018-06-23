# Angular 2 match other field validator

This custom validator for Angular 4 allows you to have fields that must be equal to some other fields.
Such validator is very useful for password confirmation validation, for example.

Besides checking if two values are matching, it also subscribes to changes from other control and re-validates when either of two controls is updated.

# Usage

```ts
private constructForm () {
  this.form = this.formBuilder.group({
    email: ['', [
      Validators.required,
      Validators.email
    ]],
    password: ['', Validators.required],
    repeatPassword: ['', [
      Validators.required,
      matchOtherValidator('password')
    ]]
  });
}
```

More up-to-date validators could be found here: [moebius-mlm/ng-validators](https://github.com/moebius-mlm/ng-validators).