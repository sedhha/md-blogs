Hey Fellas!

# Introduction
I hope you all must be doing well. So here’s another cool Flutter project which I thought of sharing with you guys. Here we try creating a storybook based on the user’s choice. My passion has always been writing and creating fantasy stories and so here is one such app, which navigates you through my fantasy stories based upon the user’s choice and accordingly narrates the happenings till the end. This project again has been inspired by AppBrewery. You can see their GitHub repo by clicking here.

So without thinking about too much of it, let’s directly dive into it and begin this project.

In this particular project, we will follow step by step guide, in order to keep track of what next needs to be done. Fortunately in Android Studio, whatever we write as **TODO**: in the comment section is stored and you can keep a track in the entire project of yours. This feature can be handy when you need to create a set of to-dos in your workflow to achieve your task. Here’s the list of to-dos I will be executing by the end of this app. You’re free to add more in your own list.

## Todo List

<li>
<ol>Creating basic programming and UI architecture</ol>
<ol>Add a dark and awesome background.</ol>
<ol>Create Story class in second dart file.</ol>
<ol>Create StoryBrain class in third dart file.</ol>
<ol>Create your own story along with its flowchart.</ol>
<ol>Update the story in StoryBrain.dart file.</ol>
<ol>Put conditional if statements.</ol>
<ol>Run the program and enjoy</ol>
</li>

## Building the App

So before diving into basic structure and UI of the app design, we need to begin with an eye-catchy background. This background can be anything. You are free to use your own, but if you are an artist, like me you can try altering some already existing images to create your own kind of background. Once you’re all done with your background creation, now is the time to rename this image file as background. Also, make sure, your image **aspect ratio** must be 16:9. Since most of the commonly used android phones have that **aspect ratio** and so it will eliminate, unnecessary post-processing like stretching or tiling etc. In case you’re an iOS user, you may go for aspect ratio of 3:2 or something near to it.

![Boilerplate setup - Story book app on flutter](https://technopain.files.wordpress.com/2019/10/1-2.jpg)

The extension can be anything based on your file type, i.e. **.jpg, .png.jpeg** or **.bmp**. But in case you have control of file type, I will suggest **.png** format. Though Flutter has the flexibility to accept any of those formats, just a gut feeling always suggests me to use **.png** formats. Additionally, AppBrewery has also used the same. So yes, yet another strong reason to go for **png**!

So after doing some random edits on this image using Picasa editor, I made it something like this. I am not sure if it will look good to my app or not, but we have a choice to change it later if we don’t like it. So, for now, let’s go ahead with [this one](https://github.com/sedhha/FlutterStoryBook/blob/master/background.png).

No matter whichever be the programming language which you will choose any day for anything, you must have used OOP concepts to make some program in your all programming experience. I mean look at the simplicity it adds to our overall architecture of programming. Keeping this thing in mind, we have created 3 files along with the “main.dart” file. These are called “story.dart” and “story_brain.dart”. 

*Fast Forward to 3 years from then - OOP sucks, functional programming is the way to go!!!*

![Storybook App - Flutter main.dart file](https://technopain.files.wordpress.com/2019/10/2-1.jpg)

After you are done, adding image background and cloning the project files, let’s go ahead and proceed with the next steps.

### Basic Programming Syntax

Since now we are well aware of what we have to do. So let me add the first todo which is:

#### Creating Basic Programming Architecture

For this, we need to start programming by importing necessary packages.

Here we go:

```
import ‘package:flutter/material.dart’;
void main() => runApp(Destini());
```

The above two lines are very basic to understand we have started building our app with importing the necessary package and then declaring the app function which is supposed to be executed when we open the application. Now let’s move on further and define the app functionality.

![Storybook App - Code Snapshot - 04](https://technopain.files.wordpress.com/2019/10/3-1.jpg)

Now moving on to our second todo and that is to create a stateless widget which defines our app’s basic look and which remains the same throughout the operation. Hence we move forward with:

```
class Destini extends StatelessWidget {
    Widget build(BuildContext context) {
        return MaterialApp(
            theme: ThemeData.dark(),
            home: StoryPage(),
            );
        }
    }
```

Note that **extends keyword** in a dart programming language is nothing but a reference to inheritance. We inherit the properties of those classes which we tend to use frequently in our programs. Again creating a Widget function which will be the base building unit for all our application and will return the static stateless widget appearance we want it to give.

Here we don’t need to make any changes. Now let’s create a stateful widget or in simpler words, the dynamically updating UI part of our app.

```
class StoryPage extends StatefulWidget {
    _StoryPageState createState() => _StoryPageState();
    }
```

Note that by using _ at the beginning of the datatype, in dart we refer to it as a private variable. Now once we are done with inheriting staefulwidget, let’s go and create the appearance we want to give to our app. This is the tricky part and so be careful with everything we do next.

**Similar to This**: <a href="https://technopain.wordpress.com/2019/04/29/interfacing-matlab-with-raspberry-pi/" style="color:#AA4A44;">Setting up Matlab based Raspbian OS for raspberry pi</a>


Most of the code in the above statement is self-explanatory. Here the state property is being inherited and to enable the polymorphism, we are using line 2. From line 3 onwards, we are now concentrating on building our widget tree.

```
return Scaffold(
    body: Container(
        decoration: BoxDecoration(
            image: DecorationImage(
                image: AssetImage(‘images/background.png’),
                fit: BoxFit.cover,
                ),
            ),
```

Now we want a scaffold display having a simple container with a pretty background. You can use any of your own images, with the preferred aspect ratio of 16:9. From line 3-6, we are trying to implement the background of the widget we were creating.


![Storybook App - Code Snapshot - 05](https://technopain.files.wordpress.com/2019/10/5-1.jpg)

Once we are done with the background, now let’s perform the margining using **padding** and then place our two important buttons to help the user navigate through the story.

```
padding: EdgeInsets.symmetric(vertical: 50.0, horizontal: 15.0),
constraints: BoxConstraints.expand(),
```

The above padding is symmetric horizontal and vertical padding followed by the constraints we are looking for. Note that I will always suggest you experiment with these values and select the ones which fit the best with your background.

Since we want to always operate in the safe area and so we will start with `SafeArea ()` function.

```
child: SafeArea(
child: Column(
crossAxisAlignment: CrossAxisAlignment.stretch,
children: <Widget>[
```

Now we need to position our widgets vertically and so we will use columns instead of rows. In case you have other plans for rows, you are free to use that as well. Another way of customizing the axis is using crossAxisAlignment and then stretch the widgets within. Now since we are going to place multiple widgets within this, we will use children.

```
Expanded(
    flex: 12,
    child: Center(
        child: Text(
            style: TextStyle(
                fontSize: 25.0,
                ),
            ),
        ),
    ),
Expanded(
    flex: 2,
    child: FlatButton(
        onPressed: () {

        },
        color: Colors.red,
        child: Text(
            ‘Choice 1’,
            style: TextStyle(
                fontSize: 20.0,
                ),
            ),
        ),
    ),
SizedBox(
    height: 20.0,
    ),
Expanded(
    flex: 2,
    child: FlatButton(
        onPressed: () {},
        color: Colors.blue,
        child: Text(
            ‘Choice 2’,
            style: TextStyle(
                fontSize: 20.0,
                ),
            ),
        ),
    ),
],
```

From our previous flutter projects, I hope you must be well aware of how this code is working. This all is just basic syntaxing and placement of the dialogue boxes around the Screen. You can play with flex values to fix the elements accordingly to your picture.

**Similar to This**: <a href="https://technopain.wordpress.com/2019/05/19/numerical-computations-for-thermodynamics-of-real-gases/" style="color:#AA4A44;">Numerical Computations for Thermodynamics of Real Gases using Matlab</a>

Congrats! Finally, we are done with the basic coding. Now let’s focus on creating the actual hardcore storyline app.


#### Actual Story Line UI

Let’s first create our new class in “**story.dart**” file. You can right-click on the library go to new and then click dart file. Rename it as “**story.dart**” and then now let’s create our class here.

##### Story Class File

```
class Story {
    String _storyTitle;
    String _choice1;
    String _choice2;
    Story(this._storyTitle, this._choice1, this._choice2);
}
```

Now we have used the constructor to initialize our variables using **this**.

##### Story Brain Class File

Here we need to add some initial stories with respective choices. The choices and the story completely depends on you. And so you may make up a story and feed it like this:

```
import ‘story.dart’;
class StoryBrain {
    List<Story> _storyData = [
        Story(
            storyTitle: ‘Type your story here’’,
            choice1: ‘Choice 1 you want to give’,
            choice2: Choice 2 you want to give’
        ),
```

Now we need to initialize a function which could return us the storyTitle. Since we haven’t started with indexing we can just go for the first story as of now. This is done in the below piece of code:

```
String getStory() {
    return (_storyData[0].storyTitle);
}
```

Now let’s create a structure of StoryBrain and display this text in our main code with the existing text by calling this function. In the same fashion, we need to get the choices and so we will use the same syntax and create two new functions like that.

Now is the time to acquire story Number and hence we will create a double or an integer variable for the same. We will use a function called nextStory() to attain collect the choice number entered by the user. In case, the user makes the first choice we will send 1 as an argument to the function else we will send 2.

Since we are done with all the coding part, let’s create a decent storyline, which shouldn’t be long enough, as we may end up digging many new possibilities, but interesting enough as well. I am using my own storyline, you may use your own, or you can copy my storyline from this [link](https://github.com/sedhha/FlutterStoryBook/blob/master/storyline.txt).

![Flutter Storybook App - Code Snapshot - 06](https://technopain.files.wordpress.com/2019/10/6-1.jpg)


This is just a very simple story where your uncle’s friend tries to find and kill you. In the process of alarming and alerting you, your uncle dies. You’re freaked out what to do next about this and he is looking for you to get you and then murder you.

In this small story, he was a bullied up person during his school days and your uncle used to bully him with his friends. He always tried to be friends with your uncle but ended up failing every time. His life became total misery, when once your uncle totally drunk, killed his niece.

So here’s the flow chart of the storyline.

Red and blue options are the two choices you have while completing this murder mystery storyline. Try it out and let me know, how do you found my story? The text file has been already provided in the link above and you can download and paste it in your **Storybrain.dart** file.

Now once we are all done with this, let’s put all the **“if”** conditions to follow the above-shown flow chart and then we are ready to run our program!

For the final code go to my [GitHub repo](https://github.com/sedhha/FlutterStoryBook). For YouTube, tutorial follow this [link](https://youtu.be/HZrk7lkHJsI). A special thanks to [London App Brewery](https://github.com/londonappbrewery/destini-challenge-completed/) for the assist and help in building this app.

Cheers! I hope you are having a nice day.

**Similar to This**: <a href="https://technopain.wordpress.com/2019/07/08/making-a-fun-self-quiz-application-using-flutter-and-dart/" style="color:#AA4A44;">Making a Fun Self Quiz Application using Flutter and Dart</a>