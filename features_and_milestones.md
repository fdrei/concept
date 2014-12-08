# zentrale - Features and Milestones

## General note for this document

Nothing in this document is fixed. It's an overview of possibilities and ideas. These ideas and possibilities can/should be reworked and are flexible. The shown figures are just an example of how the application **COULD** roughly look like. The figures aren't carved in stone.

## Vision

### Features

- E-mail client
- Chat client
- RSS Feed reader
- Contact management
- Calendar

## MVP - Overview

The first iteration of **zentrale** should provide these features:

- basic **E-mail** client
- **Contact** manager
- basic **Calendar**

The different areas are reachable from the buttons on the left side main toolbar (*Figure 1*). All sub areas provide a dynamic top toolbar with contextual functions (*Figure 2*).

![Figure 1][fig1] *- Figure 1 -*

![Figure 2][fig2] *- Figure 2 -*

----
----

## MVP - E-Mail

The basic **E-mail** client have to provide an overview of all incoming emails. The overview shows the information as single items in a list with alternating backgrounds for a better usability. Every item in the overview shows basic information like senders **name** (if already in contacts), **email address**, receiving **date** and a **message excerpt**. The overview will order all items initially by date (*Figure 3*).

![Figure 3][fig3] *- Figure 3 -*

The item detail view is reachable by clicking on an overview item. The overview moves to the left side but will not completely disappear (see **Google Material Design** definitions).

Detail view (single email view) shows everything the overview shows but the full message not only an excerpt (*Figure 4*). Additional functions are **`Reply`**, **`Forward`** and **`Delete`** (*Figure 5*).

![Figure 4][fig4] *- Figure 4 -*

![Figure 5][fig5] *- Figure 5 -*

### MVP - E-Mail: *Reply*

The reply section is located directly below the original message but in a kind of collapsed state at the bottom (*Figure 6*). It can be expanded and provides a textfield for the reply message, a button to attach files to the email, a button to clear the input and a button to send the message.

![Figure 6][fig6] *- Figure 6 -*

The expanded state fills only 1/3 of the screen by default at the bottom but is expandable and let the original message stay on top (*Figure 7*).

![Figure 7][fig7] *- Figure 7 -*

### MVP - E-Mail: *Forward*

When forwarding an email the content of the original email will be transferred in the below message input area. The input area fills the whole screen (like when writing a new mail). Buttons for **`Attachment`**, **`Cancel`** and **`Send`** will be shown as usual (*Figure 8*).

![Figure 8][fig8] *- Figure 8 -*

### MVP - E-Mail: *New Mail*

The contextual top toolbar provides in the overview the function to write a new email (*Figure 9*).

![Figure 9][fig9] *- Figure 9 -*

The new email view is basically similar to the detail view but shows an empty input area width 100% window height. Additional input fields for **`Recipient`**, **`CC`**, **`BCC`** and **`Subject`** are provided there as well as buttons for **`Attachments`**, **`Cancel`** and **`Send`** (*Figure 10*).

![Figure 10][fig10] *- Figure 10 -*

### MVP - E-Mail: *Toolbar*

In the detail and the new mail view the top toolbar contains a button to go back to the overview. The button is located in the upper left corner to point out the relation to the overview screen that is pushed to the left side (*Figure 11*).

![Figure 11][fig11] *- Figure 11 -*

### MVP - E-Mail: *Supported Protocols*
	
- IMAP

----
----

## MVP - Contacts

Contacts area provides a list of all saved contacts. It is organized in a kind of tile grid view depending on the screen resolution and window size (responsive design).
A single contact item displays a **picture** (if exists, a dummy user icon by default), the **display name** of the contact (if one is given), an **email address** (if exists) and a **phone number** (if exists). One of the last three parts has to be displayed to make sure the user will have at least one possibility to reach the contact (*Figure 12*).

![Figure 12][fig12] *- Figure 12 -*

### MVP - Contacts: *New Contact*

A new contact can be added by the **Toolbar** button **`Add New Contact`** (*Figure 13*).

![Figure 13][fig13] *- Figure 13 -*

The input form for the new contact can be realized by an overlay on top of the contact grid. The input form provides the following contact information:

- Display name
- Email address
- Phone number
- Mobile number
- Chat / Nickname
- Chat Client (if supported once and not needed for MVP)
- User picture

Buttons for **`Save`** or **`Add`** and **`Cancel`** are provided as well (*Figure 14*).

![Figure 14][fig14] *- Figure 14 -*

### MVP - Contacts: *Edit Contact*

Editing a contact should be realized by doing it "inline". So every editable area transforms into an input field. The **Edit Mode** will turned on by a button on every contact item while hovering it (*Figure 15*).

![Figure 15][fig15] *- Figure 15 -*

It's not needed to switch to another view or introducing an overlay for the **Edit Mode**. If needed the contact item will be expanded automatically to make sure every editable information is reachable for the user.

A **`Delete`** function is included in the **Edit Mode**.

### MVP - Contacts: *Supported Protocols*

- carddav

----
----

## MVP - Calendar

The default calendar view provides a twin view. 

### MVP - Calendar: *1. Month View Section*

The first view is in the top 1/3 of the viewport and keeps the current and to both upcoming months in a line. The three calendars are classically month views (*Figure 16*).

![Figure 16][fig16] *- Figure 16 -*

Weekdays are displayed on top. Day numbers will be presented accordingly below the weekdays. Days from the associated month are displayed in a kind of **active** state by a more solid font color. Surrounded day numbers are displayed with a less solid color.

Days with an event / appointment / entry will be highlighted with a colored circle in the background of the corresponding day and today is highlighted by a more solid colored circle (*Figure 17*).

![Figure 17][fig17] *- Figure 17 -*

### MVP - Calendar: *2. Timeline View Section*

The second section provides a horizontal **Timeline**. The **Timeline** is based on the current day hours. As time passes the **Timeline** moves along. The current time will be marked by a vertical line. This vertical line is located 1/5 from the left side. The **Timeline** floats from right to left. Everything that is located right from the **Current Time** line is clearly visible. Everything on the left side is overlaid by a white or light grey layer with at least 60% opacity (*Figure 18*).

![Figure 18][fig18] *- Figure 18 -*

The **Timeline** has a viewport of max. 12h of the current day. These 12 hour view is divided by vertical lines for every 30 minutes. Half hour lines get less opacity than full hour lines so the lines are alternating along the **Timeline**.

Events will be displayed in the **Timeline** as a block that covers the time for this event from start to the end of it. An event can have multiple attributes like ***Importance*** (visualized by rating stars), ***Color*** (as a kind of tag) and ***Size*** (to underline the importance).

A single event in the **Timeline** shows the **Name** of the event, the **Place**, the rating **Stars** and a symbol if a notification is set (bell icon in the upper right corner).

### MVP - Calendar: *Event Details*

A detail view of an event can be entered by clicking on the belonging event. This view and behavior is well known from the **Mac OS X *iCal App*** (*Figure 19*).

![Figure 19][fig19] *- Figure 19 -*

The detail popout contains:

- Event name
- Place
- Date and Time
- Reminder
- Participants

### MVP - Calendar: *Adding Events*

To add a new event the dynamic **Toolbar** contains a button **`Add New Event`**. It opens a popup layer like in the **Contact** section (*Figure 14*). After clicking on **`Save`** or **`Add`** the event will be entered in the **Timeline**.

### MVP - Calendar: *Editing Events*

Event editing is handled by a kind of inline editing in

### MVP - Calendar: *Supported Protocols*

- caldav

## MVP - Settings

### MVP - Settings: *Overview*


# RC1

# RC2

















[fig1]: img/fig-1.jpg
[fig2]: img/fig-2.jpg
[fig3]: img/fig-3.jpg
[fig4]: img/fig-4.jpg
[fig5]: img/fig-5.jpg
[fig6]: img/fig-6.jpg
[fig7]: img/fig-7.jpg
[fig8]: img/fig-8.jpg
[fig9]: img/fig-9.jpg
[fig10]: img/fig-10.jpg
[fig11]: img/fig-11.jpg
[fig12]: img/fig-12.jpg
[fig13]: img/fig-13.jpg
[fig14]: img/fig-14.jpg
[fig15]: img/fig-15.jpg
[fig16]: img/fig-16.jpg
[fig17]: img/fig-17.jpg
[fig18]: img/fig-18.jpg
[fig19]: img/fig-19.jpg
