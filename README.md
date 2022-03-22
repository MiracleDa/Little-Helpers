Original App Design Project - README Template
===

# Little Helpers

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
# This application will serve as a bridge between people needing help, and organizations able to provide help. Users will create an account and sign in, users will submit a help request which will be sent to the Database, and presented to organizations in a help format, and as organizations take request they will be cheeked off. #

### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Independent Intity
- **Mobile:** Yes 
- **Story:** No
- **Market:** No
- **Habit:** No
- **Scope:**N)

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* [fill in your required user stories here]
* ...

**Optional Nice-to-have Stories**

* [fill in your required user stories here]
* ...

### 2. Screen Archetypes

<img src='image_67132673.JPG'/>

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* [fill out your first tab]
* [fill out your second tab]
* [fill out your third tab]

**Flow Navigation** (Screen to Screen)

* [list first screen here]
   * [list screen navigation here]
   * ...
* [list second screen here]
   * [list screen navigation here]
   * ...

## Wireframes
[Add picture of your hand sketched wireframes in this section]
<img src="YOUR_WIREFRAME_IMAGE_URL" width=600>

### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
[This section will be completed in Unit 9]
### Models
[Add table of models]
### Networking
- Home Feed Screen
- 
(Read/GET) Query all posts where user is author

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


(Create/POST) Create a new like on a post

(Delete) Delete existing like

(Create/POST) Create a new comment on a post

(Delete) Delete existing comment

Create Post Screen
  (Create/POST) Create a new post object

Profile Screen
  (Read/GET) Query logged in user object
  (Update/PUT) Update user profile image

- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp]
