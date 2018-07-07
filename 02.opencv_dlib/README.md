Adding on to OpenCV in 01. , will be using opensource dlib library to find facial landmarks and a few other features.

Using a 68 point facial landmark detector. You can use a 5 point facial landmark detector also which is faster (by 8-10%), more efficient, and smaller (by a factor of 10x).

For the 68 point facial landmark detector:

    Points 0 to 16 is the Jawline
    Points 17 to 21 is the Right Eyebrow
    Points 22 to 26 is the Left Eyebrow
    Points 27 to 35 is the Nose
    Points 36 to 41 is the Right Eye
    Points 42 to 47 is the Left Eye
    Points 48 to 60 is Outline of the Mouth
    Points 61 to 67 is the Inner line of the Mouth

For Head Pos Estimation , using simple 3D locations of a few points in some arbitrary reference frame ( a.k.a Model Coordinates in OpenCV docs ):

    Tip of the nose : ( 0.0, 0.0, 0.0)
    Chin : ( 0.0, -330.0, -65.0)
    Left corner of the left eye : (-225.0f, 170.0f, -135.0)
    Right corner of the right eye : ( 225.0, 170.0, -135.0)
    Left corner of the mouth : (-150.0, -150.0, -125.0)
    Right corner of the mouth : (150.0, -150.0, -125.0)



3D ref points(world coordinates), model referenced from http://aifi.isr.uc.pt/Downloads/OpenGL/glAnthropometric3DModel.cpp:

    (6.825897, 6.760612, 4.402142)      33 left brow left corner
    (1.330353, 7.122144, 6.903745)      29 left brow right corner
    (-1.330353, 7.122144, 6.903745)     34 right brow left corner
    (-6.825897, 6.760612, 4.402142)     38 right brow right corner
    (5.311432, 5.485328, 3.987654)      13 left eye left corner
    (1.789930, 5.393625, 4.413414)      17 left eye right corner
    (-1.789930, 5.393625, 4.413414)     25 right eye left corner
    (-5.311432, 5.485328, 3.987654)     21 right eye right corner
    (2.005628, 1.409845, 6.165652)      55 nose left corner
    (-2.005628, 1.409845, 6.165652)     49 nose right corner
    (2.774015, -2.080775, 5.048531)     43 mouth left corner
    (-2.774015, -2.080775, 5.048531)    39 mouth right corner
    (0.000000, -3.116408, 6.097667)     45 mouth central bottom corner
    (0.000000, -7.415691, 4.070434)     6 chin corner



In OpenCV the function ```solvePnP``` and ```solvePnPRansac``` can be used to estimate pose. ```solvePnP``` implements several algorithms for pose estimation which can be selected using the parameter flag. By default it uses the flag SOLVEPNP_ITERATIVE which is essentially the Direct Linear Transform solution followed by Levenberg-Marquardt optimization.

