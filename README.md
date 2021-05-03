# How to submit your sessions

## Prepare a folder
You need to prepare a folder that contains all the information to build a session. We highly recommend using underscore whenever space is used. You can view the current session list at [https://github.com/nucleome/sessions/tree/main/4DN](https://github.com/nucleome/sessions/tree/main/4DN). Each submitter has a folder named by his/her GitHub id. All his/her sessions folder is in this folder. A folder with the name of an existing folder in the submitter's folder will overwrite (i.e., update) the existing session. 

## Prepare session data
Inside this folder, you need to prepare four files. 
* The first file is a `meta.json` file representing the meta-information of this session. The details of the `meta.json` file are shown below. 
```
{
    "Title":"4DN portal put DCIC visualization tool side-by-side",
    "Caption":"A custom webpage window is opened on the right. In this example, we open the DCIC visualization tool in this panel. Users can then compare the Nucleome Browser view side-by-side with the HiGlass view on the right. ",
    "Version":"version 1.0",
    "Author": "Yang Zhang (CMU)",
    "Required servers": "/d/portal,http://genome-dev.compbio.cs.cmu.edu:9007" 
}
```
> A JSON file is a collection of keys and values. This example shows that at least five keys are required for a valid `meta.json` file. These keys are case-sensitive. **Title** is a short sentence describing the session. **Caption** is the caption that explains the details of this session. It may include details of data, regions of interest, etc. **Version** is the latest version of this session. **Author** is the contributor and affiliation of this session. Finally, **Required servers** is the data servers that this session depends on. For example, the session shown here is constructed using data from `/d/portal` (the default data server contains public 4DN data from the DCIC web portal). `http://genome-dev.compbio.cs.cmu.edu:9007` is a custom data server. Note that for custom data, Nucleome Browser currently only supports HTTP rather than HTTPS. 
* The second file is a `session.json` file representing the session file you downloaded from the Nucleome Browser. The documentation of sharing and saving session is [here](https://nb-docs.readthedocs.io/en/latest/session.html#). 
* The third file is a `screenshot.jpg` file which shows the screenshot of the session. Both JPG and PNG formats are supported.
* The fourth file is a `thumbnail.jpg` which is the thumbnail of the screenshot. You can use online tools such as [this one](https://www.img2go.com/resize-image) or `convert` command (Linux system) to resize a figure. We recommend keeping the width of the thumbnail as 480px. For the `convert` command, you can use the following script to resize the screenshot to a 480px wide thumbnail.
```
# create a thumbnail with a width of 480px from an original picture screenshot.jpg
convert -thumbnail x480 screenshot.jpg thumbnail.jpg
```

## Structure of a typical user folder
All users who have submitted sessions to this GitHub repo will have a folder named by GitHub id. Sessions folders from a user will be stored in his or her folder. An `index.txt` file indicates how many sessions (session folder name) a user has submitted. The structure of a user will like this.

```
<github id>
----index.txt
----<sesion 2 folder>
--------<meta.json>
--------<screenshot.jpg>
--------<thumbnail.jpg>
--------<session.json>
----<sesion 2 folder>
--------<meta.json>
--------<screenshot.jpg>
--------<thumbnail.jpg>
--------<session.json>
```

## Prepare for a pull-request
Once you have prepared or the required files/folder, you can submit a pull request. After we process and test your session, your sessions will be shown up in [https://gallery.nucleome.org](https://gallery.nucleome.org)
