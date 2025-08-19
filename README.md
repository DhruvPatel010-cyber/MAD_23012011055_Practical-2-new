# Practical-2

## Aim
Create an Android application to demonstrate functions of Activity Life Cycle and display messages using Logcat, Toast, and Snackbar.

---

## Requirements
- Android Studio
- Kotlin

---

## Description
This application displays "Hello World" in the center of the screen with a yellow(android:background="#FFFF00") background.  
The TextView is styled with:
- Blue text color (android:textColor=@android:color/holo_blue_bright) 
- 27sp font size  (android:textSize="27sp")
- Bold and italic  (android:textStyle="bold|italic")

Activity life cycle methods such as `onCreate`, `onResume`, `onPause`, `onStop`, and `onRestart` are demonstrated by showing messages in:
- Logcat  
- Toast  
- Snackbar  

---

## Code

```kotlin
val TAG = "MainActivity" //in class MainActivity

fun showMessage(msg:String){
        Log.i(TAG, "showMessage: $msg")
        Toast.makeText(this, msg, Toast.LENGTH_SHORT).show()
        Snackbar.make(
            findViewById(R.id.main),
            msg,
            Snackbar.LENGTH_SHORT
        ).show()
    }

override fun onRestart() {
        showMessage("onRestart method is called")
        super.onRestart()
    }

    override fun onResume() {
        showMessage("on resume called")
        super.onResume()
    }

    override fun onPause() {
        showMessage("on pause called")
        super.onPause()
    }

    override fun onStop() {
        showMessage("on stop method called")
        super.onStop()
    }

```
## UI

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="#FFFF00">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"

        android:text="Hello World"
        android:textColor="@android:color/holo_blue_bright"
        android:textSize="27sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        />
</androidx.constraintlayout.widget.ConstraintLayout>
```
---

## Logcat
<img width="1383" height="408" alt="image" src="https://github.com/user-attachments/assets/2a3ca4cb-63d4-49f4-82c4-fe36e0d9ed86" />

---

## Toast and Snakebar
<img width="366" height="805" alt="image" src="https://github.com/user-attachments/assets/61a68dde-e2c1-4dd8-9e9d-728b353ba757" />
