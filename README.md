# Global-Tech-Conference-Dataset-MSExcel
Global Tech Conference dataset Analysis using MS Excel.
**If you're practicing with same dataset and found yourself confused solving these questions then my friend, I got you. I will try to explain as much in details as possible.**

## Problem Statement
This project contains data related to Global Tech Conference. The data set consists of speakers on different topics from different locations. As a data analyst, your task in hand is to find a suitable approach and solve the problems given in the attached file. Utilizing engaging storytelling techniques and visually appealing charts with interactive slicers, you'll effectively communicate the significance of the insights and their implications for future conference planning and engagement strategies.

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

## Solutions and Approachs
We will find the solutions for all the questions asked in the dataset of 3 sheets, 9 Questions. Then, use those solutions to get insights and finally craft a dashboard.

**Q1. The Customer Success Team is eager to gather feedback from attendees for post-conference assessment. They require personal information for a select group of attendees to initiate feedback requests. You are asked to provide them with the information of the below provided Attendee IDs.**

**A1** ![A1](https://github.com/user-attachments/assets/5a3a62fd-3bad-4d5d-b7fd-8f4a59658840)
- The approach is simple to this question, we've been given Lookup Values(Attendee ID) and Table Array(Attendees sheet) using VLOOKUP you can find Masked Email to Session ID.
- Then taking Session ID as Lookup Value, and Table Array(Sessions sheet) using VLOOKUP you can find Session Topic, Session Date and Speaker Id.
- Now taking Speaker ID as Lookup Value and Table Array(Speakers sheet) and again using VLOOKUP you can find Speaker Name and Field of Expertise.

**Q2. The management seeks insights into the distribution of attendees across different Tech Fields represented at the conference. Understanding this distribution will help in tailoring future events to cater to specific interests and trends within the tech community. You need to calculate the total number of attendees for each Tech Field and then create a labelled bar chart for it, sorted in descending order.**

**A2** ![A2](https://github.com/user-attachments/assets/c58bc64c-0fc2-410e-a51a-cb66a2bedf85)
- First we need to find all unique Tech Fields. By using UNIQUE on Tech Field column in Attendees sheet.
- Then to calculate total number of attendees for each Tech Field, we will use COUNTIF in which taking Tech field column from Attendees sheet as Range and the unique Tech Fields we found earlier as Criteria.
- Copy all the values found and paste under the Tech field and Attendee columns in Q2 Sheet.
- Select the table and sort smallest to largest value. 
- select the table again and insert a Bar Graph from Insert Tab then customize the graph as you prefer.
- **Note: This question can also be solved by using Pivot Table but i wanted to practice with Formulas.**

**Q3. Identifying the most and least popular speakers is crucial for understanding attendee preferences. By examining the number of attendees for each speaker, you can determine which sessions attracted the highest and lowest participation rates, thereby informing decisions for future speaker selection. For the speaker with maximum number of attendees and minimun number of attendes, you need to find the values for the below provided columns. Also, write your approach to get the solution.**

**A3** ![A3](https://github.com/user-attachments/assets/05766edb-45d9-4391-a044-a89a4c789372)
This question is my favourite from all other questions, to solve this question:
- First we need to find "which Attendee joined which speaker" by making a New Column(Speaker ID*) in Attendees sheet, using VLOOKUP in this column taking Session ID(Lookup Value) and Sessions sheet(Table Array).
- Now this is a bit tricky part, we need to find Speaker ID with maximum and minimum number of attendees, Since there're no Lookup Values we will use a combination of INDEX, MATCH, COUNTIF, MAX and MIN functions. 
**(I've alrady explained this formula in the Global-Tech-Conference-Attendees-2023-(solved) in detail make sure to check it out.)**
- Taking Speaker ID(Lookup value) we found earlier and Speakers sheet(Table Array) using VLOOKUP you can find Speaker Name, Country and Field of Expertise.
- To find Total Attendees and Total Sessions, the approach is same with a slight difference. Here we're going to use combination of MAX,COUNTIF and UNIQUE.
**(I've alrady explained this formula in the Solved File in detail make sure to check it out.)**

**Q4. Analyzing attendee demographics by country and tech field provides valuable insights into the global reach of the conference and the popularity of different tech fields in various regions. This information is essential for planning targeted marketing campaigns and expanding the conference's international presence. You need to calculate the total number of attendees from each country, for each Tech Field.**

**A4** ![A4](https://github.com/user-attachments/assets/d9b2ab2c-b373-4138-baeb-7b443da037f4)

Here we're going to use Pivot Tables:
- First, select the Attendee table from Attendees sheet then from Insert Tab create a Pivot Table. In that select Existing Sheet and click on Q4 sheet then select on any cell in Q4 sheet where you want the Pivot Table.
- Now in Pivot Table Fields drag and drop Attendee ID in Values, Tech Field in Rows and Country in Filters and its done.

**Q5. For a deeper understanding of attendee engagement with specific speakers, you're tasked with compiling a list of attendees who attended sessions led by Speaker "SPK032". This information will help in assessing the impact and appeal of individual speakers among conference attendees. Find the list of all the Attendee IDs, who attended the sessions of Speaker "SPK032" and also provide the requested Attendee information.**

**A5** ![A5](https://github.com/user-attachments/assets/21cdc914-806e-477c-a5d8-45d533891534)

- This is the simplest question. As we've already created Speaker ID* column in Attendees sheet in Q3(First step).
- Now we'll apply Filters from Home Tab in he Header cells of each column in Attendees sheet.
- Since we're asked to find info for Speaker ID SPK032, click on the filter of Speaker ID* column, search and select SPK032.
- Copy the filtered values and paste them under the respected columns asked in Q5 sheet.

**Q6. Understanding the occupations of conference attendees and ranking them by popularity provides insights into the diversity of professionals participating in the event. This analysis aids in identifying key target audiences and tailoring content to meet their specific needs and interests. You need to calculate the number of attendees for each occupation. Also give Rank to each occupation by their popularity (eg. Rank 1 to tech field with maximum number of attendees and so on.).**

**A6** ![A6](https://github.com/user-attachments/assets/6e12fa00-ceee-4367-b897-028e339f88bb)

- First we will use UNIQUE(Occupation column from Attendee sheet as Range) to find all unique occupations.
- To calculate the number of attendees for each occupation, we will use COUNTIF in which taking Occupation column from Attendees sheet as Range and the unique Occupations we found earlier as Criteria.
- Now apply RANK on the Total Attendees we found where Total Attendees as Number, Total Attendees column as Ref, 0 for descending orde

**Q7. Identifying attendees who registered on a particular date offers insights into registration trends and the effectiveness of marketing efforts at different stages of event promotion. This information informs future registration strategies and resource allocation for promotional activities. Provide the list of all Attendee IDs and their respective names, who registed on "1-Mar-2022".**

**A7** ![A7](https://github.com/user-attachments/assets/fb3278d4-f45f-497c-8472-2fbc39251771)

- This question is same as Q5 but first we need to make a change on Registration Date column in Attendees sheet.
- Select the column and press ctrl+1 to open Format Cells options, then click on Custom and type dd-mmm-yyyy, this will help us to find Attendee ID list for exactly 1-Mar-2022.
- Filter this column for the date 1-Mar-2022, now copy all the Attendee ID and their Names that falls under this date and paste them in Q7 sheet.

**Q8. Examining the distribution of speakers and sessions across different countries provides insights into the global diversity of conference content and the geographical reach of the event. This analysis informs decisions regarding speaker recruitment and session planning to ensure broad representation and appeal. You need to calculate total number of speakers for each country and total number of sessions they conducted and then create a labelled column chart for it.**

**A8** ![A8](https://github.com/user-attachments/assets/8f0d032e-899d-4842-be99-a368df431ddd)

- First we'll find Unique Country names from Speakers sheet using UNIQUE taking Country column from Speakers sheet as Range.
- Now to calculate total number of speakers for each country we'll use COUNTIF in which taking Country column from Speakers sheet as Range and Unique Country names we found earlier as Criteria.
- Before we move ahead we need to find which sessions took place in which country and since there's no Country column in Sessions sheet, we'll have to make Country* column.
- now under this we'll apply VLOOKUP in which taking Session ID as Lookup Value and Speakers sheet as Table Array we'll get our distribution of country names across Session ID.
- To calculate total number of sessions each speaker conducted in each country we'll again use COUNTIF in which taking Country* column from Sessions sheet as Range and Unique Country names we found earlier as Criteria. We finally got our Table.
- Copy all the values and paste them under their respected columns in Q8 sheet.
- Select the whole table, create a column chart from INSERT Tab and customize as you prefer.

**Q9. Creating a column chart to visualize the distribution of experience levels within each tech field enables stakeholders to easily grasp the demographics of attendees in relation to their professional backgrounds. This visualization aids in identifying trends and opportunities for targeted engagement strategies. Create a Column Chart visualization to show the distribution of experience level in each tech field.**

**A9** ![A9](https://github.com/user-attachments/assets/66f07e05-3877-4185-adb6-3ef6bfa5940d)
Here we're gonna use Pivot Table again:
- Select the Attendees table from Attendees sheet then from Insert Tab create a Pivot table. In that select Existing Sheet and click on Q9 sheet then select on any cell in Q9 sheet where you want the Pivot Table.
- Now in Pivot Table Fields drag and drop Attendee ID in Values, Tech Field in Rows and Experience Level in Columns.
- Copy Row and Column Labels with their values and paste them in a Table format.
- Select the whole table, create a column chart from INSERT Tab and customize as you prefer.

## DASHBOARD

![Dashboard](https://github.com/user-attachments/assets/7489ad90-e6f8-4b41-b16d-4be63362a974)
