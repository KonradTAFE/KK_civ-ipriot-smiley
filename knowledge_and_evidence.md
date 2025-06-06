# Evidence and Knowledge

This document includes instructions and knowledge questions that must be completed to receive a *Competent* grade on this portfolio task.

## 1. Required evidence

### 1.1. Answer all questions in this document

- Each answer should be complete, well-articulated, and within the specified word count limits (if added) for each question.
- Please make sure **all** external sources are properly cited.
- You must **use your own words**. Please include your full chat transcripts if you use generative AI in any way.
- Generative AI hallucinates, is not an authoritative source

### 1.2. Make all the required modifications to the code

- Please follow the instructions in this document to make the changes needed to the code.

- When requested to upload evidence, upload all screenshots to `screenshots/` and embed them in this document. For example:

```markdown
![Example Running Code](screenshots/screenshot1.png)
```

![Sample](screenshots/sample.png)
> Note the `!`, and the use of a relative path.

- You must upload the code into your GitHub repository.
- While you can use a branch, your code should be in main when you submit.
- Upload a zip of this repository to Blackboard when you are ready to submit.
- You will be notified of your result via Blackboard
- However, if using GitHub classrooms, you may also receive additional feedback on GitHub directly

### 1.3. Optional: Use of Raspberry Pi and SenseHat

Raspberry Pi or SenseHat is **optional** for this activity. You can use the included `sense_hat.py` file to simulate the SenseHat on your computer.

If you use a Pi, please **delete** the `sense_hat.py` file.

### 1.4. Accessible version of the code

This project relies on visual patterns that appear on an LED matrix. If you have any accessibility requirements, you can use the `udl/accessible` branch to complete the project. This branch provides an accessible code version that uses text-based patterns instead of visual ones.

Please discuss this with your lecturer before using that branch.

## 2. Specific Tasks & Questions

Address the following tasks and questions based on the code provided in this repository.

### 2.1. Set up the project locally

1. Fork this repository (if not using GitHub Classrooms)
2. Clone your repository locally
3. Run the project locally by executing the `main.py` file
4. Evidence this by providing screenshots of the project directory structure and the output of the `main.py` file

![Local Execution (INSERT YOUR SCREENSHOT)](screenshots/CREATE_A_SCREENSHOT_OF_YOUR_local_setup.png)
![img.png](screenshots%2Fimg.png)
If you are running on a Raspberry Pi, you can use the following command to run the project and then screenshot the result:

```bash
ls
python3 main.py
```

### 2.2. Fundamental code comprehension

 Answer each of the following questions **as they relate to that code** supplied by in this repository (ignore `sense_hat.py`):

1. Examine the code for the `smiley.py` file and provide  an example of a variable of each of the following types and their corresponding values (`_` should be replaced with the appropriate values):

   | Type                    | name           | value           |
   | ----------              |----------------|-----------------|
   | built-in primitive type | (bool) dimmed  | True            |
   | built-in composite type | (tuple) WHITE  | (255, 255, 255) |
   | user-defined type       | (class) Smiley | n/a             |

2. Fill in (`_`) the following table based on the code in `smiley.py`:

   | Object                   | Type        |
   | ------------             |-------------|
   | self.pixels              | list        |
   | A member of self.pixels  | tuple       |
   | self                     | happy.Happy |

3. Examine the code for `smiley.py`, `sad.py`, and `happy.py`. Give an example of each of the following control structures using an example from **each** of these files. Include the first line and the line range:

   | Control Flow | File      | First line | Line range |
   | ------------ |-----------|------------|------------|
   |  sequence    | smiley.py | 15         | 26         |
   |  selection   | sad.py    | 26         | 29         |
   |  iteration   | happy.py  | 21         | 22         |

4. Though everything in Python is an object, it is sometimes said to have four "primitive" types. Examining the three files `smiley.py`, `sad.py`, and `happy.py`, identify which of the following types are used in any of these files, and give an example of each (use an example from the code, if applicable, otherwise provide an example of your own):

   | Type                    | Used? | Example         |
   | ----------------------- |-------|-----------------|
   | int                     | N     | age = 32        |
   | float                   | Y     | delay=0.25      |
   | str                     | N     | name = "Konrad" |
   | bool                    | Y     | dimmed=True     |

5. Examining `smiley.py`, provide an example of a class variable and an instance variable (attribute). Explain **why** one is defined as a class variable and the other as an instance variable.

> Class Smiley variable: YELLOW = (255, 255, 0)
> YELLOW variable is defined under class definition and applies to all instances of the class,
> which means that variable YELLOW can be used throughout all instances of the Smiley class.
> 
> Instance variable: Y = self.YELLOW
> When a new instance of class Smiley is created, variable Y gets bound to the class variable YELLOW. 
> As Y is created with the new instance, it can only be used within the instance and not the Smiley class.   

6. Examine `happy.py`, and identify the constructor (initializer) for the `Happy` class:
   1. What is the purpose of a constructor (in general) and this one (in particular)?

   > In general: a constructor is a method of creating and object (initializing an instance of the class) by setting up its attributes
   > 
   > In case of 'Happy' class initializer: when a new class is created, all attributes from super classes Smiley and Blinkable are initialized and applied to the new class
   > together with 2 methods: draw_mouth and draw_eyes

   > GeeksforGeeks. (2018). Constructors in Python. [online] Available at: https://www.geeksforgeeks.org/constructors-in-python/.

   2. What statement(s) does it execute (consider the `super` call), and what is the result?

   > Statement: super().__init__()
   > Result: applies the attributes from superclasses Smiley (variables WHITE, GREEN, RED, YELLOW, BLANK) 
   > and Blinkable (@abstractmethod) to the newly created instance; 
   > 
   > Statements: self.draw_mouth() // self.draw_eyes()
   > Result: upon initialization of the new instance, the Happy class methods will be automatically applied to the Smiley

### 2.3. Code style

1. What code style is used in the code? Is it likely to be the same as the code style used in the SenseHat? Give to reasons as to why/why not:

> The code style is PEP8 for readability and maintainability. Its main purpose is for the programmers to better understand the code.
> Because of that, SenseHAT does not necessarily have to use the same code style: its code needs to be functional only.
> 
> One of the basic rules of PEP8 is using snake_case for variable names while also giving variables meaningfull names.
> As SenseHAT uses built-in functions to operate the LED matrix, joystick and sensors internally, 
> their names do not have to follow the same convention.
> 
> www.raspberrypi.com. (n.d.). Raspberry Pi Documentation - Sense HAT. [online] Available at: https://www.raspberrypi.com/documentation/accessories/sense-hat.html.
> 
> > van Rossum, G., Warsaw, B. and Coghlan, N. (2001). PEP 8 – Style Guide for Python Code. [online] peps.python.org. Available at: https://peps.python.org/pep-0008/.

2. List three aspects of this convention you see applied in the code.

> 1. Four spaces indentation
> 2. snake_case variable names
> 3. Limit all lines to a maximum of 79 characters
> 
> van Rossum, G., Warsaw, B. and Coghlan, N. (2001). PEP 8 – Style Guide for Python Code. [online] peps.python.org. Available at: https://peps.python.org/pep-0008/.

3. Give two examples of organizational documentation in the code.

> 1. Comment: # We have encapsulated the SenseHat object
> 
> 2. Docstring:   
> """
> Provides a Smiley with a happy expression
> """

### 2.4. Identifying and understanding classes

> Note: Ignore the `sense_hat.py` file when answering the questions below

1. List all the classes you identified in the project. Indicate which classes are base classes and which are subclasses. For subclasses, identify all direct base classes.
  
  Use the following table for your answers:

| Class Name | Super or Sub? | Direct parent(s)  |
|------------|---------------|-------------------|
| Smiley     | Super         | N/A               |
| Blinkable  | Sub           | ABC               |
| Happy      | Sub           | Smiley, Blinkable |
| Sad        | Sub           | Smiley            |

2. Explain the concept of abstraction, giving an example from the project (note "implementing an ABC" is **not** in itself an example of abstraction). (Max 150 words)

> In the code, an abstract class Blinkable is created with an abstract, empty method 'blink'.
> The class does not have any constructor, which means it is impossible to create an instance of the class,
> however it is possible to use it as a superclass.
> Using Blinkable as superclass (as in case of Happy) means the child-class needs its own definition
> of blink method, without which the code will give  an error.
> 
> In this case, Abstraction of the class Blinkable means it does not have its own instances or defined methods,
> but binds the child-class to certain actions or attributes.
> 
> GeeksforGeeks. (2023). Data Abstraction in Python. [online] Available at: https://www.geeksforgeeks.org/data-abstraction-in-python/.

3. What is the name of the process of deriving from base classes? What is its purpose in this project? (Max 150 words)

> This process is called Inheritance. Its purpose is for the child-classes to use the same attributes and methods as
> their parent / super classes and belong to the same object type.
> In this project, Smiley superclass serves as a base template for creating a Happy or Sad smiley face.
> Through inheritance, Happy and Sad classes initiate a new SenseHat object as well as use the same pixels list and 
> variables holding colors definitions as the superclass

### 2.5. Compare and contrast classes

Compare and contrast the classes Happy and Sad.

1. What is the key difference between the two classes?
   > Happy uses two superclasses (Smiley, Blinkable) while Sad only uses one (Smiley)
   >
2. What are the key similarities?
   > Both classes are a child of Smiley and define draw_mouth() and draw_eyes() methods
   >
3. What difference stands out the most to you and why?
   > While Happy class uses tertiary operator to change the attribute of pixels,
   > Sad reassigns the value for "eyes" to achieve the same result. 
   >
4. How does this difference affect the functionality of these classes
   > Variable "eyes" starts as an iterable list of pixels to be changed, but later on
   > gets reassigned to a single value: self.BLANK or self.YELLOW. This means eyes is no longer
   > a list after this block of code, hence is not reusable
   >

### 2.6. Where is the Sense(Hat) in the code?

1. Which class(es) utilize the functionality of the SenseHat?
   > As Sad and Happy are child-classes of Smiley class, all three of them utilize the SenseHat functionality
   >
2. Which of these classes directly interact with the SenseHat functionalities?
   > Smiley is the only class which directly interacts with SenseHat by importing sense_hat library
   >
3. Discuss the hiding of the SenseHAT in terms of encapsulation (100-200 Words)
   > In current project, SenseHAT is hidden in the base class Smiley and can only be accessed by creating an instance
   > of this class. All the methods for using SenseHAT are defined within the base class. This enhances protection, 
   > reusability and maintainability of the class, which are core rules for encapsulation.
   > By encolsing SenseHAT access to main class, we can create child-classes which will inherit the
   > methods of accessing SenseHat only with predetermined set of attributes. 
   > In this project, Happy and Sad classes deal only with the way the smiley will look - happy or sad, 
   > by changing pixels in the list of pixels of the superclass, Smiley.
   >
> 
> Bex Tuychiev. “Encapsulation in Python: A Comprehensive Guide.” Datacamp.com, DataCamp, 29 Apr. 2024, www.datacamp.com/tutorial/encapsulation-in-python-object-oriented-programming.

### 2.7. Sad Smileys Can’t Blink (Or Can They?)

Unlike the `Happy` smiley, the current implementation of the `Sad` smiley does not possess the ability to blink. Let's first explore how blinking has been implemented in the Happy Smiley by examining the blink() method, which takes one argument that determines the duration of the blink.

**Understanding Blink Mechanism:**

1. Does the code's author believe that every `Smiley` should be able to blink? Explain.

> No, only Happy Smiley inherits and overrides the blink method of Blinkable superclass and therefore only Happy can blink.
>

2. For those smileys that blink, does the author expect them to blink in the same way? Explain.

> No, the blink method in Happy allows for a different blink delay to be specified.
>

3. Referring to the implementation of blink in the Happy and Sad Smiley classes, give a brief explanation of what polymorphism is.

> Polymorphism is a concept of allowing unrelated objects to be treated as objects of the same type by binding them to a common superclass,
> which, as in this case, contains an empty (abstract) method which needs to be overriden within the subclass.
>

4. How is inheritance used in the blink method, and why is it important for polymorphism?

> Polymorphism is achieved through inheritance: to properly use polymophism, we need to bind different objects to the same superclass
> which will make them inherit the superclass's mathods which can be later overriden within the object, and the objects can be treated as
> same class objects.
> Blink method is defined as abstract on the superclass Blinkable level. Since Happy class is a subclass of Blinkable, it has access to
> 'blink', but needs to redefine it (overwrite) since the method is abstract, empty.

>www.w3schools.com. (n.d.). Python Polymorphism. [online] Available at: https://www.w3schools.com/python/python_polymorphism.asp.

1. **Implement Blink in Sad Class:**

   - Create a new method called `blink` within the Sad class. Ensure you use the same method signature as in the Happy class:

   ```python
   def blink(self, delay=0.25):
       pass  # Replace 'pass' with your implementation
   ```

2. **Code Implementation:** Implement the code that allows the Sad smiley to blink. Use the implementation from the Happy Smiley as a reference. Ensure your new method functions similarly by controlling the blink duration through the `delay` argument.

3. **Testing the Implementation:**

- Test the new blink functionality on your Raspberry Pi or within the Python classes provided. You might need to adjust the `main.py` script to incorporate Sad Smiley's new blinking capability.

Include a screenshot of the sad smiley or the modified `main.py`:

![Sad Smiley Blinking](screenshots/sad_blinking.png)
![image.png](screenshots%2Fimage.png)
!![image_2.png](screenshots%2Fimage_2.png)
- Observe and document the Sad smiley as it blinks its eyes. Describe any adjustments or issues encountered during implementation.

  > Smiley closed eyes but didn't reopen them - had to "import time"

  ### 2.8. If It Walks Like a Duck…

  Previously, you implemented the blink functionality for the Sad smiley without utilizing the class `Blinkable`. Assuming you did not use `Blinkable` (even if you actually did), consider how the Sad smiley could blink similarly to the Happy smiley without this specific class.

  1. **Class Type Analysis:** What kind of class is `Blinkable`? Inspect its superclass for clues about its classification.

     > Blinkable is an abstract class, an interface intended to force its subclasses to implement some behaviours (methods)

2. **Class Implementation:** `Blinkable` is a class intended to be implemented by other classes. What generic term describes this kind of class, which is designed for implementation by others? **Clue**: Notice the lack of any concrete implementation and the naming convention.

> Blinkable is an Interface - a contract between a class and its users; it specifies a methods that a subclass must implement.
> 
> Kant, S. (2023). Interfaces and Abstract Classes in Python: Understanding the Differences. [online] Medium. Available at: https://medium.com/@shashikantrbl123/interfaces-and-abstract-classes-in-python-understanding-the-differences-3e5889a0746a.

  3. **OO Principle Identification:** Regarding your answer to question (2), which Object-Oriented (OO) principle does this represent? Choose from the following and justify your answer in 1-2 sentences: Abstraction, Polymorphism, Inheritance, Encapsulation.

  > Blinkable represents the principle of Abstraction - it is a class which cannot be initialed on its own, but rather serves as a blueprint for other classes to follow.

  4. **Implementation Flexibility:** Explain why you could grant the Sad Smiley a blinking feature similar to the Happy Smiley's implementation, even without directly using `Blinkable`.

  >  We can define a 'blink' method since it uses the 'draw_eyes' method defined within the class as well as 'show' method defined on superclass. Not using Blinkable means Sad doesn't have to implement blink method.

  5. **Concept and Language Specificity:** In relation to your response to question (4), what is this capability known as, and why is it feasible in Python and many other dynamically typed languages but not in most statically typed programming languages like C#? **Clue** This concept is hinted at in the title of this section.

  > It is an example of Duck typing - since Sad Smiley implements the 'blink' method and has all necessary attributes to do it, Python interprets it as a class of the same type as Happy.
  > This capability is dynamically typed languages like Python as we do not need to specify the type of objects and can use them interchangeably based on their behavior without worrying about their types. 

  ***

  ## 3. Refactoring

  ### 3.1. Does a Smiley Have to Be Yellow?

  While our current implementation predominantly features yellow smileys, emotional expressions like sickness or anger typically utilize colors like green, red, or orange. We'll explore the feasibility of integrating these colors into our smileys.

  1. **Defined Colors and Their Location:**

     1. Which colors are defined and in which class(s)?
        > Smiley class defines colors: WHITE, GREEN, RED, YELLOW, BLANK (black)

     2. What type of variables hold these colors? Are the values expected to change during the program's execution? Explain your answer.
        > Colors are held in constant tuples which represent the colors in RGB scale. The colors are not expected to change, which is why they are written in capitals.
     3. Add the color blue to the appropriate class using the appropriate format and values.
        > BLUE = (0, 0, 255)

  2. **Usage of Color Variables:**

     1. In which classes are the color variables used?
        > Colors are used in Smiley (to draw the while face circle), Sad (eyes and sad mouth) and Happy (eyes and happy mouth)

  3. **Simple Method to Change Colors:**
  4. What is the easiest way you can think to change the smileys to green? Easiest, not necessarily the best!
     > Change the definition of YELLOW in Smiley class to (0, 255, 0).

  Here's a revised version of the "Flexible Colors – Step 1" section for the smiley project, incorporating your specifications for formatting and content updates:

  ### 3.2. Flexible Colors – Step 1

  Changing the color of the smileys once is straightforward, but it isn't very flexible. To facilitate various colors for smileys, it is advisable not to hardcode values in any class. This approach was identified earlier as a necessary change. Let's start by removing the built-in assumptions about color in our classes.

  1. **Add a method called `complexion` to the `Smiley` class:** Implement this instance method to return `self.YELLOW`. Using the term "complexion" instead of "color" provides a more abstract terminology that focuses on the meaning rather than implementation.

  2. **Refactor subclasses to use the `complexion` method:** Modify any subclass that directly accesses the color variable to instead utilize the new `complexion` method. This ensures that color handling is centralized and can be easily modified in the future.

  3. **Determine the applicable Object-Oriented principle:** Consider whether Abstraction, Polymorphism, Inheritance, or Encapsulation best applies to the modifications made in this step.

  4. **Verify the implementation:** Ensure that the modifications function as expected. The smileys should still display in yellow, confirming that the new method correctly replaces the direct color references.

  This step is crucial for setting up a more flexible system for color management in the smiley display logic, allowing for easy adjustments and extensions in the future.

  ### 3.3. Flexible Colors – Step 2

  Having removed the hardcoded color values, we now enhance the base class to support dynamic color assignments more effectively.

  1. **Modify the `__init__()` method in the `Smiley` class:** Introduce a default argument named `complexion` and assign `YELLOW` as its default value. This allows the instantiation of smileys with customizable colors.

  2. **Introduce a new instance variable:** Create a variable called `my_complexion` and assign the `complexion` parameter to it. This step ensures that each smiley instance can maintain its own color state.

  3. **Rationale for `my_complexion`:** Using a distinct instance variable like `my_complexion` avoids potential conflicts with the method parameter names and clarifies that it is an attribute specific to the object.

  4. **Bulk rename:** We want to update our grid to use the value of complexion, but we have so many `Y`'s in the grid. Use your IDE's refactoring tool to rename all instances of the **symbol** `Y` to `X`. Where `X` is the value of the `complexion` variable. Include a screenshot evidencing you have found the correct refactor tool and the changes made.

  ![Bulk Rename](screenshots/bulk_rename.png)

  5. **Update the `complexion` method:** Adjust this method to return `self.my_complexion`, ensuring that whatever color is assigned during instantiation is what the smiley displays.

  6. **Verification:** Run the updated code to confirm that Smileys still defaults to yellow unless specified otherwise.

  ### 3.4. Flexible Colors – Step 3

  With the foundational changes in place, it's now possible to implement varied smiley colors for different emotional expressions.

  1. **Adjust the `Sad` class initialization:** In the `Sad` class's initializer method, change the superclass call to include the `complexion` argument with the value `self.BLUE`, as shown:

     ```python
     super().__init__(complexion=self.BLUE)
     ```

  2. **Test color functionality for the Sad smiley:** Execute the program to verify that the Sad smiley now appears blue.

  3. **Ensure the Happy smiley remains yellow:** Confirm that changes to the Sad smiley do not affect the default color of the Happy smiley, which should still display in yellow.

  4. **Design and Implement An Angry Smiley:** Create an Angry smiley class that inherits from the `Smiley` class. Set the color of the Angry smiley to red by passing `self.RED` as the `complexion` argument in the superclass call.
   ![img.png](screenshots/angry.png)
  ***
