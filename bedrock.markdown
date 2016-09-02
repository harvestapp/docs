# Bedrock Documentation
### Documentation for Harvest MySQL Database

## Container Information
Bedrock runs on the docker container harvestapp/images:bedrock

## Vocabulary
The Bedrock database will have some assumed Vocabulary
  - business: any farm/restaurant
  - any * implies perhaps move column to seperate database
  - any ! implies JSON?

## Assumed Models
As follows are models that need to exist in the Harvest Database

##### events (calendar events)
  - id (int)
  - title (varchar) [title of event]
  - date (datetime) [date event occurs]
  - location (varchar) [place event occurs]
  - details (varchar) [details about event]
  - at_business (boolean) [true if event occurs at creator business]
  - price (decimal) [cost of event, pay through harvest, or NULL]
  - created (date) [date event was created]

##### businesses (business accounts)
  - id (int)
  - community_points_current (int) [community points for current cycle]
  - community_points_total (int) [total historic community points]
  - name (varchar) [name of business]
  - description (varchar) [description of business]
  - daily_items (varchar) [items of the day]
  - searchable_terms (varchar) [search terms]

##### business_event [foreign key]
  - business_id (int)
  - event_id

##### business_addresses
  - id (int)
  - business_id (int)
  - street (varchar)
  - comment (varchar)
  - city (varchar)
  - state (varchar)
  - zip (int)

##### business_images
  - id (int)
  - business_id (int)
  - image (varchar) [url to business image]

##### business_menu_images
  - id (int)
  - business_id (int)
  - image (varchar) [url to menu image]

##### wanted_items
  - id (int)
  - business_id (int)
  - name (varchar) [name of wanted item]
  - quantity (int) [quantity of item wanted]

##### sale_items
  - id (int)
  - business_id (int)
  - name (varchar) [name of for sale item]
  - price (decimal) [price of item]
  - unit (varchar) unit of price

##### users
  - id (int)
  - email (varchar)
  - password (varchar)
  - username (varchar)
  - created (datetime)

##### user_business [foreign key]
  - user_id (int)
  - business_id (int)

##### business_item [foreign key]
  - business_id (int)
  - item_id

##### items
  - id (int)
  - name (varchar) [name of item]
  - quantity (int) [number of item]

##### item_category_item [foreign key]
  - item_category_id (int)
  - item_id (int)

##### item_categories
  - id (int)
  - name (varchar) [name of category]

##### business_item_category [foreign key]
  - business_id (int)
  - item_category_id (int)
