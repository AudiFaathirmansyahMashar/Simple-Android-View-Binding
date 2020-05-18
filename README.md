# Simple-Android-View-Binding
Remove findViewById()

1. Add this after buildTypes in your build.gradle(Module:app)
```java
	viewBinding{  
	  enabled = true  
	}
```

2. Add id to your button
```xml
<Button  
  android:id="@+id/button"  
  android:layout_centerInParent="true"  
  android:text="Show"  
  android:layout_width="wrap_content"  
  android:layout_height="wrap_content"/>
```

3. Type syntax below, in your MainActivity.class
```java
private ActivityMainBinding binding;  
  
@Override  
protected void onCreate(Bundle savedInstanceState) {  
    super.onCreate(savedInstanceState);  
    binding = ActivityMainBinding.inflate(getLayoutInflater());  
    setContentView(binding.getRoot());  
  
    binding.button.setOnClickListener(new View.OnClickListener() {  
        @Override  
		public void onClick(View v) {  
            Toast.makeText(MainActivity.this, "Correct", Toast.LENGTH_SHORT).show();  
        }  
    });  
}
```
