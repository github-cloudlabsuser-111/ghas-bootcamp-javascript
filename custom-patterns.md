# Custom Patterns for Secret Scanning

The goal of this file is to provide bootcamp participants with the regular expressions they need to copy and paste over to create a custom pattern during the bootcamp.

Below are the regular expressions and notes on where to paste them in the Custom Patterns view:

### Main pattern

  ```regex
  [a-zA-Z0-9!.,$%&*+?^_`{|}()[\]\\/~-][a-zA-Z0-9\t !.,$%&*+?^_`{|}()[\]\\/~-]*
  ```

### Before secret pattern

  ```regex
  (?:\A|[^a-zA-Z0-9])(?i)(?:api|jwt|mysql)?[_.-]?(?:[Pp]ass?(?:wo?r?d|code|phrase)|[Pp]wd|secret)[\t ]*(={1,3}|:)[\t ]*(?:["']|b["'])?
  ```

### After secret pattern

  ```regex
  (\z|[\r\n'"])
  ```

This pattern should help identify passwords, such as "Password123!".
