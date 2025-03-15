![GhostedvpnHackerCatGIF](https://github.com/user-attachments/assets/8355b55e-7b30-487e-bca9-81f8031b620c)
## Install Flutter in Android Studio:
1.Download Flutter SDK <br>
2.Setup Environment Variables.<br>
3.Install Flutter and Dart plugins.<br>
4.agree to all Licenses.<br>
## Here void main() -> It's the first gate which give
 the permission and let go inside flutter project.
### But it directly can't access the widgets.
## For this case helps runApp() -> that give all the access to provide the widgets.
Ex: Button,TextFields,Container,Image,Card etc.<br>
Write Hello World under runApp(): 

##### import 'package:flutter/material.dart';
##### void main() {
 ##### runApp(
    const Center(
      child: Text(
        "Hello, Flutter!",
        textDirection: TextDirection.ltr,  // 👈 Specify text direction
      ),
    ),
#####  );
##### }
![Screenshot 2025-03-15 212700](https://github.com/user-attachments/assets/f49e4207-f335-459f-a080-497bac548e2c)
![Screenshot 2025-03-15 163243](https://github.com/user-attachments/assets/ea634c5b-e49b-45f2-8889-cbc7c9cf2b0f)
### If we don't use the textDirection then there arise an error : 🚨 "No Directionality widget found."
#### Because In Flutter, when a Text widget is placed inside a Center widget without a MaterialApp or Directionality widget, you may encounter this error.If you are not using MaterialApp, you must manually specify the textDirection in the Text widget like this ^

### The Common Widgets:
## 1.AppBar: 
##### import 'package:flutter/material.dart';

##### void main() {
#####  runApp(const MyApp());
##### }

##### class MyApp extends StatelessWidget {
####  const MyApp({Key? key}) : super(key: key);

#####  @override
#####  Widget build(BuildContext context) {
    return MaterialApp(
      // Add MaterialApp here
      home: Scaffold(
        extendBodyBehindAppBar: true,
        appBar: AppBar(
          leading: IconButton(
            onPressed: () {},
            icon: Icon(Icons.menu),
            color: Colors.white,
          ),
          title: Text(
            "AppBar",
            style: TextStyle(color: Colors.white, fontSize: 30),
          ),
          actions: [
            IconButton(
              onPressed: () {},
              icon: Icon(Icons.search),
              color: Colors.white,
            ),
            IconButton(
              onPressed: () {},
              icon: Icon(Icons.safety_check),
              color: Colors.white,
            ),
          ],
          elevation: 0,
          centerTitle: true,
          backgroundColor: Colors.lightBlue,
          shape: RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(20),
          ),
          flexibleSpace: Image.asset(
            "assets/images/yo.png",
            fit: BoxFit.cover,
          ),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: const [
              Text(
                "AppBar Widget",
                style: TextStyle(fontSize: 40, color: Colors.purple),
              ),
              Text(
                "Learn it's properties",
                style: TextStyle(fontSize: 20, color: Colors.black),
              ),
            ],
          ),
        ),
      ),
    );
#####  }
##### }
### Output:
![Screenshot 2025-03-15 171519](https://github.com/user-attachments/assets/e959bbbd-12eb-4e4f-82d3-b1d225d0e632)
