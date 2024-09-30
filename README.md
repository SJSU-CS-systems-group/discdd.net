# The Problem

Much of the world still doesn't have access to the internet.
Some parts never will due to economic conditions, lack of resources, and lack of local technical expertise.
Other parts lose internet access due to natural and man-made disasters.

# Our solution

Rather than transporting internet data over data channels, we physically transport the data using existing physical transportation methods, such as buses, trains, delivery vehicles, mules, etc.
We call this Disconnected Data Distribution (DDD).
We don't require any new infrastructure or equipment.
We use existing Android phones and USB keyfobs.
Our solution is completely software-based and does not require new equipment or modifications to existing Android phones.
Users simply install our Android apps on their phones.
Our solution complements other solutions, such as long-distance Wifi and satellite internet, to bring internet services to the rest of the world.

# System components

We have three core components

![{5B5029D5-BE08-4E7A-B19C-43FADA845DFF}](https://github.com/user-attachments/assets/0dfc2aed-d8c7-4b7c-912e-507ad9c62056)

* The people in disconnected areas (we will refer to them as villagers) install our Android App on their phones.
* The people who move between disconnected areas and connected areas (called the transport) install our Android Transport App on their phones.
* We run a server on the internet that the transport will contact when it is a connected area to send and receive internet data.

We use end-to-end encryption between villagers and our server based on the Signal protocol.
When a transport is in the village, villagers' phones detect and exchange data using the Wi-Fi Direct.
The villager's phones will exchange end-to-end encrypted bundles with the transports.
We do not trust transports: data is end-to-end encrypted, and our data management does not expect every exchange to reach the destination.
This lack of trust allows anyone to be a transport.
A malicious transport can collect data that it cannot decrypt; any data changes by the transport will be detected; and transports that only collect data but never send to the destination do as much harm as not being present in the first place.

# Initial plan

Our initial plan is to target email.
We are modifying K9, an open-source Android mail client, and writing a simple Java STMP server to integrate with DDD.
Unfortunately, there are many devastated areas of the world (due to man-made and natural disasters) that have populations that need to connect with families, friends, loved ones, educational institutions, businesses, aid, etc.
We plan to try out this way of providing email to get experience with the benefits and challenges of DDD.

# Future plans

There are plenty of common internet applications that would work well with DDD:

* Signal/Whatsapp/Viber
* Youtube
* Telegram
* Github
* Turn based Games
* Facebook/Instagram/Threads
* much more

We also would like to develop more infrastructure:

* Drop boxes
* Multi-hop transports

# Invitation

You can find our code on github.
Please reach out if you are interested in trying it in your area.

# FAQ

**Why Android?**

Android phones have the largest market share in most parts of the world.
There is a rich ecosystem of people who can maintain Android phones all over the world.
Android also exposes Wi-Fi direct functionality to us in a way that isn't available with iOS.
We should be able to get DDD working on villager iPhones in the future.
It also shouldn't be hard to get DDD working on villager Linux/Windows/Mac computers.

**What version of Android do you require?**

We support Android 13 and above.

**Who wrote all this code?**

The Signal crypto library comes from the Signal open-source project.
Over the last couple of years, many students and a professor from SJSU have written the rest.
We were fortunate to receive some initial funding from Meta to fund some of the work, but most of it has been done by volunteers.
