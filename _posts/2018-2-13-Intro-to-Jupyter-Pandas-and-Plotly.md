---
author: Chris A. Williams
layout: post
title: Introduction to Jupyter Notebooks, Python Pandas, and Plotly.
---
On Saturday February 10, 2018 I led a workshop on how to use a Jupyter Notebook to analyze data with Python Pandas and then create some charts with Plotly. The notebooks have been updated since then to clarify some things based on the questions and comments that were provided. 

Note to workshop attendees: The notebooks have been updated, so you can look at the third notebook for instructions on migrating your chart to Javascript. 

First step will be to get registered on Microsoft Live so that you can create notebooks in Azure:

[https://notebooks.azure.com](https://notebooks.azure.com)

Click "Sign In" on the upper right, followed by "No account? Create one!" and then follow instructions. Once you're logged in, click "Click here to create a library!"

Add this Github library (You don't need a GitHub account to add this to Azure, *but* you *should* have a GitHub account, and you will need one later in this tutorial):

[https://github.com/enactdev/plotly-intro-jupyter](https://github.com/enactdev/plotly-intro-jupyter)

Go through notebooks 01, 02, and 03 in order. It will ask you to fill some thing in on your own, if you get stuck you can see the finished notebook in the completed/ directory. If you think this page here looks too short to be a tutorial, you are correct! The real work is all done in these notebooks.

Final step will be to start with this GitHub gist:

[https://gist.github.com/enactdev/2c45cfa8456fde957898c619ec489cf7](https://gist.github.com/enactdev/2c45cfa8456fde957898c619ec489cf7)

Click on "fork" in the upper right. You will need to be logged in first.

After forking the Gist, you will see an "Edit" button in the upper right. If you click it, you can edit the files directly in GitHub. Replace the JSON code in the file 'plotly_vars.json' with what was created in the notebook. You can view your final chart in the Blocks website (no registration required, Blocks are created automatically from your Gists). In the URL, replace '' with '' -- Here is my final example. (Note: It may take a few minutes for the JSON code to be updated.)

[https://bl.ocks.org/enactdev/8c65701cdb3ad655978f856d6ce92059](https://bl.ocks.org/enactdev/8c65701cdb3ad655978f856d6ce92059)

Thank you to everyone who came to the workshop, and anyone who missed it but went through this tutorial! If you have any questions, find me on Slack.
