# Moodle for your teaching

This image runs your own **Moodle 5.3** (the long-term support release) in a container next to your ScienceData files. You and your students log in with your ScienceData accounts - there are no extra passwords - and the students of a course are the members of a ScienceData group.

## The idea: one Moodle, a group per course

- **One Moodle for all your courses.** Moodle holds many courses in one site, and a course can be reused year after year (Moodle's course reset or copy). Run one container, always with the same folder: the folder is the site.
- **One ScienceData group per course.** Your students join the group - make it an open group so they can join by themselves, or invite them. The same group is where you share course material with them.
- **The group becomes a cohort in Moodle.** Each group that may log in appears in Moodle as a cohort with the same name, kept up to date every five minutes. A course enrols the cohort once; students who join the group later are enrolled by themselves, and Moodle's default is to unenrol those who leave it.

## Starting your Moodle

1. In **Containers**, choose **New** and the **Moodle** image.
2. Under **Who may log in**, tick the groups of your courses. With no group ticked, only you can log in - fine for trying it out.
3. Choose the folder under `/storage/` that holds the site, e.g. `moodle`. The first time, an empty folder gives a new site; later, the same folder brings back the same site.
4. Once the container runs, check **persistent ports** in the container list, so that its address - and the links your students keep - stays the same.
5. Open the container's link and choose **Log in with ScienceData**. You are Moodle's administrator.

To add the group of a new course, delete the container and start it again with the same folder and the new group ticked as well: the site, its courses and accounts stay.

## Setting up a course

1. Create the course in Moodle as usual.
2. In the course: **Participants** → **Enrolment methods** → **Add method** → **Cohort sync**.
3. Choose the cohort with the group's name and the role **Student**, and save.

Members of the group get their Moodle accounts in advance, so they are enrolled - and can be graded or messaged - before they first log in. Their e-mail address and names are filled in at that first login.

When a student leaves the group, Moodle unenrols them from the course. To keep their grades and work in the course instead, set **Site administration** → **Plugins** → **Enrolments** → **Cohort sync** → **External unenrol action** to **Disable course enrolment**.

## For your students

1. Log in to ScienceData once (through their institution) and join the course's group, or accept your invitation.
2. Open your Moodle's address and choose **Log in with ScienceData**.

## People without a ScienceData account

As administrator you can create accounts in Moodle for people who have no ScienceData account (**Site administration** → **Users** → **Add a new user**). They log in with Moodle's own login form.

## Mail

Moodle's mail - notifications, forum posts, password links for the accounts you create - is sent through ScienceData, from its no-reply address. The number of messages is limited per container, scaled by the number of people who may log in.

## Backups and updates

The database is kept on the container's disk and backed up every hour, and when the container is deleted, to `moodle_db-foldername.sql.gz` in the folder `Containers` in your ScienceData home folder. Moodle's files (course material, uploads) are in the mounted folder itself. A new container started with the same folder loads the backup, and a newer image brings its Moodle up to date at start.

## Large courses

Before using it for a course with many students, please [contact support](mailto:%support_email%).
