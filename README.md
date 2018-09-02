# events_manager
A bot that follows up with event attendees to provide them with civic information.

## Procedure
We take the event_attendees.csv file, which contains personal information filled out by the attendees, 
and use the attendees' zipcodes to find their representatives - using the Google Civic API.
In the process we, 
 + request the information we need from the API in #legislators_by_zipcode;
 + adjust zipcodes (to account for areas where the zipcode starts with '0' and the entry treated as an integer) in #clean_zipcode;
 + put the desired messages to the attendees in personalized HTML files using the template in form_letters.erb in #save_thank_you_letters; and
 + validate or invalidate the given phone numbers of the attendees based on the USA's phone format in #clean_number.
