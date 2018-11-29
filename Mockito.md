# `verify()`

`verify()` simply verifies if a method was called. Specially useful to test methods which have conditional logic and have method calls for futher operations based on that logic inside an `if` or `switch`.

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
