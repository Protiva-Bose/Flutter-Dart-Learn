![GhostedvpnHackerCatGIF](https://github.com/user-attachments/assets/8355b55e-7b30-487e-bca9-81f8031b620c)
## Install Flutter in Android Studio:
1.Download Flutter SDK <br>
2.Setup Environment Variables.<br>
3.Install Flutter and Dart plugins.<br>
4.agree to all Licenses.<br>

## There are two types of widgets:
#### 1.Stateless widget:
##### Image(Asset/Network)
##### Icon(Material/FontAwesome)
##### Container
##### Button(Elavated/Outline)
##### AppBar(Action Buttons)
##### Row,Column,Expanded
##### ListView
##### ListView.builder()
##### Navigation drawer
##### Floating Action Button
##### Stack

#### 2.Stateful widget:
##### 1.Flutter navigation
##### 2.Radio Button
##### 3.TextField(TextField/TextFormField)
##### 4.CheckBox
##### 5.DropDown

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
            borderRadius: BorderRadius.vertical(bottom: Radius.circular(20),
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

## 2. Row,Column and Expanded widgets:
Flutter provides Row and Column widgets for layout management, while Expanded helps adjust child widget sizes dynamically.
#####  Row(
 ##### mainAxisAlignment: MainAxisAlignment.spaceAround, // Spaces elements evenly
 ##### children: [
    Icon(Icons.star, size: 50),
    Icon(Icons.favorite, size: 50),
    Icon(Icons.thumb_up, size: 50),
#####  ],
##### )
✅ Use when placing widgets side by side horizontally.<br>
✅ Handles overflow issues by using Expanded or Flexible.

##### Column(
#####  mainAxisAlignment: MainAxisAlignment.center, // Centers children vertically
#####  crossAxisAlignment: CrossAxisAlignment.start, // Aligns text to the left
#####  children: [
    Text("Hello"),
    Text("Flutter"),
    Text("World"),
#####  ],
##### )
✅ Use when stacking widgets vertically.<br>
✅ Ideal for forms, lists, and stacked UI layouts.

#### The Expanded widget forces its child to take all available space inside Row or Column.But we can fixed the size what we want by using -> flex:2....
##### Row(
#####  children: [
    Expanded(
      child: Container(
        color: Colors.red,
        height: 100,
      ),
    ),
    Expanded(
      child: Container(
        color: Colors.blue,
        height: 100,
      ),
    ),
#####  ],
##### )
![Screenshot 2025-03-15 221416](https://github.com/user-attachments/assets/034545f5-0bd5-46c7-98a1-820816b6c67e)
### Another:
##### Column(
#####  children: [
    Expanded(
      child: Row(
        children: [
          Expanded(child: Container(color: Colors.red)),
          Expanded(child: Container(color: Colors.green)),
        ],
      ),
    ),
    Expanded(
      child: Container(color: Colors.blue),
    ),
 ##### ],
##### )
![Screenshot 2025-03-15 221558](https://github.com/user-attachments/assets/be34b36e-0740-4fa1-a03f-f7b9444265c8)

 ###  Write code with flex :
 ##### import 'package:flutter/material.dart';

##### void main() {
#####  runApp(const MyApp());
##### }

##### class MyApp extends StatelessWidget {
#####  const MyApp({Key? key}) : super(key: key);

#####  @override
#####  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: const Text('Expanded Flex Example')),
        body: Column(
          children: [
            Expanded(
              flex: 2, // Takes 2 parts of the height
              child: Container(color: Colors.orange),
            ),
            Expanded(
              flex: 3, // Takes 3 parts of the height
              child: Container(color: Colors.purple),
            ),
            Expanded(
              flex: 1, // Takes 1 part of the height
              child: Container(color: Colors.teal),
            ),
          ],
        ),
      ),
    );
#####  }
##### }
![Screenshot 2025-03-15 221939](https://github.com/user-attachments/assets/36e7224a-3aa9-4d00-80b7-ef385f792b3f)

## 3.ListView and ListView Builder:
#### 1️⃣ ListView Widget (Simple, but Less Efficient)<br>
Loads all items at once, which can cause performance issues for large lists.<br>
Suitable for small, static lists.<br>
Uses a children property to hold all widgets inside a list.<br>

### Some actions of the ListView widget:
#### 1️⃣ itemExtent: 100,
Sets a fixed height (or width for horizontal scrolling) for each item in the list.<br>
Helps optimize performance by reducing calculations for dynamic item heights.<br>

#### 2️⃣ reverse: false,
Determines the direction of list scrolling:<br>
true → List starts from the bottom and scrolls up.<br>
false (default) → List starts from the top and scrolls down.<br>

#### 3️⃣ scrollDirection: Axis.vertical,
Defines whether the list scrolls vertically or horizontally:<br>
Axis.vertical → Scrolls up & down (default).<br>
Axis.horizontal → Scrolls left & right.<br>

#### 4️⃣ shrinkWrap: true,
If true, ListView only takes the required space instead of filling the entire screen.<br>
Useful when ListView is inside another scrollable widget (e.g., Column or SingleChildScrollView).<br>

### Code:
 ##### body:
        SafeArea(child:
            Container(
              child: ListView(
                itemExtent: 100,
                reverse: false,
                scrollDirection: Axis.vertical,
                shrinkWrap: true,

                children: [
                  ListTile(
                    leading: CircleAvatar(child: Icon(Icons.alarm_rounded),backgroundColor: Colors.brown.shade200,),
                    title: Text("Title"),
                    subtitle: Text("SubTitle of this title"),
                    trailing: Icon(Icons.alarm_rounded),
                    onTap: (){},
                    tileColor: Colors.brown.shade100,
                  ),
                  ListTile(
                    leading: CircleAvatar(child: Icon(Icons.alarm_rounded),backgroundColor: Colors.blue.shade200,),
                    title: Text("Title"),
                    subtitle: Text("SubTitle of this title"),
                    trailing: Icon(Icons.alarm_rounded),
                    onTap: (){},
                    tileColor: Colors.blue.shade100,
                  ),
                ],
              ),
            )
      )

![Screenshot 2025-03-15 225912](https://github.com/user-attachments/assets/b592fa0f-230d-4be3-949a-7a5a29269fe8)


## ListView Builder:
#### 2️⃣ ListView.builder (Efficient for Large Lists)
Creates items dynamically as the user scrolls (better performance).<br>
Uses itemBuilder to generate items on demand.<br>
Recommended for large datasets.<br>

##### body: SafeArea(
          child: Container(
            child: ListView.builder(
              itemCount: 20, // Added a fixed item count
              itemBuilder: (context, index) {
                return ListTile(
                  leading: CircleAvatar(
                    child: Icon(Icons.alarm_rounded),
                    backgroundColor: Colors.brown.shade200,
                  ),
                  title: Text("Title $index"),
                  subtitle: Text("Subtitle of item $index"),
                  trailing: Icon(Icons.alarm_rounded),
                  tileColor: Colors.brown.shade100,
                  onTap: () {},
                );
              },
            ),
          ),
        ),
![Screenshot 2025-03-15 231945](https://github.com/user-attachments/assets/e51135d9-4d8a-435c-9530-167f67df986a)

## Another:
##### import 'package:flutter/material.dart';

##### void main() {
#####   runApp( MyApp());
##### }

##### class MyApp extends StatelessWidget {
#####    MyApp({Key? key}) : super(key: key);
   
#####  List<String> products =["University","campus","Class"];
#####  List<String> productsDetails =["University name Niter","campus is beautiful","Class started in morning"];
#####  List<int> id =[41,20,467];
#####  @override
#####  Widget build(BuildContext context) {
    return MaterialApp(
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
            borderRadius: BorderRadius.vertical(bottom: Radius.circular(20)),
          ),
          flexibleSpace: Image.asset(
            "assets/images/yo.png",
            fit: BoxFit.cover,
          ),
        ),
        body: SafeArea(
          child: Container(
            child: ListView.builder(
              itemCount: products.length, // Added a fixed item count
              itemBuilder: (context, index) {
                return ListTile(
                  leading: CircleAvatar(
                    child: Text(products[index][0]),
                    backgroundColor: Colors.blue.shade200,
                  ),
                  title: Text(products[index]),
                  subtitle: Text(productsDetails[index]),
                  trailing: Text(id[index].toString()),
                  // tileColor: Colors.brown.shade100,
                  onTap: () {},
                );
              },
            ),
          ),
        ),
      ),
    );
#####  }
##### }
![Screenshot 2025-03-16 010139](https://github.com/user-attachments/assets/074d93ad-379e-46b7-9c73-a789de1d3b02)

## 4.Navigation Drawer:
##### Navigation Drawer in Flutter
A Navigation Drawer in Flutter is a slide-in panel (usually from the left) that provides navigation options for an app. It is commonly used to navigate between different sections or screens in an app.

### .................
  ###### @override
######  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        extendBodyBehindAppBar: true,
        appBar: AppBar(
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
            borderRadius: BorderRadius.vertical(bottom: Radius.circular(20)),
          ),
          // flexibleSpace: Image.asset(
          //   "assets/images/yo.png",
          //   fit: BoxFit.cover,
          // ),
        ),
 ####       drawer: Drawer(
          child: ListView(
            children: [
              UserAccountsDrawerHeader(
                accountName: Text("protiva.bose06@gmail.com"),
                accountEmail: Text("Done project with Protiva"),
                currentAccountPicture: CircleAvatar(
                  foregroundImage: AssetImage("assets/images/yo.png"),
                ),
                otherAccountsPictures: [
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                ],
              ),
              ListTile(
                leading: Icon(Icons.home),
                title: Text("Home"),
                onTap: (){},
              ),
              ListTile(
                leading: Icon(Icons.label),
                title: Text("Label"),
                onTap: (){},
              ),
            ],
          ),
###### backgroundColor: Colors.white,
        ),
        body: SafeArea(
          child: ListView.builder(
            itemCount: products.length,
            itemBuilder: (context, index) {
              return ListTile(
                leading: CircleAvatar(
                  child: Text(products[index][0]),
                  backgroundColor: Colors.blue.shade200,
                ),
                title: Text(products[index]),
                subtitle: Text(productsDetails[index]),
                trailing: Text(id[index].toString()),
                onTap: () {},
              );
            },
          ),
        ),
      ),
    );
######  }
###### }

![Screenshot 2025-03-17 124921](https://github.com/user-attachments/assets/4f06250a-7c22-4037-ac95-4e76f2be78a4)
![Screenshot 2025-03-17 125022](https://github.com/user-attachments/assets/8c8e1aae-f967-419b-9278-1b01042c0ff8)


## 5.Floating Action Button:
#### A Floating Action Button (FAB) is a circular button that floats above the UI, typically used for a primary action in an app (e.g., adding a new item, sending a message, etc.).It creates a custom widgets by adding multiple widgets.

###### home: Scaffold(
        extendBodyBehindAppBar: true,
        appBar: AppBar(
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
            borderRadius: BorderRadius.vertical(bottom: Radius.circular(20)),
          ),
          // flexibleSpace: Image.asset(
          //   "assets/images/yo.png",
          //   fit: BoxFit.cover,
          // ),
        ),

###        floatingActionButtonLocation: FloatingActionButtonLocation.centerFloat,
        floatingActionButton: FloatingActionButton(onPressed: (){},
        child: Icon(Icons.add),
          backgroundColor: Colors.blue,
          foregroundColor: Colors.black,
        ),
###        bottomNavigationBar: BottomAppBar(
          color: Colors.blueAccent.shade100,
          child:

          Row(
            children:[
               Column(
                 children: [
                   Icon(Icons.home),
                   Text("Home"),
                 ],
               ),

              SizedBox(
                width: 140,
              ),
              Column(
                children: [
                  Icon(Icons.settings),
                  Text("Settings"),
                ],
              ),
              SizedBox(
                width: 140,
              ),
              Column(
                children: [
                  Icon(Icons.shop),
                  Text("Shop"),
                ],
              ),
            ]


          ),
        ),
        drawer: Drawer(
          child: ListView(
            children: [
              UserAccountsDrawerHeader(
                accountName: Text("protiva.bose06@gmail.com"),
                accountEmail: Text("Done project with Protiva"),
                currentAccountPicture: CircleAvatar(
                  foregroundImage: AssetImage("assets/images/yo.png"),
                ),
                otherAccountsPictures: [
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                ],
              ),
              ListTile(
                leading: Icon(Icons.home),
                title: Text("Home"),
                onTap: (){},
              ),
              ListTile(
                leading: Icon(Icons.label),
                title: Text("Label"),
                onTap: (){},
              ),
            ],
          ),
###### backgroundColor: Colors.white,
        ),
        body: SafeArea(
          child: ListView.builder(
            itemCount: products.length,
            itemBuilder: (context, index) {
              return ListTile(
                leading: CircleAvatar(
                  child: Text(products[index][0]),
                  backgroundColor: Colors.blue.shade200,
                ),
                title: Text(products[index]),
                subtitle: Text(productsDetails[index]),
                trailing: Text(id[index].toString()),
                onTap: () {},
              );
            },
          ),
        ),
      ),

![Screenshot 2025-03-17 132029](https://github.com/user-attachments/assets/d46fb492-6c65-484d-a0d1-9054503ca65c)

## 6.Stack and Positioned widgets:
#### 1. Stack Widget
The Stack widget places its children on top of each other. It's useful when you want to layer widgets, like images with text on top.

#### 2. Positioned Widget
The Positioned widget is used inside a Stack to place a widget at a specific position using top, left, right, or bottom properties.


###### body: SafeArea(
######  child: Center(
            child: Stack(
              alignment: Alignment.center,
              children: [
                Container(
                  width: 300,
                  height: 200,
                  color: Colors.blueAccent,
                ),
                Container(
                  width: 200,
                  height: 100,
                  color: Colors.grey,
                ),
                Container(
                  width: 100,
                  height: 50,
                  color: Colors.purple,
                )
              ],
            ),
          ),

        ),
![Screenshot 2025-03-17 134839](https://github.com/user-attachments/assets/e4a60e47-a3fa-4c4b-854b-348a002aa68d)

### Now uisng Positioned:
###### Positioned(
                  bottom: 0,
                  child:   Container(
                  width: 200,
                  height: 100,
                  color: Colors.grey,
                ),),

![image](https://github.com/user-attachments/assets/9f07d91c-d420-456a-9628-781c8234e829)

## 7.TextField:
A TextField in Flutter is used to take user input. It's commonly used for forms, search bars, and login screens.Both TextField and TextFormField are used for user input in Flutter, but TextFormField offers more features for forms, like validation.
#### Two ways to get data from TextField:
##### 1. onChanged() event of TextField
##### 2. use Controller or ID to hook ***

## First Process:


###### 🔐 import 'package:flutter/material.dart';

###### void main() {
######  runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget { // Change to StatefulWidget
######  @override
######  _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  var _uniname = ""; // Initialize variable

 ###### void _updateText(val) {
    setState(() {
      _uniname = val; // Update state variable
    });
 ######  }
  
 ###### @override
######  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
######  body: SafeArea(
###### child: Container(
          padding: EdgeInsets.all(20.0),
          child: ListView(
            children: [
              TextFormField(
                onChanged: (val){
              _updateText(val);
                },
                decoration: InputDecoration(
                  labelText: "Versity Name",
                  prefixIcon: Icon(Icons.verified_user_outlined),
                  border: OutlineInputBorder()
                ),
              ),
              Text("The versity name is $_uniname"),
            ],
          ),
        ),
        ),
      ),
    );
######  }
###### }


![Screenshot 2025-03-17 235104](https://github.com/user-attachments/assets/18d6e764-c63b-4ebf-88cf-8e8cade6bdb3)



## Second Process:


🔐 ###### import 'package:flutter/material.dart';

###### void main() {
######  runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget {
######  @override
######  _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  final TextEditingController _uniController = TextEditingController();
 ###### String _uniname = "";

 ###### @override
######  void initState() { // Corrected method name
    super.initState();
    _uniController.addListener(_updateText);
 ###### }

 ###### void _updateText() { // No parameter needed
    setState(() {
      _uniname = _uniController.text; // Get the latest text
    });
 ###### }

 ###### @override
 ###### Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
       body: SafeArea(
        child: Container(
          padding: EdgeInsets.all(20.0),
          child: ListView(
            children: [
              TextFormField(
                controller: _uniController,
                onChanged: (val){
              _updateText();
                },
                decoration: InputDecoration(
                  labelText: "Versity Name",
                  prefixIcon: Icon(Icons.verified_user_outlined),
                  border: OutlineInputBorder()
                ),
              ),
###### Text("The versity name is ${_uniController.text}"),
            ],
          ),
        ),
        ),
      ),
    );
    }
![Screenshot 2025-03-18 014348](https://github.com/user-attachments/assets/a00911b9-29af-45eb-ab72-4d09cc6dccbe)


https://github.com/user-attachments/assets/c84802f6-18d5-4344-b36f-c2d36abb1509



## Third Process:

###### 🔐 import 'package:flutter/material.dart';

###### void main() {
 ###### runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget {
######  @override
######  _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  final TextEditingController _uniController = TextEditingController();
######  String _uniname = "";

######  @override
######  void initState() { // Corrected method name
    super.initState();
    _uniController.addListener(_updateText);
######  }

 ###### void _updateText() { // No parameter needed
    // setState(() {
    //   _uniname = _uniController.text; // Get the latest text
    // });
 ###### }

 ###### @override
 ###### Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        extendBodyBehindAppBar: true,
        appBar: AppBar(
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
            borderRadius: BorderRadius.vertical(bottom: Radius.circular(20)),
          ),
          // flexibleSpace: Image.asset(
          //   "assets/images/yo.png",
          //   fit: BoxFit.cover,
          // ),
        ),

        floatingActionButtonLocation: FloatingActionButtonLocation.centerFloat,
        floatingActionButton: FloatingActionButton(onPressed: (){},
        child: Icon(Icons.add),
          backgroundColor: Colors.blue,
          foregroundColor: Colors.black,
        ),
        bottomNavigationBar: BottomAppBar(
          color: Colors.blueAccent.shade100,
          child: Row(
            children:[
               Column(
                 children: [
                   Icon(Icons.home),
                   Text("Home"),
                 ],
               ),

              SizedBox(
                width: 140,
              ),
              Column(
                children: [
                  Icon(Icons.settings),
                  Text("Settings"),
                ],
              ),
              SizedBox(
                width: 140,
              ),
              Column(
                children: [
                  Icon(Icons.shop),
                  Text("Shop"),
                ],
              ),
            ]


          ),
        ),
        drawer: Drawer(
          child: ListView(
            children: [
              UserAccountsDrawerHeader(
                accountName: Text("protiva.bose06@gmail.com"),
                accountEmail: Text("Done project with Protiva"),
                currentAccountPicture: CircleAvatar(
                  foregroundImage: AssetImage("assets/images/yo.png"),
                ),
                otherAccountsPictures: [
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                  CircleAvatar(
                    foregroundImage: AssetImage("assets/images/yo.png"),
                  ),
                ],
              ),
              ListTile(
                leading: Icon(Icons.home),
                title: Text("Home"),
                onTap: (){},
              ),
              ListTile(
                leading: Icon(Icons.label),
                title: Text("Label"),
                onTap: (){},
              ),
            ],
          ),
               backgroundColor: Colors.white,
        ),
        body: SafeArea(
          // child: ListView.builder(
          //   itemCount: products.length,
          //   itemBuilder: (context, index) {
          //     return ListTile(
          //       leading: CircleAvatar(
          //         child: Text(products[index][0]),
          //         backgroundColor: Colors.blue.shade200,
          //       ),
          //       title: Text(products[index]),
          //       subtitle: Text(productsDetails[index]),
          //       trailing: Text(id[index].toString()),
          //       onTap: () {},
          //     );
          //   },
          // ),
          // child: Center(
          //   child: Stack(
          //     alignment: Alignment.center,
          //     children: [
          //       Container(
          //         width: 300,
          //         height: 200,
          //         color: Colors.blueAccent,
          //       ),
          //       Positioned(
          //         bottom: 0,
          //         child:   Container(
          //         width: 200,
          //         height: 100,
          //         color: Colors.grey,
          //       ),),
          //
          //       Container(
          //         width: 100,
          //         height: 50,
          //         color: Colors.purple,
          //       )
          //     ],
          //   ),
          // ),
        child: Container(
          padding: EdgeInsets.all(20.0),
          child: ListView(
            children: [
              TextFormField(
                controller: _uniController,
              //   onChanged: (val){
              // _updateText(val);
              //   },
                decoration: InputDecoration(
                  labelText: "Versity Name",
                  prefixIcon: Icon(Icons.verified_user_outlined),
                  border: OutlineInputBorder()
                ),
              ),



              SizedBox(height: 60),
              Builder(
                builder: (context) {
                  return myBtn(context);
                },
              ),



              // Text("The versity name is $_uniname"),
              // Text("The versity name is ${_uniController.text}"),
            ],
          ),
        ),
        ),
      ),
    );
    }
######  OutlinedButton myBtn(BuildContext context){
    return OutlinedButton(
      style: OutlinedButton.styleFrom(minimumSize: const Size(200,50)),
      onPressed: (){
        Navigator.push(context,MaterialPageRoute(builder: (context){
          return Details(uniname: _uniController.text,);
        }),
        );
      },
      child: Text("Submit the Form".toUpperCase(),
        style: TextStyle(fontWeight: FontWeight.bold),),
    );
######  }
###### }

###### class Details extends StatelessWidget {
######   Details({Key?key,required this.uniname}): super(key: key);


######  String  uniname;



######  @override
######  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Details"),
        leading: IconButton(onPressed: (){Navigator.pop(context);}, icon: Icon(Icons.arrow_back),
        ),
      ),
      body: Container(
        padding: EdgeInsets.all(10),
        child: ListView(
          children: [
            ListTile(

              leading: Icon(Icons.account_balance_wallet_outlined),
              title: Text("University name"),
            )
          ],
        ),
      )
    );
######  }
###### }



## 7.CheckBox:(CheckBox/CheckBoxListTile)

#### Properties of Checkbox
##### Property	    Description
value	             Boolean value (true for checked, false for unchecked).
onChanged	         Callback function triggered when the checkbox is toggled.
activeColor	       The color of the checkbox when checked.
checkColor	        The color of the checkmark inside the checkbox.
tristate	          Allows three states (true, false, and null).
shape	             Customizes the shape of the checkbox.
side	              Defines the border style of the checkbox.


#### Properties of CheckboxListTile
##### Property	     Description
value	             Boolean value (true for checked, false for unchecked).
onChanged	         Callback function triggered when toggled.
title	             A widget for the main label (usually Text).
subtitle	          A widget for additional description.
isThreeLine	       If true, forces three lines of text.
dense	             Reduces the height of the tile for compact layouts.
controlAffinity   	Determines whether the checkbox is leading or trailing.
activeColor	       The color of the checkbox when checked.
checkColor	        The color of the checkmark inside the checkbox.
tileColor	         Background color of the tile.
shape	             Defines a custom shape for the tile.
enabled	           Whether the tile is interactive.


### Code:
###### import 'package:flutter/material.dart';

###### void main() {
######  runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget {
######  @override
######   _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  final TextEditingController _uniController = TextEditingController();
######  String _uniname = "";


######  bool? _isChecked,_listTileCheckBox = false;


######  @override
######  void initState() {
    super.initState();
    _uniController.addListener(_updateText);
 ###### }

######  void _updateText() {
    setState(() {
      _uniname = _uniController.text;
    });
######  }

######  @override
######  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text(
            "AppBar",
            style: TextStyle(color: Colors.white, fontSize: 30),
          ),
          centerTitle: true,
          backgroundColor: Colors.lightBlue,
        ),
        body: SafeArea(
          child: Container(
            padding: EdgeInsets.all(20.0),
            child: ListView(
              children: [
                TextFormField(
                  controller: _uniController,
                  decoration: InputDecoration(
                    labelText: "University Name",
                    prefixIcon: Icon(Icons.verified_user_outlined),
                    border: OutlineInputBorder(),
                  ),
                ),
                SizedBox(height: 20),
                Row(
                  children: [
                    Checkbox(
                      checkColor: Colors.white,
                      activeColor: Colors.deepPurple,
                      tristate: true,
                      value: _isChecked,
                      onChanged: (val) {
                        setState(() {
                          _isChecked = val;
                        });
                      },
                    ),
                    Text("I agree to the terms"),
                    Expanded(  // Wrap CheckboxListTile inside Expanded
                      child: CheckboxListTile(
                        value: _listTileCheckBox,
                        title: Text("Check",style: TextStyle(fontSize: 15),),
                        onChanged: (val) {
                          setState(() {
                            _listTileCheckBox = val;
                          });
                        },
                        controlAffinity: ListTileControlAffinity.leading,
                      ),
                    ),
                  ],
                ),

                SizedBox(height: 20),
                Text("The university name is: $_uniname"),
              ],
            ),
          ),
        ),
      ),
    );
######  }
###### }

## Here main used :

##### bool? _isChecked,_listTileCheckBox = false;.................. Under class _MyAppState extends State<MyApp> {.....}

##### Checkbox(
                      checkColor: Colors.white,
                      activeColor: Colors.deepPurple,
                      tristate: true,
                      value: _isChecked,
                      onChanged: (val) {
                        setState(() {
                          _isChecked = val;
                        });
                      },
                    ),
                    Text("I agree to the terms"),
                    Expanded(  // Wrap CheckboxListTile inside Expanded
                      child: CheckboxListTile(
                        value: _listTileCheckBox,
                        title: Text("Check",style: TextStyle(fontSize: 15),),
                        onChanged: (val) {
                          setState(() {
                            _listTileCheckBox = val;
                          });
                        },
                        controlAffinity: ListTileControlAffinity.leading,
                      ),
                    ),

https://github.com/user-attachments/assets/a1091e38-dfa7-4bb6-bf3f-4ea45937eaed


## 8.RadioButton():
#### There are two types to create it :
#### 1.setState() to update    2. custom widget stateless => setState in this class
### ✨ First Method: ( 1.setState() to update )
### Code:
###### import 'package:flutter/material.dart';

#### enum ProductTypeEnum {Downloadable,Deliverable}


###### void main() {
 ###### runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget {
######  @override
######  _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  final TextEditingController _uniController = TextEditingController();
######  String _uniname = "";


######  bool? _isChecked,_listTileCheckBox = false;
###### ProductTypeEnum? _productTypeEnum;

######  @override
######  void initState() {
    super.initState();
    _uniController.addListener(_updateText);
######  }

######  void _updateText() {
    setState(() {
      _uniname = _uniController.text;
    });
######  }

######  @override
######  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text(
            "AppBar",
            style: TextStyle(color: Colors.white, fontSize: 30),
          ),
          centerTitle: true,
          backgroundColor: Colors.lightBlue,
        ),
        body: SafeArea(
          child: Container(
            padding: EdgeInsets.all(20.0),
            child: ListView(
              children: [
                TextFormField(
                  controller: _uniController,
                  decoration: InputDecoration(
                    labelText: "University Name",
                    prefixIcon: Icon(Icons.verified_user_outlined),
                    border: OutlineInputBorder(),
                  ),
                ),
                SizedBox(height: 20),
                Row(
                  children: [
                    Checkbox(
                      checkColor: Colors.white,
                      activeColor: Colors.deepPurple,
                      tristate: true,
                      value: _isChecked,
                      onChanged: (val) {
                        setState(() {
                          _isChecked = val;
                        });
                      },
                    ),
                    Text("I agree to the terms"),
                    Expanded(  // Wrap CheckboxListTile inside Expanded
                      child: CheckboxListTile(
                        value: _listTileCheckBox,
                        title: Text("Check",style: TextStyle(fontSize: 15),),
                        onChanged: (val) {
                          setState(() {
                            _listTileCheckBox = val;
                          });
                        },
                        controlAffinity: ListTileControlAffinity.leading,
                      ),
                    ),
                  ],
                ),

                SizedBox(height: 20),
                Text("The university name is: $_uniname"),


                Column(
                  children: [
                    Row(
                      children: [
                        SizedBox(width: 10,),
                        Radio<ProductTypeEnum>(
                          value: ProductTypeEnum.Deliverable,
                          groupValue: _productTypeEnum,
                          onChanged: (val) {
                            setState(() {
                              _productTypeEnum = val;
                            });
                          },
                        ),
                        Text("Deliverable"), // Title for Radio
                      ],
                    ),
                    RadioListTile<ProductTypeEnum>(
                      title: Text(ProductTypeEnum.Downloadable.name),
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(10),
                      ),
                      tileColor: Colors.deepPurple.shade100,// Title f
                      dense: true,// or RadioListTile
                      value: ProductTypeEnum.Downloadable,
                      groupValue: _productTypeEnum,
                      onChanged: (val) {
                        setState(() {
                          _productTypeEnum = val;
                        });
                      },
                    ),
                  ],
                )


              ],
            ),
          ),
        ),
      ),
    );
######  }
###### }

https://github.com/user-attachments/assets/c0f226e4-cdb9-4ba3-b1a3-4da5f3296b86

### ✨ Second Method: ( 2. custom widget stateless => setState in this class )
















## 9.DropDown button:
##### DropDownButton in Flutter:
The DropdownButton widget in Flutter allows users to select an item from a list of options. It is commonly used in forms, settings, or when users need to make a selection from predefined choices.
🔹 Properties of DropdownButton
Property	Description
items	A list of DropdownMenuItem widgets representing the options.
value	The currently selected value.
onChanged	A callback triggered when the user selects an item.
hint	A widget that is displayed when no value is selected.
disabledHint	A widget displayed when onChanged is null (Dropdown is disabled).
style	Defines the text style of the dropdown items.
icon	A custom widget to replace the default dropdown arrow.
iconSize	The size of the dropdown arrow.
isExpanded	If true, the dropdown takes the full width of its parent.
underline	Defines the decoration (like an underline) for the dropdown.
dropdownColor	The background color of the dropdown menu.
borderRadius	Controls the roundness of the dropdown menu.

### Code:
###### import 'package:flutter/material.dart';
###### import 'package:widgets_learn/my_radio_button.dart';

###### enum ProductTypeEnum { Downloadable, Deliverable }

###### void main() {
######  runApp(MyApp());
###### }

###### class MyApp extends StatefulWidget {
######  @override
 ###### _MyAppState createState() => _MyAppState();
###### }

###### class _MyAppState extends State<MyApp> {
######  final TextEditingController _uniController = TextEditingController();
######  String _uniname = "";






###### _MyAppState(){
######  _selectVal=_productSize[0];
###### }
 ###### final _productSize=["Small","Medium","Large","XL"];
 ###### String _selectVal="small";








######  bool? _isChecked, _listTileCheckBox = false;
######  ProductTypeEnum? _productTypeEnum;

######  @override
 ###### void initState() {
    super.initState();
    _uniController.addListener(_updateText);
######  }

######  void _updateText() {
    setState(() {
      _uniname = _uniController.text;
    });
######  }

######  @override
######  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text(
            "AppBar",
            style: TextStyle(color: Colors.white, fontSize: 30),
          ),
          centerTitle: true,
          backgroundColor: Colors.lightBlue,
        ),
        body: SafeArea(
          child: Container(
            padding: EdgeInsets.all(20.0),
            child: ListView(
              children: [
                TextFormField(
                  controller: _uniController,
                  decoration: InputDecoration(
                    labelText: "University Name",
                    prefixIcon: Icon(Icons.verified_user_outlined),
                    border: OutlineInputBorder(),
                  ),
                ),
                SizedBox(height: 20),
                Row(
                  children: [
                    Checkbox(
                      checkColor: Colors.white,
                      activeColor: Colors.deepPurple,
                      tristate: true,
                      value: _isChecked,
                      onChanged: (val) {
                        setState(() {
                          _isChecked = val;
                        });
                      },
                    ),
                    Text("I agree to the terms"),
                    Expanded(
                      // Wrap CheckboxListTile inside Expanded
                      child: CheckboxListTile(
                        value: _listTileCheckBox,
                        title: Text(
                          "Check",
                          style: TextStyle(fontSize: 15),
                        ),
                        onChanged: (val) {
                          setState(() {
                            _listTileCheckBox = val;
                          });
                        },
                        controlAffinity: ListTileControlAffinity.leading,
                      ),
                    ),
                  ],
                ),
                SizedBox(height: 20),
                Text("The university name is: $_uniname"),
                Column(
                  children: [
                    Row(
                      children: [
                        SizedBox(
                          width: 10,
                        ),
                        Radio<ProductTypeEnum>(
                          value: ProductTypeEnum.Deliverable,
                          groupValue: _productTypeEnum,
                          onChanged: (val) {
                            setState(() {
                              _productTypeEnum = val;
                            });
                          },
                        ),
                        Text("Deliverable"), // Title for Radio
                      ],
                    ),
                    RadioListTile<ProductTypeEnum>(
                      title: Text(ProductTypeEnum.Downloadable.name),
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(10),
                      ),
                      tileColor: Colors.deepPurple.shade100, // Title f
                      dense: true, // or RadioListTile
                      value: ProductTypeEnum.Downloadable,
                      groupValue: _productTypeEnum,
                      onChanged: (val) {
                        setState(() {
                          _productTypeEnum = val;
                        });
                      },
                    ),
                  ],
                ),





                SizedBox(height: 50,),


                DropdownButton(
                    value: _selectVal,
                    items: _productSize.map((e) => DropdownMenuItem(child: Text(e),value: e,)

                    ).toList(),
                    onChanged: (val){
                          setState(() {
                            _selectVal=val as String;
                          });
                }),

                SizedBox(height: 30,),


                DropdownButtonFormField(
                    value: _selectVal,
                    items: _productSize.map((e) => DropdownMenuItem(child: Text(e),value: e,)

                    ).toList(),
                    onChanged: (val){
                      setState(() {
                        _selectVal=val as String;
                      });
                    },
                    icon: Icon(Icons.arrow_drop_down_circle,
                    color: Colors.deepPurple.shade700,),
                  decoration: InputDecoration(
                    labelText: "T-shirt Sizes",
                    prefixIcon: Icon(Icons.accessibility_new_outlined,
                    color: Colors.purple,),
                    border: OutlineInputBorder(),
                  ),
                ),

              ],
            ),
          ),
        ),
      ),
    );
######  }
###### }





https://github.com/user-attachments/assets/28b46339-b6d2-4cb7-991a-2a53dfa0d4c8




## Mainly used:
###### final _productSize=["Small","Medium","Large","XL"];
######  String _selectVal="small";


###### DropdownButtonFormField(
                    value: _selectVal,
                    items: _productSize.map((e) => DropdownMenuItem(child: Text(e),value: e,)

                    ).toList(),
                    onChanged: (val){
                      setState(() {
                        _selectVal=val as String;
                      });
                    },
                    icon: Icon(Icons.arrow_drop_down_circle,
                    color: Colors.deepPurple.shade700,),
                  decoration: InputDecoration(
                    labelText: "T-shirt Sizes",
                    prefixIcon: Icon(Icons.accessibility_new_outlined,
                    color: Colors.purple,),
                    border: OutlineInputBorder(),
                  ),
                ),







