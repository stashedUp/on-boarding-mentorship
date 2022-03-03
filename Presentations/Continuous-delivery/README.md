READ FULL ARTICLE: https://warrensbox.medium.com/found-7-lost-principles-of-continuous-delivery-2125a3049d09   

1. Create a repeatable and reliable process for releasing software
Ask yourself, “How long would it take your organization to deploy a change that involves just one single line of code?”
We live in a world where shortened release cycles are a necessity. With agile development practices and continuous integration (CI), it is imperative for teams to have access to a stable tool which can manage the process of building, testing and deploying software as changes are made.
For a long time, Jenkins has been the tool of choice among developers, but as many companies have moved into the cloud, and in particular, AWS ecosystem, other tools such as Bamboo, AWS CodePipline, Go CD are gaining traction. The underlying purpose of these tools remains the same — to release your software.
Every change committed to source control triggers the creation of a new instance of the pipeline. We call this a release candidate. If the release candidate passes all the tests, it can be released.   

2. Automate, if possible, everything
Automation is a prerequisite for the deployment pipeline because it is only through automation that we can guarantee that people will get what they need at the push of the button.   


3. Keep everything under version control
Everything should be committed into source control, not just your software code. Version control isn’t all about having backups. That is only a side effect. Version control is about documenting and annotating the process of creation, and it is uniquely necessary for programming because of how eternally iterative programming is. Code that is not annotated with its history and its motivations suffers to an extreme degree of entropy, becoming more and more difficult to understand.   

4. If it hurts, do it more often — bring the pain forward
If testing is a painful process that occurs just before release, don’t do it at the end. Instead, do it continually from the beginning of the project. In the same way that your application and build scripts need testing, so do your configuration settings. Ensure that references to external services in your configuration settings are good.   

5. Keep the build and test process short
The longer the release cycle, the longer the development team has to make incorrect assumptions before the deployment occurs, and the longer it will take them to fix it.


6. Make every part of the process of building, deploying, testing and releasing software visible to everybody involved
Improve feedback so that problems are identified, and is resolved, as early as in the process as possible. Enable teams to deploy and release any version of their software to any environment at will through a fully automated process.   

7. Done Means Released
“Continuous is more often than you think” — Mike Roberts
Too often in software development, “done” doesn’t really mean “DONE!”. It doesn’t mean tested. It doesn’t necessarily mean styled. And it certainly doesn’t usually mean accepted by the product owner. It just means developed.    

