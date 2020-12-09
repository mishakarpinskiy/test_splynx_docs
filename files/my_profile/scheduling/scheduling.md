Administrators can connect Splynx to their Google account to sync tasks assigned to them to their Google calendars.

![Scheduling](scheduling.png)

To connect a Google account, click on the **Connect Google account** button and follow the steps to connect the account.

Upon clicking on the Add Google account button, the following window will appear:

![Authorization](authorize.png)

Click on the Google authorize link(1) to sign in. You will be redirected to the Google sign in page. Follow the instructions and allow using of Splynx calendar into a Google account.

You will then receive a code which you will enter into the field provided to connect the Google calendar in Splynx(2).

Simply copy this code and click on *connect Google account*(3) to complete the process:

![Google authorized](linked_google_acccount.png)

To sync Splynx tasks to the connected Google calendar, it is necessary to add a paired calendar. This allows the Splynx calendar of the administrator to sync items into the Google calendar. Simply click on the + add paired calendar button to add a paired calendar:

![add admin's calendar](add_admin_calendar.png)

Once this done let's assign some task to this admin:

![Assigned to admin task](task_assigned_to_admin.png)

Now admin will be able to see this task directly in Google calendar:

![task for admin under google calendar](googlee_assigned_to_admin.png)

Let's imagine a scenario when you add a [scheduling team](../../configuration/scheduling/teams/teams.md) named "Technicians" where a current admin is a member of this team. You assigned a task to a team "Technicians":

![task_assigned_to_team](task_assigned_to_team.png)

and even if admin is a member of a team, task wasn't synced to Google calendar:

![empty Google calendar](empty_google_calendar.png)

The reason of this - you didn't pair a calendar of this team. Let's do this:

![pair team calendar](add_team_calendar.png)

once  this done you can check your Google calendar:

![google_assigned_to_team](google_assigned_to_team.png)

**Conclusion**: if admin wants to sync tasks what assigned directly to him and tasks what assigned to a team(where this admin is a member) it's needed to pair a personal calendar and a team calendar:

![final setup](final_setup.png)

Note that if admin is a member of few teams, each calendar of this team needs to be paired here to sync tasks assigned to these teams. 
