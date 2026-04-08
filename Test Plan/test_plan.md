To test the Realtorial system, we will use a combination of unit and integration tests. These will not only ensure the system functions properly but will also validate the useability of the system based on human feedback. System testing will encompass the ability to input tutorial description data, converting the descriptions into the necessary UI components, enabling the front-end on the head-mounted display (HMD) to communicate with the backend ML model, and displaying interactions the user must perform with the real-world items. From the user-experience perspective, having various UI elements be reachable in the world with intuitive interactions and having the tutorial pace be followable for a lay user is very important. 

Many elements of the test plan will need to be tested by hand given the human-centric nature of the project. Button-pressing, object locomotion, etc. are examples where this is true. Lower-level system tests such as backend-frontend communication, ML model inference/metrics, etc. will be testable with automatic unit/integration tests, speeding validation in these areas. 

Test Case Descriptions 

### IC1.1 	Input Console 1 – App Launching 

IC1.2 	The purpose of this test is to establish a functional UI for user input. 

IC1.3 	This test will establish that there is a console that the user can use to select a 	certain tutorial. 

IC1.4	Inputs: Our inputs will be the activation of the console through the HMD’s OS 

IC1.5	Outputs: The output will be the console displaying the tutorials we would have 	stored 	in the program  

IC1.6	Normal 

IC1.7	Blackbox 

IC1.8	Functional 

IC1.9	Unit test 

 

### IC2.1 	Input Console 2 – Tutorial Specification and Description 

IC2.2 	To have multiple tutorials available to users, the ability to input a specification of a 	given tutorial is required. 

IC2.3 	The tutorial specification “parser” (from YAML) will be tested, ensuring that the 	proper information (objects, interactions, etc.) is extracted. 

IC2.4	Inputs: Valid and invalid specification files. 

IC2.5 	Outputs: An in-memory data structure that contains all the information from the 	input. 

IC2.6	Both 

IC2.7	Blackbox 

IC2.8	Functional 

IC2.9	Unit test 

 

### IC3.1	Input Console 3 – Tutorial Step 

IC3.2	The purpose of this test is to establish a working functionality that will continue the 	progression of a tutorial or to stop one when it concludes. 

IC3.3	This test will establish a button input to navigate through tutorials and let them play 	out and to conclude them when they are done 

IC3.4	Inputs: Button input to progress tutorials 

IC3.5	Outputs: Progression or conclusion of a tutorial. 

IC3.6	Normal 

IC3.7	Blackbox 

IC3.8	Functional 

IC3.9	Unit test  

 

 

### G1.1 	GUI 1 - Step Overview Display 1 

G1.2	The purpose of this test is to ensure that an “overview” graphic is generated for 	each step of a tutorial. 

G1.3	This test will be successful when information from a tutorial step, including the 	object(s) it requires, the interaction the user must make with it(them), a picture of 	the objects(s). 

G1.4	Inputs: A loaded tutorial session 

G1.5	Outputs: The populated overview being displayed to the user 

G1.6	Normal 

G1.7	Blackbox 

G1.8	Functional 

G1.9	Integration 

 

### G2.1 	GUI 2 – Object Segmentation 2 

G2.2	Test that objects required for a tutorial step are properly segmented for localization 	of them by the user. 

G2.3	This test will ensure that object segmentation masks are properly localized in the 	world and are colored to match the object category. 

G2.4	Inputs: a segmentation mask specification object. 

G2.5	Outputs: Coordinates, colors, etc. that define the placement and type of object. 

G2.6	Normal 

G2.7	Blackbox 

G2.8	Functional 

G2.9	Unit 

 

### G3.1 	GUI 3 – Object Interaction Markers 

G3.2	Test that object interaction markers are placed into the scene to represent 		transformations, grabs, rotations, etc. 

G3.3	This test will check that interaction markers are placed in the right location and 	have the correct orientation, rotation, grab points, etc. such that following them 	leads to completion of the task. 

G3.4	Inputs: An object interaction specification. 

G3.5	Outputs: Coordinates and the 3D object (arrow, point, etc.) that represents the 	interaction. 

G3.6	Both 

G3.7	Blackbox 

G3.8	Functional 

G3.9	Unit 

 

 

 

### FC1.1	Framework Communication 1 

FC1.2	The purpose of this test is to determine if there is communication between the front 	end and back end of the software. 

FC1.3	This task will be a success when we are able to create a link between the front end 	and back end and see this communication 

FC1.4	Input: PUT requests filled with json data sent to the back end 

FC1.5 	Output: PUT request is stored in the back end and able to be retrieved. 

FC1.6	Normal 

FC1.7	Whitebox 

FC1.8	Functional 

FC1.9	Integration 

 

### FC2.1	Framework Communication 2 

FC2.2	The purpose of this test is to determine if the front end can retrieve and load data 	from the back end and display it properly. 

FC2.3	With the use of GET requests, we will retrieve data from the back end to display for 	the user. 

FC2.4	Input: GET request to the back end to retrieve json data. 

FC2.5	Output: Data pulled from the GET request is retrieved and displayed correctly for 	the user. 

FC2.6	Normal 

FC2.7	Whitebox 

FC2.8	Functional 

FC2.9	Integration 

 

 

### ML1.1	ML 1 - Inference 

ML1.2 	This test seeks to ensure that ML model inference occurs as expected. 

ML1.3	This test operates by pushing imagery through the model and generating metrics 	that convey the model’s accuracy. 

ML1.4	Inputs: Example imagery from the HMD’s cameras. 

ML1.5	Outputs: Segmentation masks and metrics computed on annotated imagery. 

ML1.6	Both 

ML1.7	Whitebox 

ML1.8	Functional 

ML1.9	Unit 

 

 

### D1.1	Deployment 1 - HMD Deployment 

D1.2	This test will ensure that Unity applications can be deployed to the HMD. 

D1.3	Being able to deploy the application to the HMD and have it accessible to the user is 	a successful running of this test. 

D1.4	Inputs: The Unity application on a computer. 

D1.5	Outputs: An application on the HMD that the user can run. 

D1.6	Normal 

D1.7	Blackbox 

D1.8	Functional 

 

### Test Case Matrix 
|  | Normal/Abnormal | Blackbox/Whitebox | Functional/ Performance | Unit/Integration | Results |
| --- | --- | --- | --- | --- | --- |
| IC1 | Normal | Blackbox | Functional | Unit | Passed |
| IC2 | Both | Blackbox | Functional | Unit | Passed |
| IC3 | Normal | Blackbox | Functional | Unit | Passed |
| G1 | Normal | Blackbox | Functional | Integration | Passed |
| G2 | Both | Blackbox | Functional | Unit | Passed |
| G3 | Both | Blackbox | Functional | Unit | Passed |
| FC1 | Normal | Whitebox | Functional | Integration | Passed |
| FC2 | Normal | Whitebox | Functional | Integration | Passed |
| ML1 | Both | Whitebox | Functional | Unit | Passed |
| D1 | Normal | Blackbox | Functional | Unit | Passed |