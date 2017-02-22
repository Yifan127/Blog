### Week5 Project practice : Weather Report Web-1

#### Requirements description

1. Use **Flask-SQLAlchemy** to store data
2. Add **Update** function, and user can update weather description if the data are wrong
3. Add **Validator** for the weather description text field
4. Add **business logic**: if the query time is within 5 minutes to the last query, return the data in database directly, instead of geting new data from OpenWeatherMap
5. Add **Session** info in server side
6. Use **Chart** to display temperature


#### Break down to small tasks

1. Flask WTForm

   1.1 Use WTForm to create forms, replace the html one in last week task
   
   1.2 Add build-in validators
   
   1.3 Add Custom validators
   
   1.4 jons.loads
   
2. Flask-SQLAlchemy

   2.1 Define table
   
   2.2 Define columns: Integer, String, Boolean, Datetime, PickleType
   
   2.3 Constriction: unique, nullable, default
   
   2.4 Foreign Key & One to One Relationship
   
   2.5 Query, filter, filter_by, distinct
   
   2.6 Insert
 
   2.7 Update
   
3. Package and Blueprint

   3.1 The \_\_init\_\_.py
   
   3.2 Blueprint 

   3.3 Flask configuration

4. Jinja

   4.1 Macro
   
   4.2 Filter
   
5. Flask URL and Redirection

   5.1 Redirection
   
   5.2 Url_for() with parameter in Blueprint
   
6. Flask Session

   6.1 Session and cookie
   
   6.2 Store session in server side
   
7. Google Chart API
   
   7.1 Line Chart
   
   7.2 Add annotation
   
   7.3 Chart options

  
   





