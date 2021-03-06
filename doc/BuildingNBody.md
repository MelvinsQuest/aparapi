#BuildingNBody
*How to build the NBody example. Updated Nov 11, 2011 by frost.g...@gmail.com*
##Building NBody
The NBody example is located in the/ examples subdirectory under the Aparapi trunk:

    trunk/
       ...
       examples/
         ...
         nbody/
            src/java/com.amd.aparapi.nbody/
            build.xml
            nbody.sh
            nbody.bat
The NBody example requires a little more work to build because it depends on a third party project named ‘JOGL’.

JOGL is a set of OpenGL™ bindings for Java® and the NBody example uses this library to render the particles/bodies (potentially many thousands of them) at runtime. More information about JOGL can be found here http://jogamp.org/jogl/www.

The build.xml file build target will download the jars required to build and run the nbody example if the files do not exist.

To build nbody, perform the following commands.

    C:> ant clean build
The NBody build.xml file includes a ‘run’ target so you can launch the application using.

    C:> ant run
Or if you prefer to launch from either the nbody.sh or nbody.bat script.

For Linux® we also need to chmod nbody.sh in order to execute it.

    chmod +x nbody.sh
The nbody scripts take the execution mode as the first argument, the number of bodies as the second argument, and then the height and width (in pixels).

Windows example:

    C:> nbody  GPU 32768 800 800
Linux example:

    $ ./nbody.sh  GPU 32768 800 800
Attribution