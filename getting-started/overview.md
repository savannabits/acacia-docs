# Overview

---
- [Introduction](#introduction)
- [Case Scenario](#case-scenario)

<a name='introduction'></a>
## Introduction
Acacia is a package crafted to help you quickly scaffold a backend for your system. The whole point is to allow you concentrate on the main user-facing logic of your application, while we take care of the nitty gritties of your low-level setup data.

<a name='case-scenario'></a>
## Case Scenario
__The App__: You are writing in the process of creating a music streaming app that looks like spotify. The main challenge in your dev process is to figure out how to securely stream a selected song and still continue streaming even when a user switches tabs.

__The Challenge__: However, in order for you to have the application up and running, you need a backend where the admin can list, view, create, edit and delete the following data among others:
- Album Types
- Song Types
- User Types
- Roles
- Permissions
- Artists
- Record Labels
- Albums
- Songs
- Playlist Types
- Playlists
- etc

How much development effort would it steal from you to create all these CRUDs, fully functional (If you are lazy like me you would probably only seed the data types but leave out the interface for managing them :D). If you are hardworking, this may take you days, weeks or even months depending on your coding speed. Imagine adding a month to your timeline to deliver the app above. What if I told you it doesn't have to be a month but rather minute? Yes, that's right. That is where **Acacia** shines.

__The Solution__: After the initial scaffold, 
1. simply install **Acacia** with a few commands,
2. write your migrations (We leave database design to you, it's better that way)
3. Run a single command to generate all the modules above

Assuming it would take you 20 minutes to write migrations for all the modules listed above (Most of the tables have identical fields really) and another 10 seconds to run the generation command, you are home and dry in 21 minutes. Days saved!

**Already convinced? Let's proceed to install Acacia**

<p class="flex justify-end">
<larecipe-button tag="a" href="./installation" type="primary" >Installation <i class="fas fa-arrow-right"></i> </larecipe-button>
</p>
