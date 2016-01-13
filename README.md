# AuthModuleRequirements

## Top Level Requirements for Authentication Module

These are the requirements for a Web Application Authentication Module.

A Web Application should honor these requirements so that 3rd party
software providers can implement an authentication module
that can authenticate the user with e.g. two factors like with
privacyIDEA.

* It **must** be possible to implement an AuthModule in 
  different levels of details.
  It should be possible to implement the simplest form
  of an AuthModule in less than 60 lines of code.

* An AuthModule **must** not be responsible for:

  - Checking if a user exists
  - Returning user information
  - Managing of users
  - Authorization

  The AuthModule **may** _optionally_ do such things.
  But it must not be mandatory!

* The simplest way for an AuthModule implementation should
  be a password verification.
  The simplest form of an AuthModule should be *one* *function*
  accepting username and password and returning something like
  "true" or "false".

  I.e. the Web Application should call such a function from
  within its usual login process.

* A more complex AuthModule should be able to authenticate
  the user with something else than a username and password.
  For this to work, an AuthModule must be able to replace 
  the UI of the Login process.

  I.e. the Web Application should be able to call an
  external login process and only use the result of
  this login process.

* A more complex AuthModule should be able to provide its
  own authentication workflows.
  Many two factor authentications nowadays work by
  challenge response, two steps or with additional
  javascripts (like U2F).

  The AuthModule **must** have the control of the login 
  UI within the login process, so that it can provide several
  login screens.

## Implementation suggestion / example

  
  


