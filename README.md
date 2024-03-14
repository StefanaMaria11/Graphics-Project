1.	Subject specification
   
	The subject of this project is the photorealistic presentation of 3D objects using OpenGL library. Open Graphics Library is a specification of a standard which defines a multiplatform API, widely used for programming the 2D and 3D components of computer programs.
	The scene I chose to implement is a small medieval kingdom, that has a fortress, knights, dragons and other beings. The user manipulates the object scene directly by entering the mouse and keyboard and can move around it.

3.	Scenario
   
a.  Scene and object description
	The scene showcases a small medieval fortress with two dragons and a group of knights approaching on a road, appearing ready for an attack. Inside the fortress, there's a king, an elf lady, and several buildings, guarded by additional knights. The broader map also features nature elements, including a deer.

b. Functionalities
	The user can have a visualization of the entire scene by pressing the keyboard keys or the mouse. One can also switch between solid view and wireframe or polygonal and smooth face using keyboard keys. Fog also appears or disappear by the choice of the user. Its intensity can be increased or decreased.
	There are multiple sources of light: directional light, the point light. Also the object that projects the point light can be moved by pressing the corresponding keyboards.

3.	Implementation details
   
	a.  Functions and special algorithms
		i. Possible solutions

OpenGL library consists in a large variety of functions such as:

•	glViewport(…) used for setting Viewport transform

•	glfwCreateWindow(…) used for creating the window

•	glGenTextures(…)

•	glBindTexture(…)

•	glTextImage2D(…) used for creating depth texture for the Framebuffer objects

•	many others.
	One of the functions I’ve used in this project is void renderScene() which is the function used to send all the data to the shaders and compute all the values. Here is where all the models and their shadows are created, where the normal matrix are computed and where the rotation, translation and scaling are done.
	Another function is void initUniforms(), where the lights’ details are all set – the point light, the directional light and the spotlight.
 
	The function void initShaders() is a function where the shaders are instantiated.
 
	The function void initModels() is a function where all the 3D Models are instantiated.
 
	Another important functions are:
 
•	void processMovement()
•	void move(gps::MOVE_DIRECTION direction, float speed)
•	void mouseCallback(GLFWwindow* window, double xpos, double ypos)
•	void keyboardCallback(GLFWwindow* window, int key, int scancode, int action, int mode)
	These functions perform all the necessary changes on the models or on the camera so that they perform the moves desired by the user.
		ii. The motivation of the chosen approach
	In the laboratories dedicated to this subject we have learnt how to compute light, shadows, to perform operations of translation, scaling and rotation on different objects. Having this starting point and also a skeleton of the project, the work I had to do in carrying out this project had a fairly well-defined path.
 
	b. Graphics model
 
	Objects and textures have been downloaded from the internet. Most objects were imported into the Blender to be edited and placed in the final scene.
	This part seemed to me quite difficult, because some textures were not displayed on the object or, moreover, the object was not displayed. Therefore, I had a longer search for objects/textures.
	However, I consider this to be the creative and enjoyable part.

	c. Data structures

	The only data structures required were some simple ones, to hold together all the attributes of the different types of light, as for spot light and point light. They have already been implemented in the project provided to the laboratory, so it was quite useful to have it. In addition, I added some functions to calculate the lights and fog.

	d. Class hierarchy

•	Camera: contains the implementation for camera movement (up, down, front, back, left, right)
•	SkyBox: contains skybox implementation (load, draw, load textures, initialize)
•	Mesh: represents a 3D object; includes the following data structures:
•	Vertex (position, normal vector and texture coordinates)
•	Texture (id, type and path); Material
•	Model3D: contains methods for printing meshes using a specified shader program
•	Shader: contains methods for creating and activating shader programs





4.	User manual

	The user can interact with the scene using the following keys on the keyboard:

•	I - start the preview of the scene

•	U - stop the preview

•	V and B - move the light cube

•	F - modify intensity of the fog

•	K - show wireframe view

•	L - show solid view

•	M - show point view

•	Q - rotate camera to left

•	E - rotate camera to right

•	W - move camera to the front

•	S - move camera backwards

•	A - move camera to left

•	D - move camera to right
