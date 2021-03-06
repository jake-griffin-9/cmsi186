# CMSI 186: Homework Assignment #3
## Problems About Dice [Familiarity with Java Classes]
### Assignment Due: Thursday, 2020-10-01

<blockquote>

<strong>Learning Outcomes</strong>: Students will (1) be familiar with Java classes at a basic level; (2) understand the purpose of constructors, fields, and methods; (3) understand and be able to explain the difference between instance (nonstatic) members and class (static) members of a class; (4) create, fill, and index Java arrays; (5) have a basic understanding of the differences between arrays as lists in Java; (6) be able to build and use applications with multiple classes; and (7) create simple textual user interfaces [TUI's].

</blockquote>

### For this homework:

...you will create a dice rolling game called **_HighRoll_**. The game is to try to make the maximum possible score using a set of dice. Dice in the set can have any number of sides, with the requirement that all dice in the set have the same number of sides. There can be any number of dice in the set from one to an unlimited number. Users will play the game using an on-screen menu from which they will make a selection. After pressing ENTER the program will perform the user's desired operation. To do this, you must accomplish the following activities:

### First, make public class Die which contains at the very least, the following methods:

1.  **_public Die( int nSides )_**<br />
    // Constructor for a single die with sides numbered 1, 2, …, up to nSides
1.  **_public int roll()_**<br />
    // Returns a value as a result of randomly rolling this die
1.  **_public int getValue()_**<br />
    // Returns the curent value of this die which resulted from the last roll
1.  **_public int setSides( int nSides )_**<br />
    // change the configuration of this die and return the new number of sides
1.  **_public String toString()_**<br />
    // Instance method that returns a string-y representation of THIS die, e.g., "[11]"
1.  **_public static String toString()_**<br />
    // Classwide version of the preceding instance method
1.  **_public static void main( String[] args )_**<br />
    // The built-in test program for this class<br />
    // TRY TO TEST AT LEAST 10 DIFFERENT CONFIGURATIONS

### Next, make public class DiceSet which contains at the very least, the following methods:

1.  **_public DiceSet( int k, int n )_**<br />
    // Constructor for a set of k dice each with n-sides (k ? 1 and n ? four)
1.  **_public int sum()_**<br />
    // Returns the present sum of this set of dice
1.  **_public void roll()_**<br />
    // Randomly rolls all of the dice in this set; returns void since it just sets the values<br />
    // Use either of the "toString()" methods to get the values in the set
1.  **_public void rollIndividual( int i )_**<br />
    // Randomly rolls only the ith die in this set [indexed from zero]
1.  **_public int getIndividual( int i )_**<br />
    * Gets the value of the ith die in this set
1.  **_public String toString()_**<br />
    // Returns a string-y representation of this set of dice, e.g., "[3][9][12][4]"
1.  **_public static String toString( DiceSet ds )_**<br />
    // Classwide version of the preceding instance method
1.  **_public boolean isIdentical( DiceSet ds )_**<br />
    // Returns true iff this set is identical to the set ds passed as an argument<br />
    // with the ordering of the dice in each set is not important
1.  **_public static void main( String[] args )_**<br />
    // The built-in test program for this class

### Finally, make public class file HighRoll.java which uses your dice set to play the game. You will need to have a main that constructs the dice set, has rolls, and displays scores from each roll. The rules are as follows:

1. Implement a Textual User Interface (TUI) on the command line. This will display a list of options to the user, and will prompt for input.
1. <strong>Input MUST be a number from 1 to 5</strong>. Based on that input your program will perform the operation the user selected.
1. <strong>Your program MUST display the results</strong> of each operation, then skip a blank line or two, and then finally must re-display the options menu.
1. Your program must accept a "Q" character to quit the HighRoll game.  Make your program accept both the uppercase and lowercase character.
1. Your TUI menu must appear as follows
    * **1. ROLL ALL THE DICE**
    * **2. ROLL A SINGLE DIE**
    * **3. CALCULATE THE SCORE FOR THIS SET**
    * **4. SAVE THIS SCORE AS HIGH SCORE**
    * **5. DISPLAY THE HIGH SCORE**
    * **6. ENTER 'Q' TO QUIT THE PROGRAM**
1.  For option 2, <strong>you MUST accept a second number as part of the entry</strong>.  For example, your program would read "2 5" to re-roll only die number 5; this method means you must **parse** the input to get the die index [We'll discuss this in class].
1.  To run the program, you **MUST** start the program using...<br /><br />
    **_java HighRoll &lt;number of dice&gt; &lt;number of sides&gt;_**<br /><br />
1.  See the notes below.

### Notes:

1.  The method sum() in the DiceSet class should return an integer, not a long.
1.  There is a minimum number of sides that a die may have. When you think about it, a two-sided die is just a coin: heads or tails are the only values possible, corresponding to one or two, zero or one, on or off, light or dark, etc. Since this isn't a "Coin" class, don't use that.
1.  Likewise, there is no such thing as a "three-sided" die. Such an item is not possible in this 3D world we inhabit. A case could be made for a hollow prism to be a three-sided die, but we would then have to define the inside faces of each side as "non-existent" or "not counted" or some such lame excuse to prevent confusion with a six-sided die.
1.  A four-sided die would be a tetrahedron [also known as a pyramid]. You can use that, but since it will never end up on its point, it is a bit hard to define what it's value would be when rolled, without coming up with a convention to unequivocably pick a side to which you can refer as its "value". If you can do that, or you can make a case in which it doesn't matter, go for it.
1.  A five-sided die is possible, if you take a tetrahedron and chop off the top to make a frustum. This would look like a pyramid with the top flattened out, or you could have a prism with the top and bottom [or ends] being solid triangular shapes. This is probably the smallest usable number of sides in real life.
1.  All that being said, this IS a sort of "thought problem" so if you can figure out a way to use even a one-sided die [pretty boring rolling that one], feel free!
1.You might be tempted to say You know, I'm only getting ONE value no matter what, so it really doesn't matter HOW many sides the die has as long as I have a random value when I roll it. However, by convention, each side of a die has a different number, with the default being that the top face on the die is the value of the roll. This also means if I have a six-sided die, there's no way I can get an 11 on that die unless something is **drastically** hinky…
1.  Note that you should only allow the user to quit the game by using the QUIT option from the menu. That means you will implement a "good endless loop" as discussed in class.

### Submission Guidelines:
Make a sub-directory in your repository as mentioned above, called "homework03" and commit your source code into it. DON'T FORGET TO ADD A COMMIT COMMENT!""

