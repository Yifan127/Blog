### Week3 Project practice : Weather Report API

#### Requirements description

1. Call API to get current weather 
2. Get weather of a particular date
3. Change unit of measure

#### Break down to small tasks

1. Search for Weather API providers, select two of them, read API docs, compare between them

   1.1 Open Weather Map
   1.2 心知天气 ThinkPage
2. Import requests, get data from above APIs

   2.1 Send get request
   2.2 Get response status code
   2.3 Parse Json response data
   2.4 Add timeout parameter
   2.5 Catch exception
   
3. Make the response data more meaningful 
   3.1 What's UNIX timestamp
   3.2 What does the datetime mean by 'Naive' and 'Aware'?
   3.3 Get local timezone
   3.4 Convert UNIX timestamp to readable format string
   3.5 Convert wind degree to readable compass direction
   
4. Set temperature unit of measure

   4.1 Add validator for the input unit parameter
5. Query weather with specific date

   5.1 Add validator for the input date parameter
   5.2 Convert date string to date object
   5.3 Use timedelta to compare date





