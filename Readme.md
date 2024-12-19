# Prerequisites
- You need a Supabase table called "test_messages" with the following fields: id, created_at, content (text), user_id (uuid)
- You need 2 standard RLS policies for the test_messages table:
    - Enable insert for authenticated users only
    - Enable users to view their own data only
- You need a user signed up with email & password

# Instructions
1. Put your Supabase key and the project URL in /lib/supabase.ts
2. Put the email and password of your user into App.js
3. Install dependencies with `npm install`
4. Start the app on iOS or Android emulator with `npm start`
5. Click Login
6. Send messages, this should work as expected and you should see the new messages in the list.
7. Close the app (not just background but really close it)
8. Reopen the app (e.g. by clicking "a" in the Terminal to open again in the Android emulator)
9. In the app, you should still be logged in but when sending messages, they won't appear in the list. Although they are stored in the database.
8. When signing out and signin in again, the realtime channel works again until the app is closed again.

Note:
After some investigation, it seems to be related to RLS policies. Without any policies on the table, the real-time channels are working fine. As soon as I add two standard policies for INSERT and SELECT, the issue comes up.

Video:
https://youtube.com/shorts/DXeU3AywDJI?feature=share
