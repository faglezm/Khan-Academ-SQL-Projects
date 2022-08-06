# Khan-Academ-SQL-Projects
Khan Academy SQL Module provides the technical skills and foundations for SQL query composition. Topics like querying, database management and managing data, 

In this course 4 projects were developed with certain grade of tecchnical difficulty. This technical skills set the base of great foundations for future projects.

## Project: App Basic library booking system

In this project, I create a sample query for a Library booking app that stores your data in a SQL database (which is pretty likely!) and write SQL statements that might look like their own SQL.

I have CREATE(ed) tables, INSERT(ed) columns and information as well creating a possible structure of a book store loan system that helps to track where the books are, name, author and the status together with the person that loans it.

```

CREATE TABLE user (id INTEGER PRIMARY KEY,
    name TEXT,
    email TEXT);
    
INSERT INTO user (name, email)
    VALUES ("Chris Mior", "chris.mr08@hotmail.com");
INSERT INTO user (name, email)
    VALUES ("Zara Lauren", "laurenza.79@hotmail.com");
INSERT INTO user (name, email)
    VALUES ("Michael Hilfiger", "milauren9023@icloud.com");
INSERT INTO user (name, email)
    VALUES ("Karl Klein", "Kk.leinco@gmail.com");
    
CREATE TABLE books (id INTEGER PRIMARY KEY,
    name TEXT,
    author TEXT,
    pages INTEGER,
    year INTEGER,
    status INTEGER);
    
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Powerarchy", "Melanie Joy", 197, 2017, "Shelve");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Practical SQL: A beginner guide to storytelling with data", "ANthony DeBarros", 349, 2018, "Loan");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("Business Diagnosis", "Richard Mimick", 250, 2014, "On hold");
INSERT INTO books (name, author, pages, year, status)
    VALUES ("HomoDeus", "Yuval Noah Sharari", 387, 2018, "Loan");
    
SELECT * FROM books;

/* UPDATE */
UPDATE books SET status = "On hold" WHERE name = "Powerarchy";

SELECT * FROM books;

/* DELETE */
DELETE FROM books WHERE id = 3;

SELECT * FROM books;

```

## Project: Design a store database

Create your own store! Your store should sell one type of things, like clothing or bikes, whatever you want your store to specialize in. You should have a table for all the items in your store, and at least 5 columns for the kind of data you think you'd need to store. You should sell at least 15 items, and use select statements to order your items by price and show at least one statistic about the items.

```
CREATE TABLE store (id INTEGER PRIMARY KEY, product TEXT, section TEXT, aisle INTEGER, price INTEGER);

INSERT INTO store VALUES(1, "Stew Beef Boneless", "Frozen Meat", 2, 9.91);
INSERT INTO store VALUES(2, "Green Onion", "Vegetables", 1, 0.99);
INSERT INTO store VALUES(3, "Farmer's Market, Yellow Onions 3lb Bag", "Vegetables", 1, 2.49);
INSERT INTO store VALUES(4, "Zuchini", "Vegetables", 1, 1.23);
INSERT INTO store VALUES(5, "Seaquest, CookedShrimp", "Frozen Fish", 10, 3.00);
INSERT INTO store VALUES(6, "No Name, Elbow Macaroni Pasta", "Pasta and Rice", 4, 1.29);
INSERT INTO store VALUES(7, "xTRA Crisp English Muffins", "Breakfast", 7, 1.50);
INSERT INTO store VALUES(8, "Organic Lemons 2lb", "Fruits", 2, 0.55);
INSERT INTO store VALUES(9, "Roma Tomatoes", "Vegetables", 2, 0.66);
INSERT INTO store VALUES(10, "Ziggy's Cheese & Spinach Ravioli",  "Frozen", 3, 5.00);

SELECT * FROM store ORDER BY price;

SELECT AVG(price) FROM store WHERE section = "Vegetables";
```

## Project: Famous people (Related Tables)

In this project, you’re going to make your own table with some small set of “famous people”, then make more tables about things they do and join those to create nice human readable lists.

For example, here are types of famous people and the questions your data could answer:

Movie stars: What movies are they in? Are they married to each other?
Singers: What songs did they write? Where are they from?
Authors: What books did they write?
Fictional characters: How are they related to other characters? What books do they show up in?

```
/* Create table about the people and what they do here */

CREATE TABLE famous (id INTEGER PRIMARY KEY,
    fullname TEXT,
    job TEXT,
    famousfor TEXT);
    
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Angelina Jolie", "Actrees", "Maleficient");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Brad Pitt", "Actor", "Fury");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Ben Affleck", "Actor", "Argo");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Jennifer Lopez", "Singer", "Jenny from the block");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Nicole Kidman", "Actrees", "Grace of Monaco");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Keith Urban", "Singer", "Wild Hearts");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Cruz Real", "Actrees", "The Judge");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Marco Lotti", "Actor", "Triage");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Claudia Cliff", "Actrees", "The Moon");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Morena Rosa", "Singer", "What you claimed");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Tania Keitman", "Actrees", "Anaconda");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Cameron Stephens", "Actor", "Sir Drunk");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Marie Moonen", "Actrees", "House of cards");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Jhon Carpenter", "Actor", "Armagedon");
INSERT INTO famous (fullname, job, famousfor)
    VALUES ("Selena Gomez", "Singer", "Akiribamba");

CREATE TABLE how_old (id INTEGER PRIMARY KEY,
    famous_id INTEGER,
    age INTEGER,
    hobbie TEXT);

INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (1, 46, "Biking");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (2, 58, "Walking");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (3, 49, "Play Drums");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (4, 52, "Biking");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (11, 54, "Swimming");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (6, 54, "Play Drums");
    INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (7, 52, "Biking");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (9, 54, "Swimming");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (12, 54, "Walking");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (13, 54, "Swimming");
INSERT INTO how_old (famous_id, age, hobbie)
    VALUES (15, 54, "Play Drums");
    
CREATE TABLE couples (id INTEGER PRIMARY KEY,
    person1 INTEGER,
    person2 INTEGER);
    
INSERT INTO couples (person1, person2)
    VALUES (1, 2);
INSERT INTO couples (person1, person2)
    VALUES (3, 4);
INSERT INTO couples (person1, person2)
    VALUES (5, 6);
INSERT INTO couples (person1, person2)
    VALUES (7, 8);
    
SELECT fullname, age, famousfor, hobbie
    FROM famous
    JOIN how_old
    ON famous.id = how_old.id;

/* Now let see who is in a relationship and with whom */

SELECT fullname, age, famousfor, hobbie
    FROM famous
    JOIN how_old
    ON famous.id = how_old.id
WHERE job = "Singer";
    
    
/* Now let see who is in a relationship and with whom */

SELECT a.fullname, b.fullname FROM couples
    JOIN famous a
    ON couples.person1 = a.id
    JOIN famous b
    ON couples.person2 = b.id;
```

## Project: NBA Players-Data dig

We’ve curated a set of interesting data sets for you: NASA astronauts, Superbowl results, Pokemon stats, ,<b>NBA players</b>, Top movies, Top countries by population, Solar system objects by size, Marvel characters, Furniture store sales, Earned KA badges, Winston's donut logs, Card game results, and NFL draft picks.

###    - NBA Players was the DB chosen for the purpose of this excercise. [NBA Player database][]

Pick one of those data sets or create a data set like that, and use advanced SELECT queries to discover things about the data. What sort of questions might one have about that data, like if they were using it for an app or a business idea? Here are some ideas:

What are average, max, and min values in the data?
What about those numbers per category in the data (using HAVING)?
What ways are there to group the data values that don’t exist yet (using CASE)?
What interesting ways are there to filter the data (using AND/OR)?

```
/* Put your data in here and query it! */
CREATE TABLE players(
   Player            TEXT,
   Team              TEXT,
   Conference        TEXT,
   Date              TEXT,
   Position          TEXT,
   Height            TEXT,
   Weight            INTEGER,
   Age               INTEGER,
   Draft_Year        INTEGER,
   Seasons_in_league INTEGER,
   Season            TEXT,
   Season_short      INTEGER,
   Predraft_Team     TEXT,
   Real_value        REAL,
   Height_CM         INTEGER,
   Weight_KG         INTEGER,
   Last_Season       INTEGER
);


INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Norman Powell','Toronto Raptors','East','Mar 9, 2020','SG','6''4',215,26,2015,4,'2019-2020',2020,'UCLA',0.5,193,97,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('LeBron James','Los Angeles Lakers','West','Mar 9, 2020','F','6''8',250,35,2003,16,'2019-2020',2020,'St. Vincent St. Mary High School (Ohio)',0.5,203,113,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Mar 2, 2020','F','6''11',242,25,2013,6,'2019-2020',2020,'Filathlitikos Div II Greece (Greece)',0.5,211,109,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Kristaps Porzingis','Dallas Mavericks','West','Mar 2, 2020','FC','7''3',240,24,2015,4,'2019-2020',2020,'Real Betis Energia Plus (Spain)',0.5,221,108,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Jayson Tatum','Boston Celtics','East','Feb 10, 2020','SF','6''8',208,21,2017,2,'2019-2020',2020,'Duke',0.5,203,94,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Nikola Jokic','Denver Nuggets','West','Feb 10, 2020','C','7''0',250,25,2014,4,'2019-2020',2020,'KK Mega Bemax (Serbia)',0.5,213,113,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Jaylen Brown','Boston Celtics','East','Feb 3, 2020','SF','6''7',220,23,2016,3,'2019-2020',2020,'California',0.5,201,99,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Damian Lillard','Portland Trail Blazers','West','Feb 3, 2020','G','6''3',195,29,2012,7,'2019-2020',2020,'Weber State',0.5,190,88,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Pascal Siakam','Toronto Raptors','East','Jan 27, 2020','F','6''9',230,25,2016,3,'2019-2020',2020,'New Mexico State',0.5,206,104,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Damian Lillard','Portland Trail Blazers','West','Jan 27, 2020','G','6''3',195,29,2012,7,'2019-2020',2020,'Weber State',0.5,190,88,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Ben Simmons','Philadelphia Sixers','East','Jan 20, 2020','PF','6''10',230,23,2016,3,'2019-2020',2020,'LSU',0.5,208,104,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Kawhi Leonard','Los Angeles Clippers','West','Jan 20, 2020','F','6''7',230,28,2011,8,'2019-2020',2020,'San Diego State',0.5,201,104,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Josh Richardson','Philadelphia Sixers','East','Jan 13, 2020','G','6''6',200,26,2015,4,'2019-2020',2020,'Tennessee',0.5,198,90,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('DeMar DeRozan','San Antonio Spurs','West','Jan 13, 2020','GF','6''7',220,30,2009,10,'2019-2020',2020,'USC',0.5,201,99,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Jan 6, 2020','F','6''11',242,25,2013,6,'2019-2020',2020,'Filathlitikos Div II Greece (Greece)',0.5,211,109,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('LeBron James','Los Angeles Lakers','West','Jan 6, 2020','F','6''8',250,35,2003,16,'2019-2020',2020,'St. Vincent St. Mary High School (Ohio)',0.5,203,113,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Jaylen Brown','Boston Celtics','East','Dec 30, 2019','SF','6''7',220,23,2016,3,'2019-2020',2020,'California',0.5,201,99,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Brandon Ingram','New Orleans Pelicans','West','Dec 30, 2019','SF','6''9',190,22,2016,3,'2019-2020',2020,'Duke',0.5,206,86,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Kyle Lowry','Toronto Raptors','East','Dec 23, 2019','PG','6''1',196,33,2006,13,'2019-2020',2020,'Villanova',0.5,185,88,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Dennis Schroder','Oklahoma City Thunder','West','Dec 23, 2019','PG','6''1',172,26,2013,6,'2019-2020',2020,'Basketball Lowen Braunschweig (Germany)',0.5,185,78,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Bam Adebayo','Miami Heat','East','Dec 16, 2019','C','6''10',255,22,2017,2,'2019-2020',2020,'Kentucky',0.5,208,115,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('LeBron James','Los Angeles Lakers','West','Dec 16, 2019','F','6''8',250,35,2003,16,'2019-2020',2020,'St. Vincent St. Mary High School (Ohio)',0.5,203,113,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Jimmy Butler','Miami Heat','East','Dec 9, 2019','GF','6''8',232,30,2011,8,'2019-2020',2020,'Marquette',0.5,203,105,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Anthony Davis','Los Angeles Lakers','West','Dec 9, 2019','PF','6''10',253,26,2012,7,'2019-2020',2020,'Kentucky',0.5,208,114,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Dec 2, 2019','F','6''11',242,25,2013,6,'2019-2020',2020,'Filathlitikos Div II Greece (Greece)',0.5,211,109,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Carmelo Anthony','Portland Trail Blazers','West','Dec 2, 2019','F','6''8',240,35,2003,16,'2019-2020',2020,'Syracuse',0.5,203,108,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Spencer Dinwiddie','Brooklyn Nets','East','Nov 25, 2019','PG','6''6',210,26,2014,5,'2019-2020',2020,'Colorado',0.5,198,95,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Luka Doncic','Dallas Mavericks','West','Nov 25, 2019','SF','6''7',218,21,2018,1,'2019-2020',2020,'Real Madrid (Spain)',0.5,201,98,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Nikola Vucevic','Orlando Magic','East','Nov 18, 2019','PF','7''0',260,29,2011,8,'2019-2020',2020,'USC',0.5,213,118,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('James Harden','Houston Rockets','West','Nov 18, 2019','SG','6''5',220,30,2009,10,'2019-2020',2020,'Arizona State',0.5,196,99,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Pascal Siakam','Toronto Raptors','East','Nov 11, 2019','F','6''9',230,25,2016,3,'2019-2020',2020,'New Mexico State',0.5,206,104,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('James Harden','Houston Rockets','West','Nov 11, 2019','SG','6''5',220,30,2009,10,'2019-2020',2020,'Arizona State',0.5,196,99,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Nov 4, 2019','F','6''11',242,25,2013,6,'2019-2020',2020,'Filathlitikos Div II Greece (Greece)',0.5,211,109,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Anthony Davis','Los Angeles Lakers','West','Nov 4, 2019','PF','6''10',253,26,2012,7,'2019-2020',2020,'Kentucky',0.5,208,114,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Trae Young','Atlanta Hawks','East','Oct 28, 2019','PG','6''2',180,21,2018,1,'2019-2020',2020,'Oklahoma',0.5,188,81,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Karl-Anthony Towns','Minnesota Timberwolves','West','Oct 28, 2019','C','7''0',248,24,2015,4,'2019-2020',2020,'Kentucky',0.5,213,112,1);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Kemba Walker','Charlotte Hornets','East','Apr 8, 2019','G','6''1',184,28,2011,7,'2018-2019',2019,'Connecticut',0.5,185,83,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Russell Westbrook','Oklahoma City Thunder','West','Apr 8, 2019','G','6''3',200,30,2008,10,'2018-2019',2019,'UCLA',0.5,190,90,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Andre Drummond','Detroit Pistons','East','Apr 1, 2019','C','6''11',279,25,2012,6,'2018-2019',2019,'Connecticut',0.5,211,126,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Damian Lillard','Portland Trail Blazers','West','Apr 1, 2019','G','6''3',195,28,2012,6,'2018-2019',2019,'Weber State',0.5,190,88,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Trae Young','Atlanta Hawks','East','Mar 25, 2019','PG','6''2',180,20,2018,0,'2018-2019',2019,'Oklahoma',0.5,188,81,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('James Harden','Houston Rockets','West','Mar 25, 2019','SG','6''5',220,29,2009,9,'2018-2019',2019,'Arizona State',0.5,196,99,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Bradley Beal','Washington Wizards','East','Mar 18, 2019','SG','6''3',207,25,2012,6,'2018-2019',2019,'Florida',0.5,190,93,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Rudy Gobert','Utah Jazz','West','Mar 18, 2019','C','7''1',245,26,2013,5,'2018-2019',2019,'Cholet Basket (France)',0.5,216,111,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Andre Drummond','Detroit Pistons','East','Mar 11, 2019','C','6''11',279,25,2012,6,'2018-2019',2019,'Connecticut',0.5,211,126,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Mike Conley','Memphis Grizzlies','West','Mar 11, 2019','PG','6''1',175,31,2007,11,'2018-2019',2019,'Ohio State',0.5,185,79,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Ben Simmons','Philadelphia Sixers','East','Mar 4, 2019','PF','6''10',230,22,2016,2,'2018-2019',2019,'LSU',0.5,208,104,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Donovan Mitchell','Utah Jazz','West','Mar 4, 2019','SG','6''3',215,22,2017,1,'2018-2019',2019,'Louisville',0.5,190,97,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Bojan Bogdanovic','Indiana Pacers','East','Feb 11, 2019','F','6''8',216,29,2011,4,'2018-2019',2019,'KK Cibona (Croatia)',0.5,203,98,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Paul George','Oklahoma City Thunder','West','Feb 11, 2019','GF','6''9',220,28,2010,8,'2018-2019',2019,'Fresno State',0.5,206,99,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Feb 4, 2019','F','6''11',242,24,2013,5,'2018-2019',2019,'Filathlitikos Div II Greece (Greece)',0.5,211,109,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Nikola Jokic','Denver Nuggets','West','Feb 4, 2019','C','7''0',250,24,2014,3,'2018-2019',2019,'KK Mega Bemax (Serbia)',0.5,213,113,0);
INSERT INTO players(Player,Team,Conference,Date,Position,Height,Weight,Age,Draft_Year,Seasons_in_league,Season,Season_short,Predraft_Team,Real_value,Height_CM,Weight_KG,Last_Season) VALUES ('Giannis Antetokounmpo','Milwaukee Bucks','East','Jan 28, 2019','F','6''11',242,24,2013,5,'2018-2019',2019,'Filathlitikos Div II Greece (Greece)',0.5,211,109,0);


SELECT * FROM players LIMIT 3;

/* Let's do an initail count of players per division of my initial data */

SELECT COUNT(Team), Conference FROM players GROUP BY Conference;

/* Let's check the team's avg weight, avg height and avg age in the SG Position*/

SELECT Team, ROUND(AVG(Weight)) AS weight_avg, ROUND(AVG(Height_CM)) AS height_avg, ROUND(AVG(Age)) AS Age FROM Players WHERE Position = "SG" GROUP BY Team ORDER BY Age;

/*Let's find out who's the tallest player with the lowest weight*/

SELECT Player, Weight, Height_CM, Position FROM players GROUP BY Player HAVING MIN(Weight) AND MAX(Height_CM) ORDER BY Weight LIMIT 3;

/* CASE STATEMENT: Let see how many players in the PG position are below average */
SELECT COUNT(*),
    CASE
        WHEN Height_CM > 208 THEN "Above max"
        WHEN Height_CM > 193 THEN  "On avg"
        WHEN Height_CM > 184 THEN "Below Avg"
        ELSE "Minimums"
    END AS "Height/Position"
FROM players WHERE Position = "PG" GROUP BY "Height/Position";

/*HAVING: Players having more than 10 season in league*/
SELECT Player, Seasons_in_league FROM players GROUP BY Player HAVING Seasons_in_league > 10;

/*AND: Players from East conference in PG Position*/
SELECT Player FROM players WHERE Conference = "East" AND Position = "PG" OR Position = "F" GROUP BY Player;

/*OR: Players from East conference or F Position*/
SELECT Player FROM players WHERE Conference = "East" OR Position = "F" GROUP BY Player LIMIT 5;

```




