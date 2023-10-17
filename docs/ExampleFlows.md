Example flows

Alice comes to Plan for Mi and is looking to make an account to help plan her daughter's birthday party and is looking for a vendor to help with balloons. First, Alice will create a new account for herself. Once she has created her account she will create a new event for her daughter's birthday party. Now that she has her event set up, she wants to look for a Balloon specialist to help with the party, so she will search the vendors to find someone and add them to the Event.
She starts by calling POST /user/ to create her new account and get her user_id which is 7003
She then calls PUT /user/7003/event/ and passes in the information about her daughters party and gets the event_id back as 3099
She then calls GET /vendor/Ballon_Specialist/ to get a list of the vender_ids (5560,8039,4055 who specialize with balloons, she goes through each vendor using GET /vendor/{5560}/view/ to see each vendors rating and reviews to picks the one she prefers.
Next she will call PUT /event/3099/5560/ to add her chosen vendor to her daughters birthday party
Alice now has a great way to organize her daughters party and she has the best balloon decorations ever seen on planet earth


Jason is a vendor and wants to join Plan for Mi to boost his catering business. He first needs to create a vendor account adding in his business name and contact information. He views his profile and double checks to make sure everything looks good. Jason gets requested to cater a corporate party. He views the party details and accepts. 
He starts by calling POST /vendor/ to create his vendor account and gets his vendor_id which is 1018
He checks his vendor profile GET /vendor/1018/view/ and sees his name and contact, no ratings or reviews since he is a new vendor
He looks over the party details GET /event/xyz123/ and sees the event name Corporate Party, their user id 456, their location Park, the date 10/16/23, and their budget 5000.
When he accepts PUT /event/xyz123/1018/ returns success.
Jason now can cater the corporate business and eagerly awaits their review.


Emily is a party planner and is looking for a flower vendor for an upcoming wedding. She already has an account with Plan For Mi, so she creates a new event. Once she has created her event, she will begin searching for flower vendors. She finds one she likes and books them for her event. After the wedding she leaves a wonderful review on the flower vendors profile. 
Emily creates a new event by calling PUT /user/324/event/ and adds the information about the wedding and gets back the event_id 555
Emily searches for flower vendors GET /vendor/florals/ to get a list of the vender_ids (123,456,789 who specialize with flowers, she goes through each vendor using GET /vendor/{123}/view/ to see each vendors rating and reviews to picks the one she prefers.
She will then add a vendor to her event PUT /event/555/123/ 
She is satisfied with the vendor and leaves a review PUT /vendor/{123}/review/{977}, success!
Emily is happy with her decision and helps the vendor with her awesome review!
