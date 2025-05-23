 Code Explanation: MainActivity.java
This is the main activity class for the MyFlora Android app. Here's a breakdown of what this code does:

Extends AppCompatActivity: This class is the base for activities that use the modern Android components and features while maintaining backward compatibility.

EdgeToEdge.enable(this): This enables edge-to-edge display, allowing your app to draw behind system bars like the status bar and navigation bar for a more immersive UI.

setContentView(R.layout.activity_main): Sets the layout defined in activity_main.xml as the UI for this activity.

Handling Window Insets:

java
Copy
Edit
ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
    Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
    v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
    return insets;
});
This part ensures that your UI respects system UI elements like the status bar and navigation bar by applying appropriate padding dynamically. It retrieves the insets and sets them as padding for the root view with ID main.

📝 Notes
Make sure your activity_main.xml layout has a root view with the ID @+id/main for this to work properly.

This approach provides a modern and responsive layout experience on all devices, especially those with gesture navigation or display cutouts.

