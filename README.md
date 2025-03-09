OtpView Library

OtpView is a customizable OTP input field for Android applications. It provides a smooth and flexible way to implement OTP input in your app.

Installation

Step 1: Add JitPack Repository

Add the JitPack repository to your project's settings.gradle file (if not already added):

pluginManagement {
    repositories {
        google()
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}

dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}


Step 2: Add Dependency
Add the following dependency to your module-level build.gradle.kts:

dependencies {
    implementation("com.github.Ashu-Hasan:OtpView:1.0")
}

For Gradle (Groovy DSL), use:
dependencies {
    implementation 'com.github.Ashu-Hasan:OtpView:1.0'
}

Usage
XML Implementation
To add the OTP View to your layout:

<com.ash.otpview.OTPTextView
    android:id="@+id/otp_view"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:otpLength="6"
    app:otpBackground="@drawable/bg_pin"
    app:otpTextSize="16sp"
    app:otpSpacing="8dp" />


Kotlin Implementation
In your Activity or Fragment:

val otpView = findViewById<OTPTextView>(R.id.otp_view)
otpView.otpListener = object : OTPListener {
    override fun onOtpEntered(otp: String) {
        Toast.makeText(this@MainActivity, "OTP Entered: $otp", Toast.LENGTH_SHORT).show()
    }
}

Java Implementation
In your Java Activity:

OTPTextView otpView = findViewById(R.id.otp_view);
otpView.setOtpListener(new OTPListener() {
    @Override
    public void onOtpEntered(String otp) {
        Toast.makeText(MainActivity.this, "OTP Entered: " + otp, Toast.LENGTH_SHORT).show();
    }
});

Customization

You can customize OTP input field properties such as:

Attribute - Description - Example Value

otpLength - Sets the number of OTP digits - 4, 6

otpBackground - Background of each input box - @drawable/bg_pin

otpTextSize - Size of OTP text - 16sp

otpSpacing - Space between OTP boxes - 8dp
