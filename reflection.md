# Reflection - Milestone 3  
December 07, 2019  

## __Team Critique__  

---

Overall, we are generally happy with the progress of the dashboard 2 weeks into development. There are certainly elements that need improving upon, functionally and aesthetically, but we were able to create a functional app that aids in answering the research questions. The sentiment is that the plots are simple and intuitive to navigate and read, and the interactivity does not overwhelm or confound the user; the use of tabs to separate the plots helps in distinguishing the research questions.

There are, however, several limitations that need to be addressed in future iterations. Aesthetically, the plots should be able to resize automatically to fill the page and padding should be added to provide separation from the sides of the screen; a navigation side bar that contains the user selector options would help in addressing some of the confusion around the selectors and de-clutter the page. There are some issues with load times of the line plot - this needs to be looked into. With respect to the data in the plots, all axes labels should remain static regardless of options selected (ie when selecting damage types and the corresponding axes). Generally, we need to optimize the user exploratory analysis experience.


## __Maintenance of Python Dashboard__  

---

Certain elements were prioritized over others when determining a workflow for maintenance. Since our app was working without any bugs, the primary goal was to clean up the code to make it easier to read and reproducable; the idea was that this would allow for easier maintenance and feature updates in the future. Next, it was important to incorporate the feedback from our peers and TA; there were certain elements of the dashboard that could immediately be addressed to make the overall experience more engaging - ideally more feedback would be required. Next, the principles of creating effective dashboards would be reviewed and the dashboard adjusted as required _(no time for this element)_. Finally, additional features would be added _(no time for this element)_. Items completed and outstanding are as follows:

### __Completed__

---

1. Implement known bug-fixes and work-arounds  
    - no known issues to fix  

2. Implement feedback you receive from peers during Lab 3's feedback session:  
  - __TA feedback__:    
    - examples were not removed as they provide guidance to users. Peer reviewers thought enclusion was useful.  
    - another plot for no damage was not created - this would clutter the page. The idea is to demonstrate that no-damage birdstrikes dwarf damage causing birdstrikes and an overlay best demonstrates this. A user would only look at either all damage causing birdstrikes together or non-damage causing birdstrikes.   
  - __Peer feedback__:  
    - direction was added to each selector identifying what plot it controls/adjusts.  
    - changed damage type in dropdown to match legend of plots.  
    - no change to the y-axis needed.    
    - no change to area plot vs line plot.  
      - area chart is more aesthetically pleasing and the interactive tools help in removing any confusion a user may have.  
    - bar chart is ordered in ascending order, x-axis is not meant to be "ordered".  
      - suggestion by peers would be a nice-to-have (perhaps a toggle to switch between type of ordering along the x axis).    
    - city's information not provided in data set.  

3. Clean-up and refactor code to make it more readable   
    - added margins to dashboard.  
    - consolidated tab content to be a list under the tab callback for both tabs (instead of returning two dbc elements at the callback return).  
    - changed tab colour and background colour.  
    - changed size of plots to better fit on a 1080p laptop screen.  
    - `mds_special` theme added.  
    - changed legend size for better readability.  
    - added tooltips to line plot over time.    
    - changed dcc object names to properly reflect their type.  
    - removed unneeded code. 
    - corrected grammar and added additional content on number of states represented.   

4. Reformated code and added docstrings (PEP8 style).  

### __Outstanding__

---

1. Implement feedback you receive from peers during Lab 3's feedback session.    
  - __TA feedback__:  
    - ensuring all states and airports appear on the map consistently, regardless of damage type, needs to be addressed _(see Alabama for substantial damage)_.    
    - if above bullet cannot be implemented, provide a ___warning___ message.  
  - organization of selectors and examples needs to be further examined and optimized for user experience.  
2. If needed, reorganize and restructure files/directory structure to separate different structures (Dash docs - Structuring a Multi-Page App for suggested organizations).    
  - not necessarily required for this project.    
3. Apply principles of creating effective dashboards (Lecture 4).  
4. Implement any new features (if time permits).    
  - need to figure out how to have plots size and scale automatically instead of setting property sizes of the Iframes and altair plots.

#### __Feature Wish List__   

- Option to show data over months rather then years, allowing for "yearly cycle" analysis.      
- Update bird count for bar plot when specific year range is selected.  
- Add a cross line guides feature together with the mouse interactive tool to explore the heat map.  This will prevent the user from getting lost when there are too many features to explore.    
- Import features that could use the same plots layout and automatically generate them using different data.    


### __Lab Activity Feedback Summary__

A list of summarizing all the issues can be found in [issue 41](https://github.com/UBC-MDS/Group_105/issues/41). 

In general, the app was not at all difficult to use by the peer reviewers. However, it was noticed by the app creators that because the plots were on the bottom and controls on the top, the peer reviewers started clicking without observing the changes on the plot and became confused. The general conclusions from this feedback activity are as follows:  

1. Consider reducing the number of questions to allow the controls and plots to be visible at the same time.  
2. Modify labels of plots to include units, so users understand that they are looking at the total number of bird strikes and not averages. 
3. Resize the plots if there are still size issues. We might consider moving the list of questions to another tab.  
4. Maintain consistency in the dropdown selection and plot legends ("No damage" is the same as "None").  