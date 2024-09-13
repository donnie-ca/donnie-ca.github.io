---
layout: essay
type: essay
title: "Smart and Not-so-Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2024-09-12
published: true
labels:
  - Software Engineering
  - Learning
---

## Why are smart questions important?

One of the most important skills for software engineers to develop is communication, and being able to ask smart questions is essential. A smart question means the question is written in clear, grammatical, correctly spelled language, is precise and informative, and is explicit in what the problem is. These kinds of questions help identify potential issues early and ensures that the engineer is aligned on the goals and objectives of the project. Not-smart questions lead to your time wasted, others' time wasted, and nothing learned. Ultimately, the ability to ask the right questions not only saves time and resources but also leads to more innovative and high quality software development outcomes. 

## The smart question

To showcase an example of asking a smart question, here is a StackOverflow question asked 12 months ago titled [thread_local + std::thread deadlock on destruction](https://stackoverflow.com/questions/77126448/thread-local-stdthread-deadlock-on-destruction). The page contains the following:
```
Anyone knows what kind of UB is this? The following code deadlocks on jthread destruction when built with MSVC 19.29.30148, sometimes it deadlocks after std::cout and sometimes before. This is somehow related to thread_local, but I cannot see what is the issue. It seems to work fine under other compilers and platforms.

#include <thread>
#include <memory>
#include <iostream>

int main(void)
{
    std::thread t2(
        [&] {
            thread_local std::jthread asd([] {
                    std::cout << "ASD" << std::endl;
                    });
        });
    if (t2.joinable()) { t2.join(); }
}
Update: Reproducible both on static and dynamic runtime
```
This post checks many of the boxes in the guidelines provided by Eric Raymond. First of all, they used a concise and meaningful header that lets the reader know exactly what kind of problem this is. Additionally, the author of the post did not put in huge blocks of code, but instead took only the code surrounding the error and describes all relevent information regarding the problem such as where the code is deadlocking, informing that the problem is related to thread_local, and saying that the code works with other compilers and platforms. This led to multiple knowledgable engineers being able to quickly identify the problem and provide multiple tips that might fix the issue.

## The not-so-smart question

To demonstrate an example of a not-so-smart question, here is an example that a StackOverflow user provided titled [Remove Alphanumeric string and following character from end of the string in power BI](https://stackoverflow.com/questions/78981017/remove-alphanumeric-string-and-following-character-from-end-of-the-string-in-pow). The page contains the following:
```
I want to remove alphanumeric string and all the following characters from the end of a string in column in power bi

example 1: Input /Chill/chill/batch/design/961057df-7a86-4159-a532-f6919175f478/version

Output /Chill/chill/batch/design

example 2: Input /Chill/chill/batch/design/961057df-7a86-4159-a532-f6919175f478

Output /Chill/chill/batch/design
```
There are many glaring problems in this question just by taking a glance at it. To start, the header is very vague and does not describe any specific issues, but rather just tells the readers what the overall project is. In the main body of the post, the author unneccesarily restates the title and then states the desired output for specific inputs. A better way of asking this question would be to attempt to solve the problem by themselves, identifying any issues or bugs, and then posting the symptoms of the errors and providing the code to StackOverflow. In this question, there was no code or bugs provided, and it seemed more like a "homework question" than anything else.

##Conclusion

As a result of this experience, I was able to differentiate between asking questions the smart way and the not-smart way. Analyzing these two different types of questions in depth helped me understand the little things that make big differences in the quality of a question. Now that I know the aspects required for a smart and meaningful inquiry, I will be able to utilize this knowledge to get more value out of the questions I ask, whether it be in person or through an online forum like StackOVerflow. 
