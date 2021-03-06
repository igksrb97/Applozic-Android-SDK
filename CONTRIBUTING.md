# Contributing to Applozic Android SDK
Thanks for taking time to contribute to Applozic SDK.

We would love your contribution to the Applozic SDK. If you are planning to contribute to Applozic SDK, then please follow the below guidelines:

1) Incase of a small change or a minor bug fix, we request you to fork this repo, do the changes in your fork and then create a PR clearly describing the changes and their scope. Please follow our PR guidelines when creating one.
2) Incase of heavy or breaking changes, contact us on email or support before putting in your efforts and time in the development as we may not be able to use the changes as we need to keep the SDK stable so that developers do not need to change the code continuously. So please get in touch before planning to contribute breaking changes.

## Code guidelines:
Please follow the below guidelines:

### Naming conversations:
1) Start variable/method names with a lowercase letter, and use camelCase rather than under_scores. The variable/method name must be meaningfull, even though the scope is very small.
2) Constants (public/private static final) are ALL_CAPS_WITH_UNDERSCORES. Also the modifiers need to be static final.

### Line length:
At max, please limit the line length to 100 characters

### Usage of context:
Do not use Context or **Activity context** everywhere. These contexts must be used only to **Start an activity, service or inflating a layout**
Rest all of the cases, get the context as `ApplozicService.getContext(context)`. Below are few examples:

```java
 ApplozicService.getContext(context).getString(R.string.some_text);
 ApplozicService.getContext(context).getResources();
```

### Imports:
Use fully qualified imports.
```java
android.content.*;   //incorrect
android.content.Intent; //correct
```

### Logging:
Please follow the below guidelines for logging information in the logcat.
1) TAG needs to be defined at a class level. All the logs from the class should be logged under the same tag. Tag should contain the class name.
 For e.g:
 ```java
   class AlConversationService{
     private static final TAG = "AlConversationServiceLogs";
   }
 ```
 2)  Use Applozic's internal method for logging. **Do not use** `Log.d, Log.e` etc. Use the below method:
  ```java
  Utils.printLog(context, TAG, <LOGGING-DATA>);
  ```
  
  ### Commits:
  Please do not commit the build, intermediate or autogenerated files with the code changes. **Your commit needs to have only the code changes, resources additions etc**.
  Please remove the .iml and other build files from the commit.
  
  For any queries you can contact us at support@applozic.com.
