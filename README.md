# Little-Helpers


# Help @ Hand

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
1. [Schema](#Schema)

## Overview
### Description


### App Evaluation
- **Category:** Social Networking 
- **Mobile:** This app would be primarily developed for mobile but would perhaps be just as viable on a computer, such as tinder or other similar apps. Functionality wouldn't be limited to mobile devices, however mobile version could potentially have more features.
- **Story:** 
- **Market:** Any individual could choose to use this app, and to keep it a safe environment, people would be organized into age groups.
- **Habit:** This app could be used as often or unoften as the user wanted depending on how deep their social life is, and what exactly they're looking for.
- **Scope:** 

## Product Spec
### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* [x] User creates account
* [x] User logs in to access 
* [x] User view different posts
* [x] User can share a post
* [x] User can make a post
* [x] user can view about us screen
* [ x] user can view feed
* [x] user can make help request


### 2. Screen Archetypes

* Login 
* Register - User signs up or logs into their account
   * Upon Download/Reopening of the application, the user is prompted to log in to gain access to their profile information to be properly.
   * ...
* Feed Screen - Feed that users view in order to see what's going on in the world and who needs help.
   *  
   * Allows user to make post stating what heppened and what all is needed for them or others.

* Settings Screen
   * Lets people change account, and general app settings.

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Home
* Feed Page
* Profile
* Settings


**Flow Navigation** (Screen to Screen)
* Forced Log-in -> Account creation if no log in is available
* Feed View -> Like, Comment, Share
* Profile -> Text field to be modified. 
* Settings -> Toggle settings

## Wireframes
<img src="wireframes.JPG">


### [BONUS] Interactive Prototype
<img src="app.gif">

## Schema 
### Models
#### Post

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | objectId      | String   | unique id for the user post (default field) |
   | author        | Pointer to User| image author |
   | image         | File     | image that user posts |
   | caption       | String   | image caption by author |
   | commentsCount | Number   | number of comments that has been posted to an image |
   | likesCount    | Number   | number of likes for the post |
   | createdAt     | DateTime | date when post is created (default field) |
   | updatedAt     | DateTime | date when post is last updated (default field) |
### Networking
#### List of network requests by screen
   - Home Feed Screen
      - (Read/GET) Query all posts where user is author
         ```swift
         let query = PFQuery(className:"Post")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           // TODO: Do something with posts...
            }
         }
         ```
      - (Create/POST) Create a new like on a post
      - (Delete) Delete existing like
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment
   - Create Post Screen
      - (Create/POST) Create a new post object
   - Profile Screen
      - (Read/GET) Query logged in user object
      - (Update/PUT) Update user profile image


