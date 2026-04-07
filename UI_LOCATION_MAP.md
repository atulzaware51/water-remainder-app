# 🗺️ UI Elements Map - Where Everything Is Located

## 📍 File Overview - lib/main.dart

```
lib/main.dart (264 lines total)
│
├─ LINES 1-5: Imports & Main Function
│
├─ LINES 7-20: ⚙️ APP CONFIGURATION (WaterReminderApp)
│   ├─ Line 13: 📝 App Title ← EDIT HERE
│   └─ Line 15: 🎨 Primary Color ← EDIT HERE
│
├─ LINES 22-30: 📱 Screen Setup
│
├─ LINES 31-50: 🧮 Logic & Variables
│   ├─ Line 31: glassesConsumed = 0
│   ├─ Line 32: targetGlasses = 8
│   └─ Line 33: glassSize = 250 ml
│
└─ LINES 51-264: 🎨 UI BUILD (Everything you see!)
    │
    ├─ LINES 52-57: 📌 AppBar (Top Header)
    │   ├─ Line 73: 📝 AppBar Title Text ← EDIT HERE
    │   ├─ Spacing
    │   └─ Colors
    │
    ├─ LINES 65-135: ⭕ PROGRESS CIRCLE & NUMBER
    │   ├─ Line 88-89: 📏 Circle Size (width/height) ← EDIT HERE
    │   ├─ Line 90: 📏 Circle Thickness (strokeWidth) ← EDIT HERE
    │   ├─ Line 91: 🎨 Circle Background Color
    │   ├─ Line 93-95: 🎨 Circle Progress Color
    │   ├─ Line 109: 📝 Font Size for Number ← EDIT HERE
    │   └─ Line 111: 📋 Number displayed
    │
    ├─ LINES 137-151: 🎯 DAILY GOAL BOX
    │   ├─ Line 147: 🎨 Box Background Color ← EDIT HERE
    │   ├─ Line 150: 📏 Box Rounded Corners ← EDIT HERE
    │   ├─ Line 142: 📝 "Daily Goal" Text ← EDIT HERE
    │   └─ Line 149: 📝 Goal Details Text
    │
    ├─ LINES 153-182: 📊 WATER CONSUMED DISPLAY
    │   ├─ Line 160: 🎨 Box Background Color ← EDIT HERE
    │   ├─ Line 165: 📝 "Consumed" Label ← EDIT HERE
    │   ├─ Line 170: 📝 "Remaining" Label ← EDIT HERE
    │   ├─ Line 173: 📏 Number Font Size ← EDIT HERE
    │   └─ Line 180: 🎨 Number Color
    │
    ├─ LINES 184-213: 🔘 BUTTONS (Add & Reset)
    │   ├─ ADD GLASS BUTTON:
    │   │   ├─ Line 198: 📝 Button Text ← EDIT HERE
    │   │   ├─ Line 200: 📏 Text Font Size ← EDIT HERE
    │   │   ├─ Line 204: 🎨 Button Color ← EDIT HERE
    │   │   └─ Line 196: 🎨 Icon
    │   └─ RESET BUTTON:
    │       ├─ Line 210: 📝 Button Text
    │       └─ Line 209: 🎨 Button Icon
    │
    └─ LINES 215-257: 🎉 SUCCESS MESSAGE (Shows when goal reached)
        ├─ Line 237: 📝 "Great Job!" Text ← EDIT HERE
        ├─ Line 244: 📝 Success Message ← EDIT HERE
        ├─ Line 231: 🎨 Box Background Color ← EDIT HERE
        ├─ Line 233: 🎨 Border Color
        └─ Line 229: 🎨 Icon

```

---

## 🎯 Quick Location Guide

### **Find & Edit Sections**

**To find any section, use:** Ctrl+G (Go to Line)

```
Feature                    Line    Ctrl+G    Change
─────────────────────────────────────────────────────
App Title                  13      13        'Your Title'
Main Color                 15      15        Colors.green
AppBar Text                73      73        'New Text'
Circle Size                88      88        250 (width)
Circle Thickness           90      90        15
Big Numbers                109     109       64
Daily Goal Box Color       147     147       Colors.green[100]
Box Corner Radius          150     150       20
Button Text                198     198       'Drink!'
Button Font Size           200     200       24
Button Color               204     204       Colors.orange
Success Message            237     237       '💪 Awesome!'
```

---

## 🎨 Visual Layout of the App

```
┌─────────────────────────────────────────┐
│  [AppBar - Line 52-57]                  │
│  "Water Reminder" ← Line 73             │
├─────────────────────────────────────────┤
│                                         │
│          [Progress Circle]              │
│          Lines 65-135                   │
│          ⭕ 0 glasses                   │
│          Size: Line 88-89               │
│                                         │
│  [Daily Goal Box - Lines 137-151]       │
│  Daily Goal                             │
│  8 glasses (2000 ml)                    │
│                                         │
│  [Consumed Display - Lines 153-182]     │
│  ┌──────────────┬──────────────┐        │
│  │ Consumed     │  Remaining   │        │
│  │ 0 ml         │  2000 ml     │        │
│  └──────────────┴──────────────┘        │
│                                         │
│  ┌─────────────────────────────┐        │
│  │  💧 Add Glass Button        │        │
│  │  Lines 184-205              │        │
│  └─────────────────────────────┘        │
│                                         │
│  ┌─────────────────────────────┐        │
│  │  Reset Day Button           │        │
│  │  Lines 207-213              │        │
│  └─────────────────────────────┘        │
│                                         │
│  [Success Message - Lines 215-257]      │
│  (Only shows when goal reached)         │
│  🎉 Great Job!                          │
│                                         │
└─────────────────────────────────────────┘
```

---

## 📑 Full Line-by-Line Breakdown

### **Lines 1-20: Setup & Configuration**
```
1    import 'package:flutter/material.dart';
2    
3    void main() {
4      runApp(const WaterReminderApp());
5    }
6    
7    class WaterReminderApp extends StatelessWidget {
8      const WaterReminderApp({Key? key}) : super(key: key);
9    
10   @override
11   Widget build(BuildContext context) {
12     return MaterialApp(
13       title: 'Water Reminder',          ← 🔴 EDITABLE: App title
14       theme: ThemeData(
15         primarySwatch: Colors.blue,    ← 🔴 EDITABLE: Main color
16         useMaterial3: true,
17       ),
18       home: const WaterReminderScreen(),
19     );
20   }
```

### **Lines 52-75: AppBar Section**
```
52   @override
53   Widget build(BuildContext context) {
54     return Scaffold(
55       appBar: AppBar(
56         title: const Text('Water Reminder'),  ← 🔴 EDITABLE: Top text
57         centerTitle: true,
58         elevation: 0,
59       ),
```

### **Lines 86-112: Progress Circle & Number**
```
86                     child: Stack(
87                       alignment: Alignment.center,
88                       children: [
89                         SizedBox(
90                           width: 200,              ← 🔴 EDITABLE: Width
91                           height: 200,            ← 🔴 EDITABLE: Height
92                           child: CircularProgressIndicator(
93                             value: getProgress(),
94                             strokeWidth: 12,      ← 🔴 EDITABLE: Thickness
95                             backgroundColor: Colors.grey[300],
96                             valueColor: AlwaysStoppedAnimation<Color>(
97                               getProgress() == 1.0 ? Colors.green : Colors.blue,
98                             ),
99                           ),
100                        ),
...
106                        Text(
107                          '$glassesConsumed',      ← 🔴 EDITABLE: Number display
108                          style: const TextStyle(
109                            fontSize: 48,         ← 🔴 EDITABLE: Number size
110                            fontWeight: FontWeight.bold,
111                            color: Colors.blue,
112                          ),
```

### **Lines 145-151: Daily Goal Box**
```
145       Container(
146         padding: const EdgeInsets.all(16),
147         decoration: BoxDecoration(
148           color: Colors.blue[100],            ← 🔴 EDITABLE: Box background
149           borderRadius: BorderRadius.circular(12),  ← 🔴 EDITABLE: Corners
150         ),
151         child: Column(
...
154           const Text(
155             'Daily Goal',                       ← 🔴 EDITABLE: Label
156             style: TextStyle(
157               fontSize: 16,
158               fontWeight: FontWeight.w600,
159             ),
...
163           Text(
164             '$targetGlasses glasses (${targetGlasses * glassSize} ml)',
165             style: const TextStyle(
166               fontSize: 14,
167               color: Colors.black54,
168             ),
```

### **Lines 184-213: Buttons**
```
184       const SizedBox(height: 40),
185       // Add Water Button
186       SizedBox(
187         width: double.infinity,
188         child: ElevatedButton.icon(
189           onPressed: glassesConsumed < targetGlasses ? addGlass : null,
190           icon: const Icon(Icons.local_drink, size: 28),
191           label: const Text(
192             'Add Glass of Water',              ← 🔴 EDITABLE: Text
193             style: TextStyle(fontSize: 18),   ← 🔴 EDITABLE: Size
194           ),
195           style: ElevatedButton.styleFrom(
196             padding: const EdgeInsets.symmetric(vertical: 16),
197             backgroundColor: Colors.blue,    ← 🔴 EDITABLE: Color
198             disabledBackgroundColor: Colors.grey[300],
199           ),
200         ),
```

### **Lines 215-257: Success Message**
```
215       if (getProgress() == 1.0)
216         Container(
217           padding: const EdgeInsets.all(16),
218           decoration: BoxDecoration(
219             color: Colors.green[100],        ← 🔴 EDITABLE: Background
220             borderRadius: BorderRadius.circular(12),
221             border: Border.all(color: Colors.green, width: 2),
222           ),
223           child: Row(
224             children: [
225               const Icon(Icons.check_circle, color: Colors.green, size: 32),
226               const SizedBox(width: 16),
227               Expanded(
228                 child: Column(
229                   crossAxisAlignment: CrossAxisAlignment.start,
230                   children: const [
231                     Text(
232                       'Great Job!',                           ← 🔴 EDITABLE: Title
233                       style: TextStyle(
234                         fontSize: 18,
235                         fontWeight: FontWeight.bold,
236                         color: Colors.green,
237                       ),
238                     ),
239                     Text(
240                       'You\'ve reached your daily water goal!',  ← 🔴 EDITABLE: Message
241                       style: TextStyle(
242                         fontSize: 14,
243                         color: Colors.green,
244                       ),
```

---

## 🎯 Top 10 Most Edited Lines

| Rank | What | Line | Common Edits |
|------|------|------|--------------|
| 1 | App Title | 13 | 'Water Reminder' → 'Your Title' |
| 2 | Primary Color | 15 | Colors.blue → Colors.green |
| 3 | AppBar Title | 56 | 'Water Reminder' → 'Your Text' |
| 4 | Circle Size | 90-91 | 200 → 250, 300 |
| 5 | Number Font | 109 | 48 → 64, 72 |
| 6 | Button Text | 192 | 'Add Glass...' → 'Drink!' |
| 7 | Button Color | 197 | Colors.blue → Colors.orange |
| 8 | Button Font | 193 | 18 → 24, 28 |
| 9 | Success Title | 232 | 'Great Job!' → 'Awesome!' |
| 10 | Success Message | 240 | Message text → Your message |

---

## 🚀 Now You Know Where Everything Is!

**Ready to edit? Follow this path:**

```
1. Open main.dart (Ctrl+P)
2. Go to Line X (Ctrl+G)
3. Find the text you want to change
4. Edit it
5. Save (Ctrl+S)
6. Watch it update in browser!

Repeat steps 2-6 as many times as you want!
```

**Happy editing! 🎨**
