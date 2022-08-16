# Note

This was the final project for an iOS Codepath Bootcamp I completed in Spring 2019. The project idea was developed by teammates and I was responsible for building the app.

# Cassiopeia

## Table of Contents

1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
1. [Schema](#Schema)

## Overview

### Description

This was meant to be a marketplace for artists to selling their work auction style in the app.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

-   User can create a login/profile
-   User can login
-   User can view profile
-   User can edit their profile
-   User can upload artwork pictures
-   User can add artwork information
-   User can edit their artwork information
-   User can delete artwork
-   User can search for artwork
-   User can view artwork that is available for purchase
-   User can view the details for an artwork
-   User can express interest in buying artwork
-   User can view list of interested buyers for their artwork
-   User can make their account private
-   User can set notifications for interest in their artwork
-   User can set whether they are a buyer or artist

**Optional Nice-to-have Stories**

-   User can bid on artwork
-   User can view art by category
-   User can upload videos of artwork
-   User can purchase artwork directly from app

### 2. Screen Archetypes

-   **Login Screen**
-   User can create a login/profile
-   User can login
-   On sign up, user can indicate whether he/she is a buyer/artist
-   **Stream**
-   User can view artwork that is available for purchase
-   User can view list of interested buyers for their artwork
-   **Detail**
-   User can view the details for an artwork
-   User can express interest in buying artwork when looking at the details for it
-   **Creation**
-   User can upload artwork pictures
-   User can add description on artwork
-   User can edit their artwork information
-   **Profile**
-   User can view profile
-   User can edit their profile
-   **Settings**
-   User can set notifications for interest in their artwork
-   User can make their account private

### 3. Navigation

**Tab Navigation** (Tab to Screen)

-   Home
-   Search
-   Add artwork
-   Buyer Interest
-   Profile

**Flow Navigation** (Screen to Screen)

-   Login/Sign Up -> home
-   Home -> details of selected artwork
-   Profile -> settings

## Wireframes

### [BONUS] Digital Wireframes & Mockups

<img src="https://i.imgur.com/7WQC9ph.jpg" width=600 alt="wireframe">

<a href="https://www.figma.com/file/BuGoy26XU9wLiNFTC8teFR/Cassiopeia-iPhone-X?node-id=0%3A1">Figma Wireframes and Mockups</a>

### [BONUS] Interactive Prototype

<img src="https://i.imgur.com/PGyJy0A.gif" width=300 alt="wireframe">

<a href="https://www.figma.com/proto/BuGoy26XU9wLiNFTC8teFR/Cassiopeia-iPhone-X?node-id=0%3A1&scaling=scale-down" target="_blank">Figma Interactive Prototype</a>

## Schema

### Models

**User**

| Property   | Type   | Description                                                                  |
| ---------- | ------ | ---------------------------------------------------------------------------- |
| userID     | string | unique id for the user (default field)                                       |
| username   | string | unique display name for the user                                             |
| password   | string | a string of characters users use to login to their account, form of security |
| firstName  | string | the first name of the user                                                   |
| lastName   | string | the last name of the user                                                    |
| email      | string | the email address of the user                                                |
| userType   | string | the type of user this is, a buyer or a student                               |
| school     | string | the school that the user attends                                             |
| occupation | string | the user's current job title                                                 |

**Artwork**

| Property     | Type            | Description                                                                  |
| ------------ | --------------- | ---------------------------------------------------------------------------- |
| artID        | string          | unique id for the artwork (default field)                                    |
| medium       | string          | the medium used to create the art piece                                      |
| description  | string          | a brief description by the artist of the work                                |
| dateCreated  | string          | the date that the artist completed the work                                  |
| dateUpdated  | string          | the date that the work was posted (default field)                            |
| user         | Pointer to user | the artwork's artist/user that uploaded it                                   |
| availability | string          | whether or not the art available for purchase or if it has been sold already |

**Chat**

| Property  | Type               | Description                                   |
| --------- | ------------------ | --------------------------------------------- |
| chatID    | string             | unique id for the chat (default field)        |
| artworkID | Pointer to artwork | the artwork that this chat is for             |
| buyerID   | Pointer to user    | the buyer's id, person who initiates the chat |
| userID    | Pointer to user    | the artist's id                               |

**Message**

| Property   | Type            | Description                                                |
| ---------- | --------------- | ---------------------------------------------------------- |
| messageID  | string          | unique id for the message (default field)                  |
| timeSent   | string          | the timestamp of when the message was sent (default field) |
| chatID     | string          | the unique id for the chat that this message is for        |
| senderID   | Pointer to user | unique id of the current user that is sending the message  |
| receiverID | Pointer to user | unique id of the receiver for the message                  |
