<h1>GROUP 5 MIST 4610 Group Project 1</h1>

<h2>TEAM NAME:</h2>
29704 Group 5

<h2>Team Members:</h2>

1. Michael Hearnes [@michaelhearnes](https://github.com/mh101410)

2. Elton Hsieh [@eltonhsieh](https://github.com/ehsieh1)

3. Aidan Kane [@aidankane](https://github.com/aidanpatrickkane)

4. Mandy Larsen [@mandylarsen](https://github.com/awl25)

5. Zhengze Li [@zhengzeli](https://github.com/Hwyqlzz)

6. Nabeel Mohammed [@nabeelmohammed](https://github.com/nabeelmohd56)

<h2>Problem Description:</h2>
Our project creates a relational database for a tennis club based on the prompt entered below into ChatGPT. In this case, ChatGPT acted as the client and set the appropriate entities and attributes for us to model as necessary.

Prompt: Pretend you are the owner/operator of a tennis (or football, soccer - your choice) club needing to build a relational database. You hired some students from the MIST 4610 class at the University of Georgia to create the database for you. They need to know more about your organization to identify which entities, attributes, and relationships are important for you. Start by describing your business as a real client.

Response: I am the owner/operator of a tennis club chain called "Green Valley Tennis Center," located in Athens, Georgia. Our club is a premium tennis facility that caters to tennis enthusiasts of all ages and skill levels. We offer a range of services, from professional coaching and training to court rentals, leagues, tournaments, and a pro shop. Our goal is to provide a top-notch experience for tennis players and create a vibrant and welcoming tennis community in our area.

Key aspects of our business that the MIST 4610 class students should consider when designing the relational database include:

1. **Employees**: Represents the staff working at the Green Valley Tennis Center, including their personal information, contact details, job roles, and work schedules.

2. **TennisClubs**: Represents the tennis club itself, Green Valley Tennis Center, including details about the club's location, facilities, and general information.

3. **Courts**: Represents the tennis courts available at the club, including information about each court, such as court number, and availability.

4. **CourtReservations**: Tracks reservations made by members for specific tennis courts on specific dates and times, including information about bookings and court assignments.

5. **Positions**: Represents the various job positions within the organization, both for employees and club management, including details about job titles, responsibilities, and experience levels.

6. **Leagues**: Represents the tennis leagues organized by the club, including information about league types, divisions, and participants.

7. **ProShops**: Represents the pro shop at the tennis center, which sells tennis equipment and apparel, including details about the shop's inventory, products, and hours of operation.

8. **Merchandise**: Contains information about the merchandise available in the pro shop, including product details, pricing, and stock levels.

9. **Tournies**: Represents tennis tournaments organized by the club, including details about tournament types, schedules, and participants.

10. **Memberships**: Tracks the different membership plans offered by the Green Valley Tennis Center, including different types of memberships, associated fees, and membership descriptions.

11. **OrderDetails**: Stores detailed information about orders made by members in the pro shop, including items purchased, quantities, and prices.

12. **Participation**: Tracks the participation of members and players in various club activities, such as leagues, tournaments, and coaching sessions.

13. **Orders**: Represents orders made by members in the pro shop, including order dates, total amounts, and payment information.

14. **Players**: Maintains profiles for all club members and players, tracking their personal information, contact details, and skill levels.

15. **Lessons**: Tracks coaching and instruction services offered by the club, including details about coaching sessions, schedules, and instructors.

16. **Coaches**: Represents the certified tennis coaches employed by the club, including coach profiles, availability, and coaching schedules.

The students from the MIST 4610 class should consider these aspects when designing the database schema, identifying the entities (tables), their attributes (fields), and the relationships between them. The relational database should facilitate efficient management of our tennis club's operations and help us deliver a seamless experience to our members and guests.

Based on this response from the client, we determined that the entity central to the data model is the tennis clubs. Players can then buy memberships, participate in tournaments and leagues, reserve courts, and book lessons with coaches. Additionally, each club has a pro shop with merchandise, from which players can place orders. All employees of the club are modeled as well, including support staff and tennis coaches. The goal of our database is to model the entities and their respective attributes, the relationships between them, and then to create sample data off of which the tables can be populated. This will allow us to write SQL queries on the database that will provide us with insight into the operations of the club.

<h2>Data Model:</h2>

Explanation of data model:

Our data model is representative of a tennis club's structure, as described above by the hypothetical client. To begin, we have the Tennis Club table itself, which has several relationships stemming from it. The club has a one-to-one relationship with the pro shop; one club has one pro shop. To account for this, the pro shop's ID is placed in the tennis club's attributes as a foreign key. The Tennis Clubs table has one-to-many relationships with Employees (many employees work for one club), Leagues (many leagues correspond to one club), and Courts (a club has many courts). The Pro Shops table has a one-to-many relationship as well with Merchandise (an assortment of merchandise is present at the shop).

The branches off of the Tennis Clubs table have relationships tracing to them as well. For the Employees table, there is a one-to-many relationship with Positions (there are many employees, each with one position). The Courts table has a one-to-many relationship with Court Reservations (one court can be reserved many times).

Aside from the Tennis Clubs entity, another table that is critical to the model is Players. Players can reserve courts, book lessons with coaches, and participate in tournaments. Thus, several relationships can be traced back to the Players entity. The Players table has a one-to-many relationship with Court Reservations (a player can book a court many times). There are also two many-to-many relationships that Players have: Coaches and Tournies. The associative entities between these are Lessons and Participation, respectively. These relationships are present because there are many coaches and many players, who can book many lessons, and there are many players and many tournaments, in which players participate many times. Expanding upon the Tournies table, this entity also has a one-to-many relationship with Leagues (there are many tournaments in one league), which can be further traced back to Tennis Clubs. The final relationship that can be traced back to Players is the one-to-many relationship with the Orders table (one player can make many orders).

The final pieces of the puzzle are the relationships that flow back to the Pro Shops entity. As mentioned above, the Pro Shops table has a one-to-many relationship with Merchandise. From the Merchandise table, Order Details can be traced using a one-to-many relationship (one order can have many items). Furthermore, Order Details has a one-to-many relationship with Orders (there can be more than one row in Order Details corresponding to one order). Finally, Memberships has a one-to-many relationship with Orders (one member can place many orders).




Data model:
![IMG_2808 13](https://github.com/Hwyqlzz/group5/assets/148079593/1d81de7c-b9ac-4bf7-8bcc-b3fcdb0a38b2)

<h2>Data Dictionary:</h2>

<img width="601" alt="employees" src="https://github.com/Hwyqlzz/group5/assets/35616163/79dd32bc-c1dc-4396-b941-1096876cd8e9">

<img width="538" alt="Screenshot 2023-11-02 191948" src="https://github.com/Hwyqlzz/group5/assets/35616163/260b51c8-15dc-40c7-aa01-3b00b086e354">

<img width="599" alt="positions" src="https://github.com/Hwyqlzz/group5/assets/35616163/d8591094-ef9f-419f-9bca-2fb6247eedd1">

<img width="600" alt="coaches" src="https://github.com/Hwyqlzz/group5/assets/35616163/228c513e-d943-42a9-bcd2-4a9c35a4384a">

<img width="603" alt="courtres" src="https://github.com/Hwyqlzz/group5/assets/35616163/1274e44a-df45-4534-8d4a-1cd02c97cd5d">

<img width="593" alt="Screenshot 2023-11-02 191334" src="https://github.com/Hwyqlzz/group5/assets/35616163/394f633b-3729-4034-bdf6-300cd6f82ca4">

<img width="602" alt="leagues" src="https://github.com/Hwyqlzz/group5/assets/35616163/ca26e73e-4819-49c7-aa8a-6873864c6e92">

<img width="602" alt="lessons" src="https://github.com/Hwyqlzz/group5/assets/35616163/0a8fd865-0005-4261-9b77-6c8e2539fc27">

<img width="607" alt="memberships" src="https://github.com/Hwyqlzz/group5/assets/35616163/02112388-b07b-4196-8178-49410b28ccbf">

<img width="515" alt="merchandise" src="https://github.com/Hwyqlzz/group5/assets/35616163/5847b740-2a10-4dc8-bbc3-d31418f0a43e">

<img width="542" alt="orderdetails" src="https://github.com/Hwyqlzz/group5/assets/35616163/5aecfad6-f79f-4d0e-af7d-d4fa2b9287dc">

<img width="543" alt="image" src="https://github.com/Hwyqlzz/group5/assets/35616163/4a851f65-e377-4540-8856-a55caceaf39d">

<img width="543" alt="participation" src="https://github.com/Hwyqlzz/group5/assets/35616163/444b1d8e-def2-402d-8765-a48fb98c7279">

<img width="538" alt="Screenshot 2023-11-02 192231" src="https://github.com/Hwyqlzz/group5/assets/35616163/dfb2ab19-51af-4cdc-8376-1cfdfae2b86e">

<img width="538" alt="proshops" src="https://github.com/Hwyqlzz/group5/assets/35616163/b8310026-e0d4-4400-abd3-30961736b2e5">

<img width="541" alt="tournies" src="https://github.com/Hwyqlzz/group5/assets/35616163/2a01ec74-15e8-49ed-81de-8ea99cb57127">








<h2>Queries:</h2>

<img width="408" alt="Screenshot 2023-11-02 232512" src="https://github.com/Hwyqlzz/group5/assets/35616163/04053896-d375-4ebb-9099-be132bd3591d">

Query 1 lists out the player's ID, player name, and their number of court reservations.
<img width="1092" alt="Screenshot 2023-11-01 at 16 51 05" src="https://github.com/Hwyqlzz/group5/assets/148079593/34efbe54-b542-4311-ba3b-806d3accc9f8">

This will allow the club to recognize how many times a player has made a reservation, allowing for some packages or discounts to be offered to those with more bookings.

Query 2 lists the information for all the players who have not made a court reservation.
<img width="1064" alt="Screenshot 2023-11-01 at 16 51 43" src="https://github.com/Hwyqlzz/group5/assets/148079593/7b91476c-6cc8-4c33-8eb6-29d9d53f4148">

This allows the club to market to and contact specific customers (promotional emails or coupons). This helps to maximize revenue and efficiency as it specifically targets those who are not engaged in the booking rather than wasting time and resources advertising to those who are already engaged in the booking.

Query 3 lists out the player name and number of lessons they have scheduled
![elton hsieh simple query 3 93](https://github.com/Hwyqlzz/group5/assets/148079593/569b3b09-a690-4c01-875d-253ce9c59713)

This allows the club to assess the effectiveness of the lessons and ensure that player's performance is improving as they take more lessons.

Query 4 lists out % of players and coaches who identify as either “non-binary” or “prefer not to say”.
![elton hsieh complex query 4 46](https://github.com/Hwyqlzz/group5/assets/148079593/acada3c7-c069-4ce3-8c45-37307516c69c)

This data can help the club measure progress in diversity and make informed decisions regarding diversity and inclusion initiatives, ensuring that all members, regardless of their gender identity, feel comfortable and valued at the club.

Query 5 lists out the player names who have spent less on merchandise than the average player  
![aidan complex query 5 78](https://github.com/Hwyqlzz/group5/assets/148079593/95e30d27-d07b-4eec-95b7-ddfb1e0d6759)

This allows the club to tailor their marketing towards those who have not been spending as much money at the pro shop. In addition, the club can begin a rewards program to incentivize purchases.

Query 6 lists out players who have never played in a tournament. 
![aidan simple query 6 50](https://github.com/Hwyqlzz/group5/assets/148079593/aa16ac8b-3a09-4c70-9fe9-39b564154be4)

This shows the club who is and is not interested in competitive tennis, which can be used to refine strategies for player engagement based upon what each player prefers, whether that be competition or just learning how to play.

Query 7 lists the coach's name, the number of players that have lessons with the coach, and the number of lessons that the coach has in total. Order by number of lessons descending.


<img width="666" alt="Screenshot 2023-11-02 at 19 41 16" src="https://github.com/Hwyqlzz/group5/assets/148079593/8dbdea9f-77e5-4193-a9f2-1f9fb6817ba8">

Shows the coaches’ workload and who is the most in-demand, which could be used to incentivize coaches for bonuses.

Query 8 lists out the order number, the name of the product, and the name of the player who placed the order for those orders that have the comment “Product arrived damaged.”


<img width="649" alt="Screenshot 2023-11-02 at 19 42 02" src="https://github.com/Hwyqlzz/group5/assets/148079593/c4e876a9-5203-481c-83ea-2d508a58e510">

This shows which customers were unsatisfied with their order and perhaps which products should no longer be carried since they are present in each of the orders. Enables the pro shop to provide the best customer service possible.


Query 9 lists the names of the employees and the start date of employment for those employees who have worked at the club since 2018 or earlier and make less than $50/hour. Sort by seniority of employment.


<img width="703" alt="query9" src="https://github.com/Hwyqlzz/group5/assets/35616163/9d584b99-80ce-48a0-989a-a6c994b73861">

This shows to management who has been working at the club the longest and thus likely knows about the operations of the club to perhaps be promoted into a management position, taking salaries into account to see if employees deserve a raise.

Query 10 lists out the names of players and their tournament records (wins, draws, and losses) and win percentage, including those with no match history. Order by number of wins.

<img width="775" alt="query10" src="https://github.com/Hwyqlzz/group5/assets/35616163/a1a9fea2-5236-4631-8412-9811f59b1b43">

This shows the best-performing players, who could be awarded prize money for winning a league or tournament.


<h2>Database information:</h2>
Name of the database: ns_F2329704Group 5

Additional information: All queries above are stored as procedures in the database and are callable using the format: CALL TP_Q1();

