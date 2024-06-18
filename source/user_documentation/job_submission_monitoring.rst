========================================================
LITESOPH Job Submission, Monitoring and File Management
========================================================


Overview
========

LITESOPH Job Submission, Monitoring and File Management is a set of modules capable of handling tasks such as submitting a job to a remote machine, tracking the status of a running job and transferring files from remote to local machines.   

Features and Functionalities
============================

1. The Job Submission module supports queue (qsub, sbatch etc) as well as non-queue (bash) based job submission on remote machine through password and passwordless approach. The passwordless approach is generally used to avoid entering the password repeatedly for every job submission. It can also help bypass captcha based login authentication. See :doc:`/./FAQs/pwless-ssh` 

2. Monitoring modules handle tracking the status of the job as well as terminating the running job on the remote machine. File Management module handles the downloading of all files as well as selective transfer of the files from remote to local machines via different transfer methods (direct transfer along with compression and split transfer).


Usage
=====

.. image:: /_static/images/job_submission.png
   :width: 1000
   :alt: job_submission_monitoring

**1 & 2**: Selection between non-queue (bash) and queue (qsub) job submission. User must select **1** for bash based and **2** for queue based job submission.

**3. Host IP address:** required IP address of the remote machine. 

**4. Port:** required port number of the remote machine.

**5. Username:** required username of the remote machine.

**6 & 7:** User can login to a remote machine by providing a password using **option 6 (with password)**. Furthermore, for a
remote machine which requires captcha authentication for login, passwordless login can be used by selecting **option 7 (without password)** and entering the **pkey-file** See  :doc:`/./FAQs/pwless-ssh` for passwordless-ssh activation. 

**8. Remote Path:** directory on remote machine under which new litesoph project will be created.

**9. Number of Processors:** required number of processors for running simulation on remote machine.

**10. Submit command:** *bash* is default when **option 1 (Command line execution)** is selected. But when **option 2 (Submit through queue)**, user must submit the scheduler submit command. e.g. qsub for PBS machines and sbatch for SLURM machines.

**11. Stat command & 12. Kill command** *(optional)*: If the user desires to kill running job, they must provide the respective scheduler's corresponding commands for checking running process and killing process. e.g. qstat, qdel for PBS machines and qstat and scancel for SLURM machines.

**13. Generate Job Script:** to generate job script after entering correct login parameters

**14. Save Job Script:** to save the generated job script

**15. Run Job:** to run the job using saved job script

**16. View Output:** to view the output log of current simulation in remote machine

**17. Job Status Bar:** shows the status of running job (displays *Job Done* after completion of job)

**18. Job ID:** to enter the job ID to kill simulation

**19. Job Status:** checks the status of running job.

**20. Kill Job:** kill running simulation using Job ID.

**21. Refresh:** get the file information of a current project on a remote machine.

**22. Download All Files:** to download all files from remote machine.

**23. File selection widget:** widget to select relevant files of current project.

**24. Download File:** to download the selected file.

**25. View File:** to download the selected file.

**26. Plot File:** to open the litesoph visualisation toolkit.

**27. Back:** get to the previous page.

**28. Back to main page:** get back to the main page.

**29. Proceed:** to proceed to the next task of the workflow.
