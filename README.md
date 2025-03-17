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
 Positioned(
                  bottom: 0,
                  child:   Container(
                  width: 200,
                  height: 100,
                  color: Colors.grey,
                ),),

![image](https://github.com/user-attachments/assets/9f07d91c-d420-456a-9628-781c8234e829)

        
