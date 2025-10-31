# Project Update

1. What is your progress on the project? Do you have any updates you want to share with us?

    I have completed the initial frontend and backend foundations of the project. The backend is a REST API built with Django, and the frontend is a web interface developed using Next.js. An initial prototype is now ready for use. Codes can be found here: <https://github.com/hyn0027/HAII-project>. Detailed implementations are organized in the submodules.

2. Have you encountered any challenges? If yes, how are you going to address the challenges?

    Not yet.

3. If you received feedback (comments) for your project proposal, please let us know how you plan to address the comments. Are you going to make any changes to your project plan? If you did not receive comments, you can skip this question.

    > Feedback: This sounds very useful and functional. What is needed next is to think through more specifically who are the users and what are the specific tasks they need to accomplish. If this is too general-purpose, I don't see how it is different from existing general purpose models and if there is a need to make a separate reading helper.

    The users of this application are people who read technical articles (e.g., research papers, blog posts, or reports) but are not experts in the field. These users often need help understanding in-domain concepts and terminology.

    The main user goal is to comprehend the article effectively, supported by several subtasks:

        1. Quickly grasping the overall structure of the article.
        2. Understanding the core technical concepts.
        3. Accessing definitions, explanations, or related concepts for unfamiliar terms without interrupting their reading flow (i.e., without manually searching online).

    I think these specific user needs and tasks make this application different from general-purpose LLM. The design will emphasize contextual assistance and intuitive concept presentation. And given the non-technical background of the user, I think there are a lot of things we can do regarding how we design the interaction interface between human and AI.
