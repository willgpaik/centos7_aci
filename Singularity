BootStrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/$basearch/
Include: yum
%setup

%files

%environment
PATH="$PATH:/usr/lib64/openmpi/bin/"
LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/lib64/openmpi/lib/"
export PATH
export LD_LIBRARY_PATH

%runscript

%post
    # commands to be executed inside container during bootstrap
    # add python and install some packages
    yum -y update
    yum -y install epel-release \
      terminator \
      centos-release-scl
    yum -y install vte-devel \
      vte291-devel \
      vte-profile \
      devtoolset-8-gcc*
    yum -y groups install "Development Tools"
    yum -y groups install "Base"
    yum -y install git cmake gcc-c++ gcc binutils \
      libX11-devel libXpm-devel libXft-devel libXext-devel \
      gcc-gfortran openssl-devel pcre-devel \
      mesa-libGL-devel mesa-libGLU-devel glew-devel ftgl-devel mysql-devel \
      fftw-devel cfitsio-devel graphviz-devel \
      avahi-compat-libdns_sd-devel libldap-dev python-devel python36-devel \
      libxml2-devel gsl-devel \
      openmpi-devel \
      cmake3 \
      hdf5-devel \
      patch \
      qt5-qtbase-devel \
      qt5-qtsvg-devel \
      g++ numpy eigen3-devel zlib-devel libqt4-devel libtiff-devel \
      bzip2 ca-certificates \
      libglib2.0-0 libxext6 libsm6 libxrender1 \
      mercurial subversion \
      mesa-libGLU-devel.i686 \
      mesa-libGL-devel.i686 \
      libcanberra-gtk* \
      boost-devel \
      autoconf 
      
    yum -y update
   
    mkdir -p /storage/home
    mkdir -p /storage/work
    mkdir -p /gpfs/scratch
    mkdir -p /gpfs/group
    mkdir -p /var/spool/torque
    
    # Make symlinks
    ln -s `which qmake-qt5` /usr/local/bin/qmake
    ln -s `which moc-qt5` /usr/local/bin/moc
    ln -s `which rcc-qt5` /usr/local/bin/rcc
    ln -s `which vim` /usr/local/bin/vi
