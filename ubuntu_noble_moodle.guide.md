# Moodle for your teaching

This image runs **Moodle 5.3** (the long-term support release). Course owner and students log in with their ScienceData accounts - with ScienceData group membership as Moodle course enrollment gate. Course material lives in ScienceData folders - one per course - which students see both in Moodle and in ScienceData.

## One Moodle, a group per course

- **One Moodle for all your courses.** Moodle can hold many courses on one site/container; a course can be reused year after year (Moodle's course reset or copy).
- **One folder, one site** To keep your material at the same URL, use the same ScienceData `/storage` folder path - the folder is the site.
- **One ScienceData group per course.** For each course, you create a ScienceData group. You choose how your students join the group - make it an open group so they can join by themselves, or invite them.
- **One folder of course material per group.** When Moodle starts, it makes a folder `Course material/<group name>` in your ScienceData files for each group that may log in, shared read-only with that group. What you put there, students find both in ScienceData and in the Moodle course - it is the same folder, nothing is copied.
- **The group becomes a cohort in Moodle.** Each group you allow to log in appears in Moodle as a cohort with the group name (synchronized every five minutes). As course owner, you enrol the cohort once; students who join the group later are enrolled and those who leave are unenrolled automatically by Moodle.

## Starting your Moodle

1. In **Containers**, choose **New** and the **Moodle** image.
2. Under **Who may log in**, tick the groups of your courses. With no group ticked, only you can log in - fine for trying it out. For each ticked group, a course-material folder is made and shared with it (see above).
3. Choose the folder under `/storage/` that holds the site, e.g. `moodle`. The first time, an empty folder gives a new site; later, the same folder brings back the same site. A non-existing folder will be created.
4. Once the container runs, check the **persistent ports** check-box in the container list, so that its address - and the links your students keep - stays the same.
5. Open the container's link and choose **Log in with ScienceData**. You will be logged in as Moodle administrator.

To add the group of a new course, delete the container and start it again with the same folder and the new group ticked as well: the site, its courses and accounts stay, and the new group gets its course-material folder.

## Setting up a course

1. Create the course in Moodle as usual.
2. In the course: **Participants** → **Enrolment methods** → **Add method** → **Cohort sync**.
3. Choose the cohort with the group's name and the role **Student**, and save.
4. Add the course material: **Add an activity or resource** → **ScienceData folder**, and choose the group's folder (it is preselected when the course enrols the group's cohort).
5. Inform your students that they must log in on ScienceData, so they are known by the system
6. Add each student to the course group on ScienceData - or ask them to join the group
7. Send the URL of your Moodle instance to your students

Members of the group get their Moodle accounts in advance, so they are enrolled - and can be graded or messaged - before they first log in on Moodle. Their e-mail address and names are filled in at that first login.

When a student leaves the group, Moodle unenrols them from the course. To keep their grades and work in the course instead, set **Site administration** → **Plugins** → **Enrolments** → **Cohort sync** → **External unenrol action** to **Disable course enrolment**.

## Course material from ScienceData

Course material has one home: the course's folder in `Course material` in your ScienceData files. The **ScienceData folder** activity shows it in the course - live, read from ScienceData each time - and students download the files from there. There are two ways in, to the same folder:

- **in ScienceData**: the web interface or the sync client - put files in the folder, and they are in the course;
- **in Moodle**: in the ScienceData folder activity you can upload files, make folders and delete - straight in ScienceData.

Students see the same folder in ScienceData too (read-only, through the group share). Moodle's own **File** and **Folder** resources - copies of files kept inside Moodle - are switched off, so that there is only one place to keep material up to date. To insert a single file from the folder elsewhere - an image in a page, say - the file picker offers **Course material (ScienceData)**.

**Videos** play in the ScienceData folder: click one to watch it. Recordings in formats browsers cannot play - from a camera or screen recorder, say - get a version that plays in the browser automatically, usually within the video's own length; the original stays as it is.

Assignments are handed in to Moodle as usual.

## ScienceData links in your course

Paste a ScienceData public link into a page, a label or any course text, and Moodle shows it in a useful form:

- **a notebook** (`.ipynb`): a preview of the notebook, with **Run this notebook** - each student gets their own copy, opened in their own notebook server on ScienceData - and a download link;
- **a video**: a player;
- **a folder**: its name and size, with a link to open it on ScienceData.

Other links stay ordinary links. The link must be a public link (Share → share link) - students do not need to be logged in to ScienceData to see the preview or the video, only to run a notebook.

## For your students

1. Log in to ScienceData once (through their institution) and join the course's group, or accept your invitation.
2. Open your Moodle's address and choose **Log in with ScienceData**.

## People without a ScienceData account

As administrator you can create accounts in Moodle for people who have no ScienceData account (**Site administration** → **Users** → **Add a new user**). They log in with Moodle's own login form.

## Mail

Moodle's mail - notifications, forum posts, password links for the accounts you create - is sent through ScienceData, from its no-reply address. The number of messages is limited per container, scaled by the number of people who may log in.

## Backups and updates

The database is kept on the container's disk and backed up every hour, and when the container is deleted, to `moodle_db-foldername.sql.gz` in the folder `Containers` in your ScienceData home folder. Moodle's own files (e.g. handed-in assignments) are in the mounted folder itself; course material is in your ScienceData files. A new container started with the same folder loads the backup, and a newer image brings its Moodle up to date at start. A course reset or copied for the next year keeps its ScienceData folder activities, showing the same folders until you choose others in their settings.

## Large courses

Before using it for a course with many students, please [contact support](mailto:%support_email%).
