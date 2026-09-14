# Applin

## Product Requirements Document

### what is this

Applin is a bill splitting app for friends having a meal together. Instead of one person paying for everyone and then going through the trouble of calculating what everyone ordered, or worse, having friends calculate GST and service charge differently and ending up with mismatched amounts, everyone in the group can easily pay their own portion. Food, drinks, GST and service charge are all calculated properly and proportionally to what each person ordered.

### why this matters to me

Splitting bills after a meal is always a bit of a pain. Someone has to pay first, then everyone tries to remember what they ordered, then the maths gets confusing with GST and service charge, then that one person has to keep chasing everyone to pay them back. It is a small problem but it happens every single time friends eat out together, and I think that makes it a real problem worth solving. I do not want to be the "bad guy" chasing my friends for money, and on the other end, I do not want to keep asking my friend how much I owe them after the meal either.

### who this is for

Groups of friends eating out together who want to split the bill properly. Applin makes people more willing to pay the bill first, since they can be confident everyone will pay them back the correct amount, without having to work it out themselves.

### the core flow

1. Someone at the meal creates a group in the app. The group is named after the date of the meal, the category (breakfast, brunch, lunch, dinner or supper), and the location or name of the restaurant.
2. A QR code is generated for that group. Everyone at the meal scans the QR code to join.
3. After ordering, each person types into the app what they personally ordered.
4. At the end of the meal, a photo of the receipt can be attached to the group, just for everyone's own reference and record.
5. The app calculates exactly what each person owes, including their share of GST and service charge, proportional to what they ordered.
6. The person who paid the bill marks themselves as the payer. Everyone else sees a request showing exactly how much they owe that person.
7. The app sends reminders to anyone who has not paid yet, so the person who paid first does not have to keep chasing people themselves.
8. Once someone pays (done outside the app, since Applin does not process payments directly), the person who paid first marks them as paid as soon as they see the bank notification. This confirmation also happens outside the app, since bank accounts are not connected to Applin.

### v1 scope

This is what we are actually building first. Everything here should be simple, working and demoable.

- QR code generation and joining a group
- Manual item entry, each person types what they ordered
- Attaching a photo of the receipt to the group, for personal record only, not read or processed by the app
- Splitting logic, food and drinks calculated per person, with GST and service charge split proportionally to what each person ordered
- Marking someone as paid, done manually by the person who paid the bill
- Reminders sent automatically to anyone who has not been marked as paid yet, showing their own total only
- Group members can see what everyone else ordered, but reminders only show each person their own total

### out of scope for v1, future vision

- Actually processing real payments between users
- Reading a receipt photo automatically instead of typing items in by hand
- Integrating Applin directly into restaurant ordering websites, so friends can pay their own portion immediately at the point of ordering, instead of splitting after the fact

### what it should feel like

A website, not a native app, but designed to feel like a proper web app on a phone. Visual direction is inspired by Apple, clean, spacious, confident typography, one clear idea per screen, nothing cluttered. Colour palette is warm and autumnal, red, orange and brown, apple and fall inspired, tying back to the name Applin.

### the maths, for v1

GST is 9% and service charge is 10% in Singapore. Service charge is calculated first, on the person's food and drink total. GST is then calculated on top of that new total, since GST applies after service charge is added to the bill. Each person's share is based on what they personally ordered, not split evenly across the group.

Example: if a person ordered $20 worth of food, service charge is $20 x 0.10 = $2. GST is then calculated on the new total, ($20 + $2) x 0.09 = $1.98. Their total owed is $20 + $2 + $1.98 = $23.98.

### what success looks like for v1

- Joining a group, entering items and seeing the final split all feel simple and clear, not confusing
- Nobody has to manually do maths or remind anyone to pay, the app handles both
- I understand every part of how it was built well enough to explain it clearly to an engineer
