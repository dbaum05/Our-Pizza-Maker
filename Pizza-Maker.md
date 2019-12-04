




# Pizza Maker
 
![image_example1][image1]
 
`Dylan`, _Jorge_, and *Jake* 
 
[//]: # (Image References)

[image1]: https://github.com/dbaum05/Our-Pizza-Maker/blob/master/WIN_20191202_08_59_36_Pro.jpg "image_example1"
[image2]: https://github.com/userName/JHS-Elevator-Assignment/blob/master/images/image_example2.JPG "image_example2"
[image3]: https://github.com/userName/JHS-Elevator-Assignment/blob/master/images/image_example3.JPG "image_example3"

## Design constraints: 
1.	Mus be able to make 3 pizzas (cheese, peperoni, and sausage) in the same amount of time per pizza. 
2.	Must be able to be put direcly in line with their packaging machines. 
3.	Must have indicators so that the customer can see where the pizza is in the making process. 
4.	The design and prototype implementation must be completed using fischertechnik components and the ROBOPro programming software.
5.	Comments in the code should communicate each function's intended purpose clearly.
6.	The final write up is professional with descriptive pictures of your elevator prototype and program.
7.	A final video is provided (which can easily be linked through the use of a markdown (.md) file). 
o	The writeuptemplate.md file in the repository, can be used to fulfill requirements 3 & 4.
8.	The final submission will be a link to your GitHub repository for this project, so please maintain a professional digital environment.
9.	While successful completion of the project means that the design constraints found in the Design Brief are met, A+ work will be awarded to projects that show creativity in meeting these objectives.
 
### Design
Three modules like the one pictured below were used to dispense the toppings (cheese, peperoni, and sausage) onto the pizzas. They were opened by a timed motor wired to M2, M3, and M4. They would then close until a switch wired to I4, I5, or I6 were activated. (all in respective order). The motors were wired to a light in parallel so that the customer could see where the pizza was. 
 
The pizza was moved along under the dispensers and oven by a conveyor belt. The motor did not apply enough torque to power such a long track, so a custom gearbox was used. It is a standard motor gearbox attached on its axis to a screw gear. This is then attached to a larger wheel, which is attached on the same axis to the gears that spin the track. This motor was wired to O1. 
 

The pizza was baked by six lights at the end of the conveyor. They were wired in parallel to the O2 port. After this the pizza would be dispensed into the packaging machine and allowed to sit for a second to cool, or it could be served hot (like good pizza should be). 
 
Here is a picture of the whole controller board. It contains all the connected wires, and was connected directly to the side of the machine. It was on the opposite side of the selector stitches to create a clean front. 
 
	Three switches were located on the front of the machine that allowed the operator to select what pizza they wanted to make. They could select cheese, peperoni, or sausage and were wired to the I1, I2, and I3 slots. 
 

Code 
 








There are three switches that allow the user to select what pizza to make. They all flow into the cheese control group after pushed, but that peperoni and sausage (I2 and I3) change their respective variables to 1 which later tells the program to apply the topping.  
The program starts running the conveyor motor (O1) after any of the buttons are pressed. 
 
There is then a time delay, and then the code for the cheese toppings to be applied. All of the timing circuits were determined through trial and error, and these may need to be adjusted per each machine if tolerances are not tight. 
 
	Once the cheese circuit is completed, the machine checks for the peperoni and sausage variables to determine if it needs to apply those toppings. If not, it flows into a delay which flows into the baking portion of the program 
 



If one of these (and only one at a time will work) is selected, the program follows this topping route. They are the same as the cheese, only the timings are different and there is a timing applied at the end to make sure that they all enter the oven at the same time. They also reset the topping variable that was activated to 0. 
 
After this, the program starts the baking element, which is wired to O2, and this is turned on and off based on a timed system. After this is completed, the oven and the conveyor are turned off and the program again checks for a pizza to be selected. 
 

