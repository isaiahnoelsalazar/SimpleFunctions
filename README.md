# How to install?
### In build.gradle
```java
dependencies {
    // other existing code
    implementation 'com.github.isaiahnoelsalazar:SimpleFunctions:1.0'
}
```
### In settings.gradle
```java
dependencyResolutionManagement {
    // other existing code
    repositories {
        // other existing code
        maven { url 'https://jitpack.io' }
    }
}
```

# Available methods
- [Check](#check)
- [Convert](#convert)
- [EasySQL](#easysql)
- [FlippableImageView](#flippableimageview)
- [Fullscreen](#fullscreen)
- [RoundedAlertDialog](#roundedalertdialog)

## Check
### hasNumbers
- will check a String for a number
- returns a boolean value
```java
Check.hasNumbers("Sample text"); // returns false
Check.hasNumbers("Sample text 1"); // returns true
```
### hasSymbols
- will check a String for a symbol
- returns a boolean value
```java
Check.hasSymbols("Sample text"); // returns false
Check.hasSymbols("Sample text!"); // returns true
```
### hasSpaces
- will check a String for a space
- returns a boolean value
```java
Check.hasSpaces("Sample_text"); // returns false
Check.hasSpaces("Sample text"); // returns true
```
### howManySecondsLeft
- will compare two Date objects to see how many seconds are left
- returns a double value representing the number of seconds
```java
Date now = new Date("2025/01/01");
Date until = new Date("2025/01/02");
Check.howManySecondsLeft(now, until); // returns 86400.0
```
### howManyMinutesLeft
- will compare two Date objects to see how many minutes are left
- returns a double value representing the number of minutes
```java
Date now = new Date("2025/01/01");
Date until = new Date("2025/01/02");
Check.howManyMinutesLeft(now, until); // returns 1440.0
```
### howManyHoursLeft
- will compare two Date objects to see how many hours are left
- returns a double value representing the number of hours
```java
Date now = new Date("2025/01/01");
Date until = new Date("2025/01/02");
Check.howManyHoursLeft(now, until); // returns 24.0
```
### howManyDaysLeft
- will compare two Date objects to see how many days are left
- returns a double value representing the number of days
```java
Date now = new Date("2025/01/01");
Date until = new Date("2025/01/02");
Check.howManyDaysLeft(now, until); // returns 1.0
```
## Convert
### toRealName
- will capitalize the first character of a given String
- returns a String
```java
Convert.toRealName("sample text"); // returns "Sample text"
```
### toBase64
- will convert a String to its Base64 version
- returns a String
```java
Convert.toBase64("Sample text"); // returns "U2FtcGxlIHRleHQ="
```
### fromBase64
- will convert a Base64 String to its normal version
- returns a String
```java
Convert.fromBase64("U2FtcGxlIHRleHQ="); // returns "Sample text"
```
### dateToDDMMYY
- will convert a Date object to a String in the format of "DD/MM/YY"
- returns a String
```java
Date now = new Date("2025/01/02");
Convert.dateToDDMMYY(now); // returns "2/1/2025"
```
### dateToMMDDYY
- will convert a Date object to a String in the format of "MM/DD/YY"
- returns a String
```java
Date now = new Date("2025/01/02");
Convert.dateToMMDDYY(now); // returns "1/2/2025"
```
### dateToYYMMDD
- will convert a Date object to a String in the format of "YY/MM/DD"
- returns a String
```java
Date now = new Date("2025/01/02");
Convert.dateToYYMMDD(now); // returns "2025/1/2"
```
## EasySQL
### Initialization
```java
EasySQL easySQL = new EasySQL(this);
```
### createTable
- creates a table inside a given database
```java
easySQL.createTable("sampleDB", "sampleTABLE", new String[]{"name:text", "age:int"});
```
### clearTable
- clears a table inside a given database
```java
easySQL.clearTable("sampleDB", "sampleTABLE");
```
### doesTableExist
- checks if a table inside a given database exists
- returns a boolean value
```java
easySQL.doesTableExist("sampleDB", "sampleTABLE");
```
### insertToTable
- inserts a value into a table inside a given database
```java
easySQL.insertToTable("sampleDB", "sampleTABLE", new String[]{"name:Sample", "age:20"});
```
### getTableValues
- returns a List<String> of all values of each column in a table inside a given database
```java
for (String value : easySQL.getTableValues("sampleDB", "sampleTABLE")){
    System.out.println(value);
}
/*
    returns:
    - name:'Sample'
    - age:20
 */
```
### getTableValuesAsArray
- returns a List<String[]> of all rows in a table inside a given database
```java
for (String[] value : easySQL.getTableValuesAsArray("sampleDB", "sampleTABLE")){
    System.out.println(java.util.Arrays.toString(value));
}
/*
    returns:
    - [name:'Sample', age:20]
 */
```
### deleteFromTable
- deletes a value from a table inside a given database using a "column:value" pair String
```java
easySQL.deleteFromTable("sampleDB", "sampleTABLE", "name:Sample");
```
### deleteTable
- deletes a table inside a given database
```java
easySQL.deleteTable("sampleDB", "sampleTABLE");
```
## FlippableImageView
## Fullscreen
### enable
- will enable fullscreen viewing on an activity
```java
Fullscreen.enable(this);
```
### disable
- will disable fullscreen viewing on an activity
```java
Fullscreen.disable(this);
```
## RoundedAlertDialog