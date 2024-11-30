# Assignment-1
ScrollView xmlns:android="http://schemas.android.com/apk/res/android" android:id="@+id/back" android:layout_width="match_parent" android:layout_height="match_parent"  

android:background="@color/material_dynamic_neutral40">  

  

<LinearLayout android:layout_width="match_parent" android:layout_height="wrap_content" android:gravity="center_horizontal" android:orientation="vertical" android:padding="20dp">  

  

<TextView android:layout_marginTop="30dp" android:id="@+id/tvTitle" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginBottom="20dp" android:text="Sign Up Form" android:textColor="@color/white" 

android:textSize="30sp" android:textStyle="bold" />  

  

<EditText android:id="@+id/etName" android:layout_width="match_parent" android:layout_height="wrap_content" android:layout_marginTop="20dp" android:layout_marginBottom="10dp" android:background="@drawable/custom_edittext" android:hint="Enter Name" android:inputType="textPersonName" android:padding="12dp" android:textColor="@color/black"/>  

  

<EditText android:id="@+id/etContact" android:layout_width="match_parent" android:layout_height="wrap_content" android:layout_marginBottom="10dp" android:background="@drawable/custom_edittext" android:hint="Enter Contact Number" android:inputType="phone" android:maxLength="10" android:padding="12dp"  android:textColor="@color/black"/>  

  

<EditText android:id="@+id/etEmail" android:layout_width="match_parent" android:layout_height="wrap_content" android:layout_marginBottom="10dp" android:background="@drawable/custom_edittext" android:hint="Enter Email" android:inputType="textEmailAddress" android:padding="12dp" 

android:textColor="@color/black"/>  

  

<EditText android:id="@+id/etPassword" android:layout_width="match_parent" android:layout_height="wrap_content" android:layout_marginBottom="10dp" android:background="@drawable/custom_edittext" android:hint="Enter Password" 

android:inputType="textPassword" android:padding="12dp" android:textColor="@color/black"/>  

  

<EditText android:id="@+id/etAddress" android:layout_width="match_parent" android:layout_height="wrap_content" android:layout_marginBottom="20dp" android:background="@drawable/custom_edittext" android:hint="Enter Address" android:inputType="textPostalAddress" android:padding="12dp" 

android:textColor="@color/black"/>  

  

<Button android:id="@+id/btnSubmit" android:layout_width="272dp" android:layout_height="wrap_content" android:layout_marginTop="10dp" android:layout_marginBottom="20dp" android:backgroundTint="@color/white" android:padding="12dp" android:text="Submit" android:textColor="@color/black" android:textSize="20dp" />  

</LinearLayout>  

</ScrollView>  

  

  

● MainActivity.kt  package com.example.assignment1  

  

import android.os.Bundle import android.text.TextUtils import android.widget.Button import android.widget.EditText import android.widget.Toast import androidx.activity.enableEdgeToEdge import androidx.appcompat.app.AppCompatActivity import androidx.core.view.ViewCompat import androidx.core.view.WindowInsetsCompat  

  

class MainActivity : AppCompatActivity() {  override fun onCreate(savedInstanceState: Bundle?) {  super.onCreate(savedInstanceState) setContentView(R.layout.activity_main) val etName = findViewById<EditText>(R.id.etName) val etContact =  findViewById<EditText>(R.id.etContact) val etEmail = 

findViewById<EditText>(R.id.etEmail)  

val etPassword = findViewById<EditText>(R.id.etPassword) val 

etAddress = findViewById<EditText>(R.id.etAddress) val btnSubmit = findViewById<Button>(R.id.btnSubmit)  

  

btnSubmit.setOnClickListener {  val name = etName.text.toString().trim() val contact = 

etContact.text.toString().trim() val email = etEmail.text.toString().trim() val password = etPassword.text.toString().trim() val address = etAddress.text.toString().trim()  

  

when {  

TextUtils.isEmpty(name) -> etName.error = "Name is required"  

TextUtils.isEmpty(contact) -> etContact.error = "Contact number is required" contact.length != 10 -> etContact.error = "Contact must be 10 digits" TextUtils.isEmpty(email) -> etEmail.error = "Email is required"  

!android.util.Patterns.EMAIL_ADDRESS.matcher(email).matches() -> etEmail.error = "Enter a valid email"  

TextUtils.isEmpty(password) -> etPassword.error = "Password is required" 

TextUtils.isEmpty(address) -> etAddress.error = "Address is required" else -> {  

Toast.makeText(this, "Sign-Up Successful!", Toast.LENGTH_SHORT).show()  

}  

}  

}  

}  

}  
