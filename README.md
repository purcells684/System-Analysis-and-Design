System Analysis & Design
Briefly summarize the DriverPass project. Who was the client? What type of system did they want you to design?

The DriverPass project was commissioned by the client, Stan U. Purcell, to modernize the driving lesson experience. The objective was to design a cloud-native, automated driving school scheduling and management system. The platform automates student registrations, coordinates real-time calendar slot bookings, processes secure card payments, and generates business growth analytics reports.

What did you do particularly well?

The design excelled at establishing clear, rigid role boundaries and data workflows for each actor type. By cleanly translating structural system limitations (like requiring constant internet access and strict relational metrics) into functional platform designs, the architecture guarantees data integrity and bank-level isolation across different layers. The accompanying sequence and class models accurately mirror this clean division of security boundaries.

If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I would choose to revise the UML Activity Diagrams. Currently, the process lifecycles are modeled as simple, linear end-to-end chains without any conditional branching or error-handling paths. To improve them, I would add decision diamonds and alternative paths to account for real-world scenarios—such as a student's card being declined by the payment gateway or an instructor's chosen slot conflicting with an existing booking.

How did you interpret the user’s needs and implement them into your system design? Why is it so important to consider the user’s needs when designing?

The user's needs were explicitly broken down into structural boundaries matching three precise personas: Students, Instructors, and Administrators. For example, the student's need for instant confirmation was addressed through a real-time validation database query loop in the sequence logic. Considering user needs is critical because a system with flawless technical architecture is ultimately a failure if it features poor usability, violates user workflows, or lacks the intuitive accessibility required for everyday operations.

How do you approach designing software? What techniques or strategies would you use in the future to analyze and design a system?

My design approach begins by gathering raw business logic, separating functional features from nonfunctional baseline limitations, and mapping out user roles. In future projects, I would integrate Agile user story mapping alongside UML diagrams to capture smaller, iterative user journeys. Additionally, utilizing robust prototyping tools and threat-modeling frameworks early in the wireframing phase ensures security boundaries are verified long before structural development begins.
