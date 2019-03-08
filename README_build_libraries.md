Download those libraries:
cd
sudo apt-get install p7zip-full

# Download and unpack the latest JogAmp release
wget http://jogamp.org/deployment/jogamp-current/archive/jogamp-all-platforms.7z
7z x jogamp-all-platforms.7z


clone this:
git clone https://github.com/hharrison/java3d-core/commit/68c2395b3098f374973e66ca962a0bde929e0a1d
mkdir j3d
cd j3d
git clone git://github.com/hharrison/vecmath
git clone git://github.com/hharrison/java3d-core j3d-core
git clone git://github.com/hharrison/java3d-utils j3d-utils
mkdir jogl-v2.3.1
curl http://jogamp.org/deployment/v2.3.1/jar/gluegen-rt.jar > jogl-v2.3.1/gluegen-rt.jar
curl http://jogamp.org/deployment/v2.3.1/jar/jogl-all.jar > jogl-v2.3.1/jogl-all.jar
cd vecmath
ant

Copy gluegen-rt.jar and jogl-all.jar in ~/j3d/jogl-v2.3.1. Change the build.xml:

  <property name="jogl.lib"          location="../jogl-v2.3.1/jogl-all.jar"/>
  <property name="gluegen.lib"       location="../jogl-v2.3.1/gluegen-rt.jar"/>
cd j3d/j3d-core