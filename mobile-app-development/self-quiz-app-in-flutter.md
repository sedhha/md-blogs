# Creating a Self Quiz App in Flutter

Hey Everyone! So here, I have just started learning the [basics of Flutter](https://www.udemy.com/course/flutter-bootcamp-with-dart), and it’s so much fun. The best part about Flutter is its simplicity and cross-platform build compatibility. That is it enables you to build your apps both in iOS as well as android devices just using one single code. This blog is mainly about short and precise tutorial as well as flutter review based on my opinion.

So this flutter tutorial is all about how to make a simple quiz app with two options, which can easily be extended using widgets, rows and columns as per your visual preference.

![Self Quiz App - Snapshot - 01 - Flutter Programming](https://technopain.files.wordpress.com/2019/10/1.jpg)

The basic UI design has been implemented using the source code given in [LondonAppBrewry’s Github repo](https://github.com/londonappbrewery/Flutter-Course-Resources). There are small modifications performed to have custom options instead of just “True ” and “False”.

So Let’s start our tutorial.

**Similar to This**: <a href="https://technopain.wordpress.com/2019/04/29/interfacing-matlab-with-raspberry-pi/" style="color:#AA4A44;">Setting up Matlab based Raspbian OS for raspberry pi</a>

## Dart Programming Language

Dart Programming Language is so easy to grasp. Google has done an outstanding job in building this programming language. Its syntax is very much similar to C/C++ or Java programming language, with the added simplicity of Python programming language.

Here I have used lists to optimize and present the options. Though I haven’t made changes in the option colours as red and green already looked classy enough with the background.

You can easily do that by editing the code in line 101, which says:

`color: Colors.green`

Similarly to change the colour of the other box, you can go to line 143 and accordingly do the alterations. Another fabulous part about android studio is that it allows you to view all the possible options. You can scroll down and see most of the available colours with their codes and titles as well.
So good luck with selecting a great background and foreground for your app!

Let’s go directly to the core concepts of programming, and see how things are happening in this program. If you already have some programming experience, understanding the basic logic of this program will be quite easy for you.


![Self Quiz App - Snapshot - 01 - Flutter Programming Hot Reload](https://technopain.files.wordpress.com/2019/10/7.jpg)

Let’s go directly to the core concepts of programming and see how things are happening in this program. If you already have some programming experience, understanding the underlying logic of this program will be quite easy for you. Things which are essential to discuss according to me may or may not be totally relevant to you. So in case if I miss something which you wanted me to mention out or go a bit more in-depth, let me know down in the comments.


The fundamental points of this program are:

- *Flutter List and List Syntax*
- *If Else Statement and Counter Operation*
- *Count Incrementation Logic*
- *SetState function*
- *Index Bound check*

So one by one, let’s discuss and explore this topic further.

## Flutter List and List Syntax

Flutter List syntax follows a very similar syntax declaration to Python programming language. First, you start with variable-type and then name and then assignment operator followed by two square braces and a semicolon. Note that a list allows us to store variables of multiple datatypes. And so the general syntax of a list in flutter is:

`list listname=[];`

This particular type of list will allow me to store variables such as:

```
‘Shivam’
34
23.423
‘a’
```

and so on. But to avoid any unnecessary programming complexities, we just specify the list with a specific datatype which we want to store into it.

![Self Quiz App - Snapshot - 01 - Flutter Programming Android Studio Emulator](https://technopain.files.wordpress.com/2019/10/5.jpg)

Here for the first list, which contains the message that is to be displayed on the screen, is in the form of string. So we will specify it as string datatype. The syntax is as follows:

`List<String> questions = [];`

Notice that this type of variable specification is very similar to typecasting in c or c++.

![Self Quiz App - Snapshot - 05 - Flutter Programming List of String](https://technopain.files.wordpress.com/2019/10/3.jpg)

Anyways moving forward, here you can add all the texts, you want to be displayed on your screen as questions and instructions in sequence. Because we are displaying them sequentially in our dart program.

In a similar way, we have many similar strings to store various other data types which include:

**options** (List of options which you want to display in the first Flat button)

**optional** (List of options which you want to display in the second Flat button)

![Self Quiz App - Snapshot - 04 - Flutter Programming Android Studio Emulator](https://technopain.files.wordpress.com/2019/10/2.jpg)

answers (in integer form, note that answers could be in boolean form too, as there are only two options. But since I am using number two to identify if we have reached the end and so I have used here int. This identification is done to clear all the check or cross marks at the end of the quiz. Though there are several other methods to do this, this is what I preferred the most.)

## If else statement and counter operations

As the user presses a button, we need to ensure that according to their answer, we have to record their observations and accordingly display whether they are right or wrong. For all the questions, answers have been stored in form of int variables. The first green box refers to one while the second red box refers to zero. And the list **answers**, has been accordingly stored as per the question.

![Self Quiz App - Snapshot - 06 - Flutter Programming Android Studio Emulator](https://technopain.files.wordpress.com/2019/10/4.jpg)

For example:

My name is:

Shivam

Shubham

So **“My name is”** is stored in the list questions,

**“Shivam”** is stored in options,

**“Shubham”** is stored in optional,

and finally, **1** is stored in answer.

**Similar to This**: <a href="https://technopain.wordpress.com/2019/07/31/my-storybook-app-in-flutter/" style="color:#AA4A44;">My StoryBook App in Flutter</a>

Since 1 refers to the first flat button (i.e. Shivam) and so if the user presses the first flat button, “correct” variable which is again an integer data type, will be incremented. In the other case, incorrect will be incremented. This will go on for all the 10 questions (you can add more if you want), matching the answers and assigning the scores.

In the end, the final score percentage which will be:

```
(correct/10)*100
```

is evaluated and added to the question using the syntax:

```
questions.add(‘You know Shivam ‘ +
(correct * 10).toString() +
‘%.’);
```

is displayed along with the other necessary messages.

![Self Quiz App - Snapshot - 07 - Flutter Programming Android Studio Emulator](https://technopain.files.wordpress.com/2019/10/6-e1570947367484.jpg)

### Count Increase Logic and Index Bounding

Once the counter reaches this part, we have to ensure that it doesn’t go beyond and so we use another if condition to bring it back to that same last position instead of incrementing.

```
if (count >= questions.length – 1) {
scoreKeeper = [];
count = questions.length – 1;
if (questions.length != options.length)
questions.add(‘You know Shivam ‘ +
(correct * 10).toString() +
‘%.’);
```

So this was all about if-else and evaluation algorithms.

### setState function

```
onPressed: () {
    setState(() {
        if (answers[count] == 1) {
            scoreKeeper.add(Icon(
                Icons.check,
                color: Colors.green,
            )
        );
        correct++;
    } else if (answers[count] == 0) {
        scoreKeeper.add(Icon(
            Icons.close,
            color: Colors.red,
            )
        );
        incorrect++;
        }
        count += 1;
    
    if (count >= questions.length – 1) {
        scoreKeeper = [];
        count = questions.length – 1;
        if (questions.length != options.length)
        questions.add(‘You know Shivam ‘ + (correct * 10).toString() +‘%.’);
        }
    }
    );
}
```

Here onpressed is the function which triggers the pressing action and then processing takes place. So this was all about how we made a very little simple decent looking self-quiz app on flutter. Later on, you can expand this and modify into any kind of quiz app. I am totally new to Flutter, but I love to share what all I learn.

![Self Quiz App - Snapshot - 07 - Flutter Programming Android Studio Emulator](https://technopain.files.wordpress.com/2019/10/8.jpg)

Let me know in the comments if you have any suggestions or ideas to make this app even better. In case you have any doubts, all your questions are appreciated. For the entire code, visit my [Github repo](https://github.com/sedhha/quizShivam/blob/master/main.dart).

Cheers! Hope you are having a good day.

 

For a demo, you may check out my [youtube video](https://youtu.be/7hRKAO4gY_k).