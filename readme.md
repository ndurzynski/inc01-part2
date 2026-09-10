# In-Class 01b, Part 2: Critical Thinking Questions

- **Course:** CSC 4360, Flutter & Dart

---

## 1. Widget Tree

> Draw or describe the widget tree of your In-Class 01b app, at least four levels deep. If a future employer asked you to add a fifth tab, which single node in your tree would you need to change first, and why does that node "own" the number of tabs?

**Answer:**

```text
Scaffold
├─ AppBar → TabBar (Tab 1, Tab 2, Tab 3, Tab 4)
├─ TabBarView
│ ├─ Container → Center → Text + ElevatedButton (Tab 1)
│ ├─ Container → Column → Image + TextField (Tab 2)
│ ├─ Container → Center → ElevatedButton (Tab 3)
│ └─ Container → ListView → Card → ListTile (Tab 4)
└─ BottomAppBar → Text

If I were to add a fifth tab, the first node in the tree I would ened to change first is adding to the TabBar array.
This is because that array is what dictates how many tabs are created initially before any tabs get their content.

```

---

## 2. Stateless vs. Stateful

> Pick one widget in your app that is stateless and one that is stateful. Explain, in plain language, what would break (or simply become unnecessary complexity) if you swapped which type each one was.

**Answer:**
```
Text Widget -  Stateless
AppBar - Stateful
```

One widget that is stateless is my Text Widget in Tab 1.If it were turned into a Stateful widget, there would be nothing needed for the Text widget to do, so it would be waiting for the user input for no reason.

One widget that is stateful is my ElevatedButton in Tab 1.If it were turned into a Stateless widget, when you click the button, nothing will happen as the Button is unable to see that the user clicked the button, which therefore would not pop up the AlertDialog.

---

## 3. Controllers & Lifecycle

> Imagine you shipped this app to the App Store without calling `_tabController.dispose()`. Describe, step by step, what would happen in memory over hours of real-world use, and why a code reviewer at a real company would flag this immediately.

**Answer:**


As the app is used more and more, the memory that the widget used is never deallocated, which means that the memory cannot be used for other purposes. This causes a memory leak where if not handled, will lead to decreased performance of the device and can lead to a crash. 

---

## 4. Declarative UI

> Compare the declarative approach used in Flutter (`setState()` → rebuild) to an imperative approach you may have seen elsewhere (e.g., manually changing an HTML element with JavaScript). Which would be easier to maintain in a large team, and why?

**Answer:**

I think that the declarative approach used in Flutter may be easier to maintain as it is easier to find(?) in Flutter versus imperative approaches.

---

## 5. Team Collaboration

> Reflect on setting up your shared GitHub repository with your partner: what part of the workflow (branches, pull requests, merge conflicts, or communication) felt hardest, and what would you do differently on your very first day at a new software job to avoid that friction?

**Answer:**

I think the hardest part is setting up everyone's branches. For future projects, I will dedicate the first day to just making sure everyone's git and branches are working properly on their own devices before assigning anything.
---