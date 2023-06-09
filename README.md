# Hospital-shift-mgmt-LLD

This project was created to understand the <b>builder design pattern</b>.


## Builder Pattern
A builder class is a type of object that is responsible for creating complex objects by breaking down the creation process into smaller, more manageable steps.<br>
The builder pattern is used when we need to create objects that have several optional or mandatory parameters that need to be set during object creation.<br>
Instead of having a complex constructor with many params, we use the builder pattern to create an object step by step.<br>
The builder class returns the fully constructed object to the client when all the necessary parameters have been specified.


<b>Client</b> : Chief of Staff at a hospital.
<br>
What does he want to know : To get a list of doctors and nurses on duty with the number of hours they have worked.
<br>
What does he want to do : To make them attend trainings and surgeries.


### Classes Used
1. Staff - This class is the one that needs to be directed by the Chief of Staff. A staff has certain attributes like job "startTime", job "endTime", "floorNo" of work, what is their work "timeLimit" and a "staffList" of all the docs and nurses on duty.
2. StaffBuilder - This class helps in setting the attributes of the Staff class by building the object step by step and finally passing the instance to the constructor of staff class to set the required values.
3. DoctorBuilder, NurseBuilder - These are child classes of the StaffBuilder and them implement the abstracted "setStaffList()" method. This method is there to add the list of docs and nurses and their current working hours. This is hardcoded right now.
4. StaffDirector - A director class is needed because the Chief of Staff doesn't know what attributes of Staff to set. He has other work and he just wants to call a method called getStaff() based on his choice of Doctor or Nurse. So the director is the one that sets the required values. Chief of Staff can obviously override and directly do that if he wants to.
5. ClientChiefStaff - This is the client class where the client wants to just get the list of staff, make them go do training or surgery.