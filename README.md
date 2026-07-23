# nest-and-nettles-labor-balancer
Operational workload management tool for Nest & Nettles supervisors. Tracks daily task assignments, activity frequency, and effort intensity across weekend shifts to help supervisors distribute heavy physical tasks fairly, prevent fatigue, and balance team effort.

# Business Introduction
Dr. Fujishiro wrote a paper on analyzing the role fairness plays as a moderator and mediator on traditional work-stressors. The results found "fairness measures moderated the relationship between workload and perceived job stress, with high workload *less likely* to lead to high stress when employees perceived that management was fair."

My own perceived workplace experience has been:
- Associates often bring complaints about unfair workload distribution to their supervisors.
- Associates who do perceived higher effort tasks consistently are more likely to burn out.
- Associates who view other co-worker's jobs as less difficult than their own are less likely to be engaged in their work.

To mitigate this, supervisors and managers have the unique job of managing employee skill level while balancing the department's perceived fairness across avaliable roles. As the number of employees scales, a manager's ability to track who has done what becomes increasingly difficult. 

# Finished Product
<img width="1280" height="757" alt="gif" src="https://github.com/user-attachments/assets/4292be9a-12a4-457d-9201-8f74bac88841" />
Feel free to download and play around with it yourself!

# Goals
To create a tracker that is easy to navigate and use to analyze team labor distribution. I put a heavy emphasis ease of use, ensuring smooth adoption.

# Program
- Excel
- Copilot/Gemini
    -  Used as a coding aid (for macros) and troubleshooting guide

# Data Source
This data is fictional and anonymized but based on real world work assignments in a warehouse setting. Any job roles and names in relation to real world attributes are coincidence and not intentional. 

# Process
<img width="816" height="443" alt="image" src="https://github.com/user-attachments/assets/f515e5e7-507f-480b-ba56-126266f69a07" /> <br>

To begin with, I was shown a rudimentary data entry set up by supervisor. Dates across the top, names on the side. This was an intuitive way to record data. Simply go to the next column and enter more data. However, this layout stunted the ability to create a pivot chart. In order to get counts of the number of times an associate performed a job task, I'd have to unpivot the data. Doing so would limit future data additions. In order to preserve the daily logging of team member roles and create an updating pivot table, I created a PowerQuery connection. 
<br>

<img width="237" height="356" alt="image" src="https://github.com/user-attachments/assets/8708166b-771f-4c0a-9a0f-48c73f3e46d2" /><br>

In the query, I ensured the date column was reading as date, unpivoted the columns, did some string corrections, input a trim command to prevent future data issues, and renamed the columns to more fitting titles. This way, whenever the data was refreshed, the data pulled from the entry table, ran it through these query steps, and then the unpivoted data was perfect to build a pivot table off of. <br>

## Building with Feedback from End Users
That really is the meat of the project right there. The pivot table is a simple count values, and then I added slicers to sort by date range, team member, and job code. I got some feedback from other supervisors and prioritized job code over team member name. This feedback was valuable and helped me ensure that the tool was being built with the end user's goals in mind. One thing I didn't get perfect on all assets was when one supervisor was testing a prototype, they kept clicking the slicer box and moving it. This obviously messed up the layout and made the tool less enjoyable to use. On some assets, I was able to disable resizing and moving which effectively eliminated the issue. On others... the option to do so was just simply greyed out. I wasn't able to find a way around that. Locking the worksheet was an option but it would limit the timeline functionality. The slicers were where I observed most of this aggressive misclicking so I'm glad I was able to remove that barrier.

# Data Entry Page Design 
I used the data entry space as an opportunity for supervisors to see a quick bird's eye view of their team's work distribution. By relying heavily on conditional formatting, I took a visually distinct color pallete (viridis) created a heat map of work load in relation to job. For example, someone who is a taste tester is a lot less fatigued than someone who's on team lift receiving. <br>

<img width="872" height="424" alt="image" src="https://github.com/user-attachments/assets/550867f8-e2e3-45da-b81a-8deaa55633df" /> <br>

This is perfectly encapsulated here. If I was using this tool on 7/19 and Kade Emma came up to me complaining about being tired or exhibiting work fatigue/demotivation. I can easily see why. Team receiving for 4 days consecutively would drain anyone's motivation. Conversely, I'd be able to notice someone like Colton Melinda who has done lighter work like training/taste tester for the past 4 shifts. If Kade and Colton were trained on the same tasks, this would be a perfect opportunity to swap their roles to give Kade a much needed break. This example truly demonstrates the strength of this tool. By embedding this analysis directly into the data entry stage, we can easily catch recent patterns and trends that sheer counts may not tell us on the summary screen. 

# Designing a tool people actually want to use
Given my creation of this tool was entirely voluntary and the supervisor's interest in using it primarily driven by their own ambition to be a better leader, I knew I had to make the tool approachable for all computer levels. Asking a supervisor to navigate to the data tab *after* they've put their mouse on the pivot table, then hit refresh not once, _but twice_ in order to get updated data wasn't realistic and was the fastest way to have a supervisor lose interest. <br>

This is where I finally dived headfirst into the world of macros. I had minimal exposure to macros from my access courses but I understood how they function. Using Gemini, I was able to quickly create 3 different macros with a focus on easing user experience. 1 refreshed the summary table by taking the data entered through the power query and updating the table, 1 simply navigated the user to the summary sheet, and finally—my favorite—a macro that checks the current date and takes the user to that point on the data entry screen. This prevents searching or scrolling, and just sets the end user up for success. End users find buttons inuitive! 

# Reflection
As someone who's worked as a team member on a warehouse floor, I definitely see the value in maintaining team dynamics. An example that comes to mind is being given a heavy box to carry, over and over again. 2 hours of heavy boxes. And while you're carrying those heavy boxes from point A to point B, you see Gary over there having a great time with light boxes. You notice in fact, he's been on light boxes all day. Isn't even breaking a sweat. Maybe the first time this doesn't bother you. Everyone has to do the hard work eventually, but let's say it's been 3 entire work shifts of you doing heavy boxes. Your muscles ache, but Gary looks as right as rain. <br>

In that moment, your desire to continue working as hard plummets. You feel as though you're not valued. You're physically incapable of continuing to perform the task at your current level and you might even feel righteous anger at management who might not even be aware of the workload discrepancy. <br>

I'm proud to have created a tool that can fix that, and display it in a way that's easy to use and interpret. I hope it finds good use in real life, and if you have any other ideas of how to optimize a workload and manage a team and how data can be involved in that process, let me know! 

# Citations
Fujishiro, K. (2005). Fairness at work: its impacts on employee well-being [Doctoral dissertation, Ohio State University]. OhioLINK Electronic Theses and Dissertations Center. http://rave.ohiolink.edu/etdc/view?acc_num=osu1117142039

Bird icon and leaf icon, edited together, both from FlatIcon.

