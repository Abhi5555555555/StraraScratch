# StraraScratch
------Q)Find distinct searches for Los Angeles neighborhoods. Output neighborhoods and remove duplicates.(SQL)
Find searches for Los Angeles neighborhoods.

Table: airbnb_search_details
Approach Hints
Expected Output
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int

solution:-
select distinct(neighbourhood) from airbnb_search_details where city= 'LA';

----- Q)Find neighborhoods that have properties with a parking space and no cleaning fees
Find all neighborhoods that have properties with a parking space and don't charge for cleaning fees.

Table: airbnb_search_details
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int

solutions:-
select distinct(neighbourhood) from airbnb_search_details where amenities like '%parking%' and cleaning_fee = 0;

------Q)Find out search details for apartments designed for a sole-person stay
Find the search details made by people who searched for apartments designed for a single-person stay.

Table: airbnb_search_details
Approach Hints
Expected Output
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int

solution:-
select * from airbnb_search_details where property_type = 'Apartment' and accommodates = 1;

----Q)Find searches with no data for the host_response_rate column


Airbnb
Easy
General Practice
ID 9620
6

Find all search details where data is missing from the host_response_rate column.

Table: airbnb_search_details
Approach Hints
Expected Output
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int

Solutions:-
select * from airbnb_search_details where host_response_rate is  null;

----Q)Find the search details for villas and houses with wireless internet access
Find the search details for villas and houses with wireless internet access.

Table: airbnb_search_details
Approach Hints
Expected Output
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int


solution:-
select * from airbnb_search_details where property_type in ('Villa','House') and amenities like '%Wireless Internet%';

-------Q)Find the total number of searches for houses Westlake neighborhood with a TV
Find the total number of searches for houses in Westlake neighborhood with a TV among the amenities.

Table: airbnb_search_details
Approach Hints
Expected Output
airbnb_search_details
Preview
id:
int
price:
float
property_type:
varchar
room_type:
varchar
amenities:
varchar
accommodates:
int
bathrooms:
int
bed_type:
varchar
cancellation_policy:
varchar
cleaning_fee:
bool
city:
varchar
host_identity_verified:
varchar
host_response_rate:
varchar
host_since:
varchar
neighbourhood:
varchar
number_of_reviews:
int
review_scores_rating:
float
zipcode:
int
bedrooms:
int
beds:
int

SOLUTION:-
select count(id) from airbnb_search_details where amenities like'%TV%' and neighbourhood = 'Westlake';

-----Q)Reviews of Hotel Arena
Find the number of rows for each review score earned by 'Hotel Arena'. Output the hotel name (which should be 'Hotel Arena'), review score along with the corresponding number of rows with that score for the specified hotel.

Table: hotel_reviews
Approach Hints
Expected Output
hotel_reviews
Preview
hotel_address:
varchar
additional_number_of_scoring:
int
review_date:
datetime
average_score:
float
hotel_name:
varchar
reviewer_nationality:
varchar
negative_review:
varchar
review_total_negative_word_counts:
int
total_number_of_reviews:
int
positive_review:
varchar
review_total_positive_word_counts:
int
total_number_of_reviews_reviewer_has_given:
int
reviewer_score:
float
tags:
varchar
days_since_review:
varchar
lat:
float
lng:
float

Solution:-
SELECT hotel_name, reviewer_score, count(*) as cnts 
from hotel_reviews
where hotel_name = 'Hotel Arena'
group by 1,2;
