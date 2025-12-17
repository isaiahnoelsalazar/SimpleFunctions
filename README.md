# How to install?
### In build.gradle
```java
dependencies {
    // other existing code
    implementation 'com.github.isaiahnoelsalazar:SimpleFunctions:[latest release version]'
}
```
> Note: Remove the brackets for version
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
- [SimpleList](#simplelist)

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
### Email.addValidDomainName
- adds a valid domain name to the list of valid domain names
```java
Check.Email.addValidDomainName("gmail");
```
### Email.addValidDomainExtension
- adds a valid domain extension to the list of valid domain extensions
```java
Check.Email.addValidDomainExtension("com");
```
### Email.addValidDomain
- adds a valid domain to the list of valid domains
```java
Check.Email.addValidDomain("gmail.com");
```
### Email.shouldUseFullDomain
- sets the checker to use full domains or not
```java
Check.Email.shouldUseFullDomain();

// Or

Check.Email.shouldUseFullDomain(true);

// Or

Check.Email.shouldUseFullDomain(false);
```
### Email.isValid
- checks a String if it is a valid email or not
- will return false if the email domain is not listed in the valid domains
```java
Check.Email.isValid("test@gmail.com"); // returns true
Check.Email.isValid("test@outlook.com"); // returns false
Check.Email.isValid("test@asd.com"); // returns false
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
### Initialization
```xml
<com.github.isaiahnoelsalazar.simplefunctions.FlippableImageView
     android:id="@+id/sample_flippable_image_view"
     android:layout_width="100dp"
     android:layout_height="100dp" />
```
or
```xml
<com.github.isaiahnoelsalazar.simplefunctions.FlippableImageView
     android:id="@+id/sample_flippable_image_view"
     android:layout_width="100dp"
     android:layout_height="100dp"
     android:src="@drawable/sample_image" />
```
or
```xml
<com.github.isaiahnoelsalazar.simplefunctions.FlippableImageView
     android:id="@+id/sample_flippable_image_view"
     android:layout_width="100dp"
     android:layout_height="100dp"
     android:scaleType="centerCrop"
     android:src="@drawable/sample_image" />
```
```java
FlippableImageView flippableImageView = findViewById(R.id.sample_flippable_image_view);
```
### setFrontImage
- set the front image of the flippable image view
```java
flippableImageView.setFrontImage(R.drawable.piece);
```
### setBackImage
- set the back image of the flippable image view
```java
flippableImageView.setBackImage(R.drawable.piece);
```
### setReverseBackImage
- reverses back image of the flippable image view
```java
flippableImageView.setReverseBackImage(true);
```
### flip
- flips the flippable image view
```java
flippableImageView.flip();
```
### instantFlip
- instantly flips the flippable image view
```java
flippableImageView.instantFlip();
```
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
### Initialization
```java
RoundedAlertDialog roundedAlertDialog = new RoundedAlertDialog(this);
```
### setTitle
- set a title for the dialog
```java
roundedAlertDialog.setTitle("Sample title");
```
### setupLeftButton
- setup the left button for the dialog with a specified text and color
```java
roundedAlertDialog.setupLeftButton("Left button");

// Or

roundedAlertDialog.setupLeftButton("Left button", Color.RED);
```
### setupRightButton
- setup the right button for the dialog with a specified text and color
```java
roundedAlertDialog.setupRightButton("Right button");

// Or

roundedAlertDialog.setupRightButton("Right button", Color.RED);
```
### setupLeftButtonOnClick
- setup the OnClick function for the dialog's left button
```java
roundedAlertDialog.setupLeftButtonOnClick(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // do something
    }
});
```
### setupRightButtonOnClick
- setup the OnClick function for the dialog's right button
```java
roundedAlertDialog.setupRightButtonOnClick(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // do something
    }
});
```
## SimpleList
### Initialization
```xml
<com.github.isaiahnoelsalazar.simplefunctions.SimpleList
    android:id="@+id/simple_list_id"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />
```
```java
SimpleList simpleList = findViewById(R.id.simple_list_id);
```
### addItem
- add a String to the list
```java
simpleList.addItem("Sample text 1");
```
### removeItem
- remove a String from the list using its position
```java
simpleList.removeItem(0);
```
### setOnItemClickListener
- set the OnItemClickListener for the list
```java
simpleList.setOnItemClickListener(new SimpleList.OnItemClickListener() {
    @Override
    public void onItemClick(int position) {
        // do something
    }
});
```
### setOnItemLongClickListener
- set the OnItemLongClickListener for the list
```java
simpleList.setOnItemLongClickListener(new SimpleList.OnItemLongClickListener() {
    @Override
    public void onItemLongClick(int position) {
        // do something
    }
});
```
### setPadding
- set the padding for each item in the list
```java
simpleList.setPadding(16);
```
### setPadding
- set individual padding for each item in the list
```java
simpleList.setPadding(24, 16, 8, 12); // left, top, right, bottom
```