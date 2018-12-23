# `verify()`

`verify()` simply verifies if a method was called. Specially useful to test methods which have conditional logic and have method calls for futher operations based on that logic inside an `if` or `switch`. Another good use case is to test if a subsequest call to a method was made when a method was called which is common in MVP and MVVM architecture where Presenters and ViewModel often call other methods for actual oprations when the bridge methods are called.

Further variation include
 - `verifyZeroInterations()`
 - `verify(<mock>, times(<count>))`
 - `verify(<mock>, atLeast(<count>))`
 - `verify(<mock>, atMost(<count>))`
 - `verify(<mock>, never(<count>))`
 - `verify(<mock>, atLeastOnce(<count>))`
 - `verifyNoMoreInterations()`

Additional Links
 - [Mockito Verify Cookbook \| Baeldung](https://www.baeldung.com/mockito-verify)
 - [Mockito Verify - JournalDev](https://www.journaldev.com/21855/mockito-verify)

# `ArgumentCaptor`

`ArgumentCaptor` is a way to capture method arguments and then assert or further test these arguments. 

Steps:

1. Create an `ArgumentCaptor` field object using `@Captor`
```java
@Captor
ArgumentCaptor<ArgumentObjectType> acArgument;
```

2. Capture the argument to be verified in the `verify()` call
```java
verify(mock).mockMethod(acARgument.capture());
```
 - A single `ArgumentCaptor` can be used to capture arguments mutiple times of the same type in a single test

3. Use `getValue()` or `getValues()` on `ArgumentCaptor` depending if multiple captures were made to fetch the captured argument and then assert or further test the argument/s.

Additional Links
 - [Mockito ArgumentCaptor](https://www.journaldev.com/21892/mockito-argumentcaptor-captor-annotation)
