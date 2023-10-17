
1.	Create User - ‘/users/’ (POST)
		Creates a new account for a specific user
	Request:
	{
		“name”		: “string”
	}

	Returns:
	{
		“user_id”	: “int”
	}

2.	Add Event - ‘/users/{user_id}/events/’ (POST)
		Creates an Event tied to a user
	Request:
	{
		“event_name”	: “string”
		“location”	: “string”
		“date”		: “int”
		“budget”	: “int”
		“vendor_id”	: “int (optional)”		
	}

	Returns:
	{
		“event_id”	: “string”
	}

3.	Create Vendor - ‘/vendors/’ (POST)
		Creates a new account for a specific vendor
	Request:
	{
		“name”		: “string”
		“contact”	: “string”
		“title”		: “string”	
	}

	Returns:
	{
		“vendor_id”	: “int”
	}

4.	Find Event - /events/{event_id}/ (GET)
		Returns the info from a specific event
	Returns:
	{
		“event_name”	: “int“
		“vendor_id”	: “int“
		“user_id”	: “int“
		“location”	: “string“
		“date”		: “int“
		“budget”	: “int“
	}

5.	Find Vendors By Title - ‘/vendors/title/{title}’ (GET)
		Returns any vendors with matching titles
	Returns:
	{
		“vendor_ids”	: int array
	}

6.	Review Vendor  - ‘/vendors/{vendor_id}/reviews/{user_id}’ (POST)
		Write a review of a specific vendor and use your user_id to show who wrote it
	Request:
	{
		“event_id”	: “string“
		“review”	: “string“
		“rating”		: “int“
	}

	Returns:
	{
		“success”	: “boolean“
	}








7.	View Vendor - ‘/vendors/{vendor_id}/’ (GET)
		View info of a specific vendor as well as their reviews and average rating
	Returns:
	{
		“name”		: “string“
		“contact”	: “string“
		“title”		: “string“	
		“ave_rating”	: “int“
		“reviews”	: “string array“
}

8.	Add Vendor - ‘/events/{event_id}/vendors/{vendor_id}’ (PUT)
		Add a specific vendor to an event
	Returns:
	{
		“success”	: “boolean“
	}
