# My Game Dev Journey

**Name:** Aryan  
**GitHub:** aryagamedev-04  
**City:** Farrukhabad, India  
**Dream:** To become a Game Developer and build my own big company making open-world games (like Rockstar & Mojang)

**Day 1 - 5 June 2026**  
- Created GitHub account  
- Created first repository `my-game-dev-journey`  
- Started learning Roll-a-Ball Unity tutorial (theory)

**Status:** My game development journey has officially started! 🔥  

**Next Target:** Arrange a PC/Laptop and start making actual games

**Why GitHub?**  
I will upload all my game projects here as I learn Unity and build towards open-world games.
**Day 2 - 6 June 2026**  
- Godot Engine setup kiya on old laptop (i3 + 4GB RAM)  
- First project created (`MyFirstGame`)  
- Added Node2D, Sprite2D with texture  
- Wrote my first GDScript for movement (arrow keys) and fixed errors  
- Game window running successfully  
- Learning a lot even with slow hardware! 🔥  

**Next Target:** Fix sprite visibility and make a bouncing ball
**✅ Theek hai bhai!**  

Yeh raha **sab kuch achhe se organized** diary notes ke liye. Ise copy karke apni diary mein likh lo.

---

### **📒 My Game Dev Journey - Godot Notes**  
**Project Name:** MyFirstGame  
**Date:** 12 June 2026 (Day 6)

### **Ab Tak Jo Seekha Hai (Summary)**

**1. Basic Godot Concepts**
- **Node2D** → Root node (sab kuch iske andar)
- **Sprite2D** → Image dikhane ke liye (Player aur Ball)
- **RigidBody2D** → Physics wali cheez (ball bounce karti hai)
- **CollisionShape2D** → Takrane ke liye shape (Circle/Rectangle)
- **StaticBody2D** → Walls (hilti nahi)
- **Timer** → Har kuch second mein naya ball spawn karne ke liye
- **Label** → Score aur Win message dikhane ke liye
- **Script (.gd)** → Rules likhne ke liye (GDScript)

**2. Player Setup**
- Arrow keys se movement
- Robot sprite add kiya
- Scale adjust kiya (1.5 - 4)

**3. Ball System**
- RigidBody2D + CollisionShape2D (Circle)
- Bounce + Boundaries (screen ke andar rehne ke liye)
- Multiple balls (har 3 second mein naya ball spawn)
- Collect logic (player touch kare toh gayab)

**4. Score & Win System**
- Score badhta hai ball collect karne pe
- 20 score pe "You Win!" message + game pause

**5. Background**
- ColorRect se background color set kiya

**6. Important Codes**

**Ball Script (`rigid_body_2d.gd`)**  
```gdscript
extends RigidBody2D

func _ready():
    linear_velocity = Vector2(180, 120)

func _physics_process(delta):
    # Boundaries
    if position.x < 50: linear_velocity.x = abs(linear_velocity.x)
    if position.x > 970: linear_velocity.x = -abs(linear_velocity.x)
    if position.y < 50: linear_velocity.y = abs(linear_velocity.y)
    if position.y > 550: linear_velocity.y = -abs(linear_velocity.y)

func _on_rigid_body_2d_body_entered(body):
    if body.is_in_group("player"):
        queue_free()
        get_parent()._on_ball_collected()
```

**Main Script (`main.gd`)**  
```gdscript
extends Node2D

var score = 0
@onready var score_label = $Label
@onready var win_label = $winlabel

func _on_ball_collected():
    score += 1
    score_label.text = "Score: " + str(score)
    if score >= 20:
        win_label.visible = true
        get_tree().paused = true
```

**7. Shortcuts**
- F5 = Play/Test game
- Ctrl + S = Save
- Right Click = Add Child Node

**Feeling:**  
Ab mera pehla proper mini game ban gaya hai! Multiple balls, collect, score aur win condition sab kaam kar raha hai. Bahut maza aa raha hai. Consistency rakhunga toh aur bada game banaunga. 🔥

---

**Kal Ka Target (Day 7):**
- Walls polish
- Better visuals / animation
- Sound effects
- Restart button

**Note:** Roz thoda-thoda practice karo. Galtiyan hona normal hai.

---

Bhai, ise copy-paste kar ke diary mein likh lo. Agar kuch add ya change karna ho toh bata dena.

**Kal subah "Ready hu" bol dena**, tab naya kaam shuru karenge.

**Aaj bahut accha kiya!** Rest kar lo. Good night 💪😊
