The ``java.time`` package in [[Java]] contains several classes to work with dates and time.

### LocalDate

This class represents a date without the time component.
It includes the year, month, and day fields.
To check all the methods and parameters go to the official doc [java.time.LocalDate](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html)

```java
LocalDate localDate = LocalDate.of(2023, 1, 15);
```

### LocalDateTime

This class represents a date and time without a time zone.
It includes the year, month, day, hour, minute, and second fields.
To check all the methods and parameters go to the official doc [java.time.LocalDateTime](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html)

```java
LocalDateTime localDateTime = LocalDateTime.of(2023, 1, 15, 15, 30, 45);
```

### DateTimeFormatter

Formatter for printing and parsing date-time objects.
To check all the methods and parameters go to the official doc [java.time.format.DateTimeFormatter](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)

The LocalDateTime and LocalDate have a parse method, that you can pass a DateTimeFormatter object to it, to format the date and time into a specific format.

```java
DateTimeFormatter parser = DateTimeFormatter.ofPattern("dd/MM/yyyy");
LocalDate date = LocalDate.parse("03/12/2007", parser);

DateTimeFormatter printer = DateTimeFormatter.ofPattern("MMMM d, yyyy"); 
printer.format(date);

// Output "December 3, 2007"
```


### Format character cheat sheet

This table represents a cheat sheet to format date and time.

| Pattern Letter | Description                     | Example                       |
|----------------|---------------------------------|-------------------------------|
| `G`            | Era designator (e.g., AD)       | AD                            |
| `y`            | Year (e.g., 2023)               | 2023                          |
| `M`            | Month in year (e.g., January)   | 1, 01, Jan                    |
| `d`            | Day in month (e.g., 15)         | 15                            |
| `h`            | Hour in am/pm (1-12)            | 3                             |
| `H`            | Hour in day (0-23)              | 15                            |
| `m`            | Minute in hour (0-59)           | 30                            |
| `s`            | Second in minute (0-59)         | 45                            |
| `S`            | Millisecond                     | 123                           |
| `E`            | Day name in week (e.g., Friday) | Fri                           |
| `EEEE`         | Full day name in week           | Friday                        |
| `a`            | AM/PM marker                    | AM                            |
| `Z`            | Time zone                       | PST                           |
| `zz`           | Short time zone                 | GMT-08:00                     |

The are other useful applications like for example if you use ``dd`` instead of ``d`` the day if is lower than 10 would add a 0 before: ``09`` 