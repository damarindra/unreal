Unreal has many type of UI, it confusing for a beginner. When we start dealing with UI, we always heard about UMG (Widgets), yes that is! You can create UI using Widgets! But, you might have a question, what is HUD? Slate? Widgets? What the f is that? Why they are so many? This article will help you to understand that.

## HUD

HUD is the most basic *Heads Up Display* class, everything will draw in here! What you see at your screen is HUD!

## Widget (UMG)

**So, isn't HUD is enough?** If you masochist, the answer is yes! lol. Widget will help you to design the UI. To explain it better, let's asking a question, *"What is relation between HUD and Widget?"*

### Relation HUD and Widget

As you know, HUD will draw everything right? So, **Widget is being drawn by HUD**, got it? As soon as you call "Add to Viewport" your Widget is a Part of the HUD your Player Controller is associated with. Thats the relationship between HUD and Widget. The Widget will then be a childcomponent of your HUD.