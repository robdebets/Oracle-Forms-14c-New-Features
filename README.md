# Oracle Forms 14c New Features
 
On 20 Decenber 2024 Michael Ferrante announced Oracle Forms and Reports 14c (14.1.2.0). For this release I "waited" for a long time, and was very eager to explore all the new features I saw in a demo at the DOAG 2024. Unfortunately, Oracle does not share any demo-code, so I had to do this for myself.<br/>
Why not share this with the rest of the community? I asked Michael whether he had problems when I published a demo-form that showed a lot of new features, in more or less the same way as he did. No problems, thanks Michael! So here it is!

A lot of these features are described in https://www.oracle.com/a/otn/docs/oracleforms-1412-newfeatures.pdf. In this readme I will show screenshots of the demo-form, with a textual reference to described features (since it won't be easy for everybody to get a forms-environment up and running).<br/>
In a final chapter I'll describe some relevant settings to get this demo started.

Disclaimer: the contents of the demo are for learning and demonstration purposes only!

## Push Buttons
![](resources/14c-pushbuttons.gif)
Runtime Features > User Interface > Push Buttons

## Edit/List
![](resources/14c-edit-list.gif)
Runtime Features > User Interface > Text Items<br/>
Runtime Features > User Interface > List Items

## Booleans
![](resources/14c-booleans.gif)
Runtime Features > User Interface > Boolean Items

## Display
![](resources/14c-display.gif)
Runtime Features > User Interface > Display Items

## Employees
![](resources/14c-emp.gif)
Runtime Features > User Interface > Multi Record Blocks<br/>
Runtime Features > Data Access, Monitoring and Manipulation > Continuous Query Notification

## Bars
![](resources/14c-bars.gif)
Runtime Features > User Interface > Multi Record Blocks > Dynamic Size Block

## Tiles
![](resources/14c-tiles.gif)
Runtime Features > User Interface > Multi Record Blocks > Tiles

## REST-services
![](resources/14c-rest.gif)
Runtime Features > Data Access, Monitoring and Manipulation > REST

## Glass
![](resources/14c-glass.gif)
Runtime Features > User Interface > Fill Pattern Property

## Misc
![](resources/14c-misc.gif)
Runtime Features > User Interface > Window > Canvas Window Scrollbars<br/>
Runtime Features > Miscellaneous Runtime Features > Image Copy<br/>
Runtime Features > User Interface > Canvasses > Stacked Canvas Splitter<br/>
Runtime Features > User Interface > Alerts

## Colors
![](resources/14c-colors.png)
Just a tab to test some predefined colors

# Installation
As database, I used Oracle 23ai with Virtual Box. Schema HR.<br/>
Installed Weblogic and Forms and Reports 14c<br/>
Compiled demofeat.fmb
To run the demo, see demo.jnlp<br/><br/>

To get CQN working: login as SYS in SQL Developer:<br/>
1. grant execute on dbms_cq_notification to hr;<br/>
2. grant change notification to hr;<br/>

<!-- eol -->

To see it in action:<br/>
1. Start a first session, go to tab Employees, execute Query<br/>
2. Start a second session, go to tab Employees, execute Query<br/>
3. Make a change, eg name James > Jameson + Save<br/>
4. Go to the first session, do navigation (eg move to another record) and then "Data set has changed. Requery recommended" will appear.<br/>
(perhaps you get an error for constraint HR.JHIST_EMP_ID_ST_DATE_PK: delete it or truncate table job_history... stupid PK anyway)<br/><br/>

For the custom fonts (tab Misc) to work: change default.fontMap.defaultMapping in registry.dat from full to partial