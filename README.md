# Global-Conference-Dataset-MSExcel
Global Conference Analytics using MS Excel.

**If you're practicing with same dataset and found yourself confused solving these Qs then my friend, I got you. I will try to explain as much in details as possible.**

## Problem Statement
This project contains data related to global conference. The data set consists of speakers on different topics from different locations. As a data analyst, your task in hand is to find a suitable approach and solve the problems given in the attached file. Utilizing engaging storytelling techniques and visually appealing charts with interactive slicers, you'll effectively communicate the significance of the insights and their implications for future conference planning and engagement strategies.

## Requirements
To solve questions of this dataset you need to know the working knowledge of the following:

**Softwares**

- MS Excel

**Functions/Formulas**

- VLOOKUP
- INDEX
- MATCH
- UNIQUE
- COUNTIF
- MIN
- MAX

## Solutions and Approach
We will find the solutions for all the questions asked in the dataset of 3 sheets, 9 Questions. Then, using those solution get insights and finally craft a dashboard.

**Q1. The Customer Success Team is eager to gather feedback from attendees for post-conference assessment. They require personal information for a select group of attendees to initiate feedback requests. You are asked to provide them with the information of the below provided Attendee IDs.**

**A1** ![A1](https://github.com/user-attachments/assets/5a3a62fd-3bad-4d5d-b7fd-8f4a59658840)

- The approach is simple to this Q, we've been given Lookup Values(Attendee ID) and Table Array(Attendees) using VLOOKUP you can find Masked Email to Session ID.
- Then taking Session ID as Lookup Value, and Table Array(Sessions) using VLOOKUP you can find Session Topic, Session Date and Speaker Id.
- Now taking Speaker ID as Lookup Value and Table Array(Speakers) and again using VLOOKUP you can find Speaker Name and Field of Expertise.

**Q2. The management seeks insights into the distribution of attendees across different Tech Fields represented at the conference. Understanding this distribution will help in tailoring future events to cater to specific interests and trends within the tech community. You need to calculate the total number of attendees for each Tech Field and then create a labelled bar chart for it, sorted in descending order.**
**A2** ![A2](https://github.com/user-attachments/assets/c58bc64c-0fc2-410e-a51a-cb66a2bedf85)

- First we need to find all unique Tech Fields. By using UNIQUE on Tech Field column in Attendees sheet.
- Then to calculate total number of attendees for each Tech Field, we will use COUNTIF in which taking Tech field column from Attendee as Range and the unique Tech Fields we found earlier as Criteria.
- Copy all the values found and paste under the Tech field and Attendee columns in Q2 Sheet.
- Select the table and sort smallest to largest value. 
- select the table again and insert a Bar Graph from Insert Tab then customize the grapgh as you prefer.

**Q3. Identifying the most and least popular speakers is crucial for understanding attendee preferences. By examining the number of attendees for each speaker, you can determine which sessions attracted the highest and lowest participation rates, thereby informing decisions for future speaker selection. For the speaker with maximum number of attendees and minimun number of attendes, you need to find the values for the below provided columns. Also, write your approach to get the solution.**
**A3** ![A3](https://github.com/user-attachments/assets/05766edb-45d9-4391-a044-a89a4c789372)

This Q is my favourite from all other Qs, to solve this Q:
- First we need to find which Attendee joined which speaker by making a New Column(Speaker ID*) in Attendees sheet, using VLOOKUP in this column taking Session ID(Lookup Value) and Sessions sheet(Table Array).
- Now this is a bit tricky part, we need to find Speaker ID with maximum and minimum number of attendees, Since there're no Lookup Values we will use a combination of INDEX, MATCH, COUNTIF, MAX and MIN functions. 

**I've alrady explained this formula in the Solved File in detail make sure to check it out.**

- Taking Speaker ID(Lookup value) we found earlier and Speakers sheet(Table Array) using VLOOKUP you can find Speaker Name, Country and Field of Expertise.
- To find Total Attendees and Total Sessions, the approach is same with a slight difference. Here we're going to use combination of MAX,COUNTIF and UNIQUE.

**I've alrady explained this formula in the Solved File in detail make sure to check it out.**

**Q4. Analyzing attendee demographics by country and tech field provides valuable insights into the global reach of the conference and the popularity of different tech fields in various regions. This information is essential for planning targeted marketing campaigns and expanding the conference's international presence. You need to calculate the total number of attendees from each country, for each Tech Field.**
**A4**

**Q5. For a deeper understanding of attendee engagement with specific speakers, you're tasked with compiling a list of attendees who attended sessions led by Speaker "SPK032". This information will help in assessing the impact and appeal of individual speakers among conference attendees. Find the list of all the Attendee IDs, who attended the sessions of Speaker "SPK032" and also provide the requested Attendee information.**
**A5**

**Q6. Understanding the occupations of conference attendees and ranking them by popularity provides insights into the diversity of professionals participating in the event. This analysis aids in identifying key target audiences and tailoring content to meet their specific needs and interests. You need to calculate the number of attendees for each occupation. Also give Rank to each occupation by their popularity (eg. Rank 1 to tech field with maximum number of attendees and so on).**
**A6**

**Q7. Identifying attendees who registered on a particular date offers insights into registration trends and the effectiveness of marketing efforts at different stages of event promotion. This information informs future registration strategies and resource allocation for promotional activities. Provide the list of all Attendee IDs and their respective names, who registed on "1-Mar-2022".**
**A7**

**Q8. Examining the distribution of speakers and sessions across different countries provides insights into the global diversity of conference content and the geographical reach of the event. This analysis informs decisions regarding speaker recruitment and session planning to ensure broad representation and appeal. You need to calculate total number of speakers for each country and total number of sessions they conducted and then create a labelled column chart for it.**
**A8**

**Q9. Creating a column chart to visualize the distribution of experience levels within each tech field enables stakeholders to easily grasp the demographics of attendees in relation to their professional backgrounds. This visualization aids in identifying trends and opportunities for targeted engagement strategies. Create a Column Chart visualization to show the distribution of experience level in each tech field.**
**A9**

## DASHBOARD
