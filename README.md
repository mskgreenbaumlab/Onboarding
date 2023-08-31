# Onboarding
Onboarding Instruction for Greenbaum Lab new hire

## MSK Account
**First, claim your MSK Account – you should have received a notification email

Once you claim your account, you will have an MSK ID and MSK email address. Then, move onto the next steps.**

**The information below can also be found on the Onboarding Checklist - https://docs.google.com/spreadsheets/d/10gAa-pEPH9-BLkUXXCePZH2yJglbfRnWq-WGHMjl4Pk/edit?usp=sharing   request access from Mike Li (lih7@mskcc.org)

## MSK Ticket System
MSK HR/IT ticket Management System (create software request, IT related tickets,time management,etc)

https://thespot.mskcc.org/esc?id=esc_dashboard

## ID Badge
Please visit 1275 York Avenue, Bobst Basement, Rm. C-G43 to pick up your MSK badge.



## MSK Office
Link - https://mskoffice.mskcc.org/



## MSK Workday
Link - https://www.myworkday.com/msk/d/home.htmld

Make sure to finish all of the onboarding requirements from MSK Workday.
Also, complete watching onboarding videos and materials through this link - https://msk.sabacloud.com/Saba/Web_spf/NA3P1PRD0015/app/dashboard
MSK Time
Link - https://msktime.mskcc.org/APIHC/TASS/WebPortal/Apihealthcare_LIVE/Default.aspx

Login using MSK ID and password.
Under the "Quick Badge" tab, you can clock in or clock out for the day.
When clocking in for the day, answer NO to the question "Are you badging out for this shift?" and Save.
When clocking out for the day, answer YES to the same question and answer YES to the follow-up question "Did you take your full or part-time meal?"; make sure to Save.
If you forgot to check in or out and need to add a time record, then go to the "Employee" tab and select "Add Clocking" (lower left corner). Input the time (military time) and date. The "User Shift Answer" asks the same question as "Are you badging out for this shift?", so answer accordingly depending on clock-in or clock-out. 


## Communication
### Slack (primary method of communication)
Fill out this form requesting access for Slack, Box, and GSuite - https://thespot.mskcc.org/esc?id=sc_cat_item&sys_id=6613a2cadbdf5c10636a0e85ca9619d8
Reach out to Tiffany Cordero (corderot@mskcc.org) regarding a Slack request. Once she invites you, you can use your MSK email to join the Slack.
Workspace name: greenbaumlab.slack.com
Teams
Some labs use Teams for instant message or file sharing. Some people prefer it because it's integrated with other Microsoft products (eg. file sharing, calendar).

https://teams.microsoft.com/

### Outlook (main method of emailing)
Web version: https://outlook.office.com/mail/

Desktop app: https://slack.com/downloads



## VPN Access
Contact MSK SPOT 646.227.3337 or techspot@mskcc.org to apply for VPN access. <br>
If you already have VPN access and need to request VPN access for someone else. use this link to request for VPN Access - https://thespot.mskcc.org/esc?id=sc_cat_item&sys_id=6db5368fdb21d0508b78a2ad13961958 <br>
Depending on an Employee or Non-Employee Request, fill out the fields with the proper information (questions that ask "describe your request", "summary", "special instructions", etc. can be filled out with a generic overview of the request).<br>
After submitting your ticket, Dr. Greenbaum will have to approve the request before moving forward.<br>
Then, follow the instructions on Global Protect: https://mskcc.ent.box.com/v/gp-install-instructions


## Virtual Computer Desktop (VCD)
The VPN Access request could take some time to process so the VCD is an alternative method of accessing MSK resources from home.
First, download the Citrix Workspace at: https://citrix.com/receiver
Then, go to http://start.mskcc.org/ and log in with you MSK account.
Once you've signed in, click on the "Virtual Computer Desktop" option and open with Citrix.
You should see a new window open up which should give you access to the MSK network.
You'll be able to sign in and sign out through the VCD.


## Github/JIRA/Confluence Access Request
Link - https://solportal.mskcc.org/EnterpriseDevTools

Use this link to request for Github/JIRA/Confluence - https://thespot.mskcc.org/com.glideapp.servicecatalog_cat_item_view.do?v=1&sysparm_id=45f0bf4cdbc07810636a0e85ca9619b9&sysparm_link_parent=3e82ef80db211090892ce02b13961946&sysparm_catalog=e0d08b13c3330100c8b837659bba8fb4&sysparm_catalog_view=catalog_Service_Catalog

## Github
Private repository for Greenbaum lab. It hosts in-house pipelines and common utilities used on HPC. Request access to github from Mike ( lih7@mskcc.org ). This repository is separate from MSKCC github. 

Greenbaum lab github: https://github.com/mskgreenbaumlab


## HPC Account
Use this link to request an HPC Account - [SPOT](https://rts.mskcc.org/service)
For HPC cluster, Dr. Greenbaum's lab uses Juno.
Fill out the PI and admin fields with Dr. Greenbaum's information.
The Cost Center number is on your ID Badge.

Fund Number: reach out to Cristina Radu (raduc@mskcc.org) or Aimee for fund number
Cost Number: 17553 (please confirm with Cynthia berryc@mskcc.org or Cristina raduc@mskcc.org )

(the cost center contains all the funds of the lab.the cc of the Greenbaum Lab is 50515, but it has over 6 funds.)

NOTE: if the "cat" command does not work, you can also try "type id_rsa.pub" to retrieve your public key.How to get your SSH Public Key - https://hpcdocs.mskcc.org/display/CLUS/Secure+Shell+SSH


## HPC Configuration

### Environment Module
To use lab's shared environment modules on juno/lilac, create following file `~/.modulerc`. then paste following lines in it.
```
#%Module
prepend-path MODULEPATH /juno/work/greenbaum/modulefiles
```

### Conda Environment
to use lab's conda environment on Juno

add following lines to `~/.bashrc` to initialize lab's conda 

```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/work/greenbaum/software/Miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/work/greenbaum/software/Miniconda3/etc/profile.d/conda.sh" ]; then
        . "/work/greenbaum/software/Miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/work/greenbaum/software/Miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```

then `source ~/.bashrc`  to initialize lab's conda in current session. no need for future ssh session.


### LD_LIBRARY_PATH
The lab has a shared library for shared applications. You can add this environment variable into `~/.bashrc` file so dynamic link loader can find it for your application.

```
# shared library for the lab
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/work/greenbaum/software/lib/
```

## Grafana
Grafana is a multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources.

[Computing Dashboard](https://hpc-grafana.mskcc.org/d/000000005/cluster-dashboard?orgId=1&refresh=10s&var-cluster=juno&var-GPUs=All&var-gpuhost=All): Monitor computational resource on Juno.

[Lab Work Storage](https://hpc-grafana.mskcc.org/d/000000027/storage-quota?orgId=1&refresh=5m&var-cluster=juno&var-path=work&var-group=greenbaum): Display the quota for Greenbaum lab work storage

[Lab Warm Storage](https://hpc-grafana.mskcc.org/d/000000027/storage-quota?orgId=1&refresh=5m&var-cluster=oscar&var-path=warm&var-group=greenbaum): Display the quota for Greenbaum lab warm storage



## Juno On-Demand Dashboard
OnDemand provides an integrated, single access point for all of our HPC resources (eg. jupyterlab, R Studio, IDE, IGV, Shiny Apps).

Website https://juno-interact01.mskcc.org/pun/sys/dashboard

## Troubleshooting
Please follow MRE (Minimal Reproducible Example) principle to ask help for troubleshooting.<br>
https://stackoverflow.com/help/minimal-reproducible-example

https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example


## Storage
- Juno
Work Storage (430TB):  /juno/work/greenbaum
Archived warm storage (400TB): /oscar/warm/greenbaum
New Warm Storage (70TB): /ifs/rtsia01/greenbaum   (log in from juno-xfer01 by ssh juno-xfer01)
- Lilac
Work Storage (20TB): /data/greenbaum
Warm Storage (400TB): /oscar/warm/greenbaum

### MSK BOX
Link - https://mskcc.ent.box.com/folder/0



### Lab Google Drive
Link - https://drive.google.com/drive/u/1/folders/0ACiz3iSxaZIdUk9PVA



### MSK Sharepoint
Cloud storage for file sharing on Teams

Link: https://mskcc.sharepoint.com/



### SMB File Share
Type in the shared drive path in the browser, this will mount the drive on your local host.

eg. for HPC's share drive: smb://hpc-share01.mskcc.org

