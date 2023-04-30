Download Link: https://assignmentchef.com/product/solved-hungry-squirrel-2
<br>
5/5 - (2 votes)

For the final exam project, you will write a game application called “Hungry Squirrel”.  In this game, there is a Squirrel in a maze looking for nuts.  You will guide the squirrel to find and collect the nuts. There are two types of nuts available in the maze, Almonds and Peanuts.  As the squirrel eats the nuts, it gains nutritional points. Once the squirrel finds all the nuts in the maze, the game is over. To implement this game, you will define 8 classes: Maze class, Entity class, Squirrel class, Wall class, Nut class, Almond class, Peanut class, and HungrySquirrelGame class. Each class is described in details in the following sections.

The following class diagram shows the class hierarchy between the classes:

EntityNutSquirrelPeanutAlmondMovable

Wall&lt;impl

In this document, you will find each class defined in details. There is enough information to help you build and implement this game. The class description does not provide or describe the Constructors, setter/getter methods or toString method, you should add them as needed. You are not required to implement the class attributes and methods exactly as specified here; feel free to add/remove attributes or methods as you see fit. However, you must define each class and do not make modifications to the class names.

1.     Entity ClassYou must define an abstract “Entity” class.  Three types of entities exist in the Maze: Nut, Squirrel and Wall.  Each entity has three attributes:

1.       symbol: This instance variable is a character symbol by which an entity is identified on the Maze.  For example, a squirrel is represented by ‘@’. Each nut will be represented by the first character of its name (e.g. Almond will be represented by ‘A’).

2.       row: This instance variable is the row position of the entity in the maze.

3.       column: This instance variable is the column position of the entity in the maze.

The abstract Entity class contains an abstract method:

public void create();

The Entity class contains the following concrete method:

public Entity put(int newRow, int newCol)

This method puts an entity at location (newRow, newCol) in the maze. You have to pay attention because the entity cannot move to a location already filled with a wall (i.e. ‘*’).  This method returns an Entity that was replaced in the new location. This can be useful when moving the squirrel and figuring out if it ate a nut.

2.     Movable InterfaceThe Movable interface declares a single method and is implemented by Entities that can move in the maze (e.g. Squirrel)

void move(char direction);

3.     Squirrel ClassYou must define the Squirrel class. The squirrel is represented by the “@” symbol in the maze. It is able to move up, down, left and right.  The initial location of the squirrel is determined by the user. The program must prompt the user to enter the starting row and column of the squirrel. The squirrel cannot move to where there is a wall (i.e. ‘*’).  Once the squirrel moves over a nut, it eats the nut and collects points.  Each type of nut carries a different point.

The Squirrel class is inherited from the Entity abstract class. The Squirrel class implements the Movable interface. The Squirrel class contains two attributes:

1.      pointsCollected: This attribute provides the total points a squirrel object has accumulated as a result of gathering nuts.

2.      totalNutsEaten: This attribute provides the total number of nuts eaten thus far.

The Squirrel class defines the following methods:

public void create()

This method provides the implementation of the abstract method in the Entity superclass.  This method asks the user to provide the initial location of the squirrel in the maze.  You have to make sure the location provided by the user is valid and available. If the user provides an invalid or unavailable location, you will have to ask the user to input a new set of data.  You must continue until the user provides a valid position. Keep in mind that a squirrel cannot be placed where there is a wall ‘*’.

public void move(char direction)

This method moves the squirrel one position to the direction specified.

4.     Wall ClassWall is a class that is inherited from Entity super class.  Walls are stationary and won’t move in the maze. The wall class has the following attribute:

static final char symbol = ‘*’

5.     Nut ClassNut is an abstract super class that is inherited from Entity super class.  There are two types of nuts available: Almond and Peanut. When a squirrel eats a nut, it’ll gain points. Once a nut is eaten, it should disappear from the maze. There are total of 5 nuts created. The nuts locations are created randomly in the maze and have to be placed in a valid location in the maze, meaning that a nut cannot be put in a position occupied by a wall (*), a squirrel (@) or a previously created nut. The number of peanuts / almonds are based on a random 50% chance.

The Nut class contains the following attribute:

1.       Total Nuts: This class variable is a constant variable that represents the total number of nuts that will be created for this game (For this project, we create 5 nuts).

2.       NutritionPoints: This instance variable stores then nutrition points of the nut.

3.       Name: This String instance variable is the name of the nut (“Almond” or “Peanut”)

The Nut class implements the following methods:

void create()

This method implements the abstract method in the Entity superclass.  This method randomly creates the location of the nuts.  You have to make sure the locations are valid and available. Keep in mind that a nut cannot be placed over a wall (*), a squirrel (@) or a previously created nut. In other words, it can only be placed where there is a blank space (‘ ‘).

6.     Almond ClassAlmond is a type of a Nut .  An almond is represented by the character symbol ‘A’ in the maze.  An almond carries 5 nutritional points; therefore, when the squirrel eats an almond, it gains 5 points.

The Almond Class is inherited from the Nut abstract super class. The Almond class defines the following attribute:

1.       Nutrition Points: This class variable is a constant variable that represents the nutrition points an almond carries.

7.     Peanut ClassPeanut is a type of a Nut.  A peanut is represented by the character symbol ‘P’ in the maze.  A peanut carries 10 nutritional points; therefore, when the squirrel eats a peanut, it gains 10 points.

The Peanut Class is inherited from the Nut abstract super class. The Peanut class defines the following attribute:

1.       Nutrition Points: This class variable is a constant variable that represents the nutrition points a peanut carries.

8.     The Maze ClassYou must define the Maze class.   The maze is a 20 x 50 rectangular area represented by a 2-dimensional Entity array.   The walls in the maze are represented by ‘*’ and available positions by blank space. The maze structure is read from a text file “Maze.txt” (The Maze.txt will be provided to you). A squirrel is able to freely move in blank spaces in the maze.

**************************************************

********************                **********************

********************                **********************

********************                **********************

***********                                                        ***********

***********                                                        ***********

*                                                                                              **

*                                                                                              **

*                                                                                              **

*                           **********************                       **

*                           **********************                       **

*                           **********************                       **

*                           **********************                       **

*                                                                                              **

*                                                                                              **

*                                                                                              **

*****                            **************                  ********

************                                                  *************

*****                                                                        *********

**************************************************

The Maze class defines the following attributes:

1.       Max_Maze_Row: This class variable is a constant variable that defines the maximum number of rows in the maze (it should be set to 20 rows).

2.       Max Maze Column: This class variable is a constant variable that defines the maximum number of columns in the maze (it should be set to 50 columns).

3.       maze[][] : This class variable is a 2-dimentional Entity array that contains the full maze and the entities.

The Maze class implements the following methods:

public static void create(String filename)

This method reads the file passed to the method (i.e. Maze.txt) and initializes the 2-dimentional array with the maze content provided in the file.

public static void display()

This method displays the maze structure and the containing entities.

public static boolean available(int row, int col)

This method takes a row and a column and determines if the location at the row and the column is blank space. If it is, it returns true; otherwise, it returns false.

9.     HungrySquirrelGame ClassThe HungrySquirrelGame class defines the main method.  The flow of the main method can be something like this:

1.      Call the create method of the Maze class to create the maze.

2.      Instantiate a squirrel object. This creates the squirrel and  puts the squirrel in the maze based on the user input.

3.      Instantiate an array of Nut objects and determine and create the type of nuts (almond or peanut).

4.      Display the maze with all the entities created.

5.      Accept user input to move the squirrel.

6.      For every move the full maze with all the entities should be displayed.

7.      Every time the squirrel collects a nut, a message must be output displaying the points collected for the new nut and total points collected thus far.

!!! Squirrel ate Almond and gained 5 points (Total 15 points) !!!

8.      Once the squirrel collects all the nuts, a message must be displayed and the game is over.

“Squirrel successfully collected all the nuts. Total points 30.”

“Thank you for playing this game”

**************************************************

********************                    **********************

********************                    **********************

********************                    **********************

***********                                                          ************

***********                                                          ************

*                                                                                                  **

*                                                                                                  **

*                                                                                                  **

*                           **********************                           **

*                           **********************                           **

*                           **********************                           **

*                           **********************                           **

*                                                                                                  **

*                                                                                                  **

*                                                                                                  **

*****                            **************                      ********

************                                                      *************

*****                                                                            *********

**************************************************

Enter the Squirrel position (row , column): 1,1

Position not available. Try again!

Enter the Squirrel position (row , column): 7,23

User input accepted.

Enter commands u,d,l,r to move Up, Down, Left, and Right:

**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                          @                                                    **

*                                                                                                  **

*                 A                                                               P             **

*                           **********************                           **

*                           **********************                           **

*           P              **********************                           **

*                           **********************                           **

*                                                                                    A           **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 P                                         *********

**************************************************

Enter command: d

**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                                                                                 **

*                                          @                                                    **

*                 A                                                               P             **

*                           **********************                           **

*                           **********************                           **

*           P              **********************                           **

*                           **********************                           **

*                                                                                    A           **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 P                                         *********

**************************************************

**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                                                                                 **

*                                                                                                  **

*                                                                                                  **

*                           **********************                           **

*                           **********************                           **

*                            **********************                           **

*                           **********************                           **

*                                                                                                  **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 @                                        *********

**************************************************

Squirrel successfully collected all the nuts. Total points 40

Thank you for playing this game

10.           Extra Credit (+3 Points)Define a new entity called “PoisonousCashew”. Poisonous cashews are bad for the squirrel and carry negative nutrition points (-15 points).  If a squirrel collects poisonous cashews and its total points become negative, the squirrel dies and the game is over. There are total of 5 poisonous cashews in the maze.

11.           Grade Negotiation TableThe following table provides the grade weight for each class that is implemented. You will have the option of asking for two of the class implementation in return of giving away points.

ClassPointsMaze Class10Entity Class10Squirrel Class7Nuts Class5Almond Class3Peanut Class3HungrySquirrelGame Class1012.           Final Project Submittal Instructions and Grading ProcessThe final project is due before the midnight of the due date. Your final project must be written in NetBeans IDE.  To submit your final project, you must create a zip file of your NetBeans project and submit your project on Canvas.  Your NetBeans project name should be your firstname and lastname with no spaces in between (e.g. AmirHallajpour) and the project zip file must have the same name as your project.