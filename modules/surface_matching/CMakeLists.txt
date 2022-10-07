set(the_description "3D point features")
ocv_define_module(surface_matching opencv_core opencv_flann WRAP python)

if(APPLE AND HAVE_OPENMP)
    # OpenMP is probably installed externally, eg. using 'brew install libomp'.
    # Then, the flags set in OpenCVFindFrameworks.cmake are not enough.
    # The proper way in CMake 3.12+ is to do this:
    ocv_target_link_libraries(${the_module} PRIVATE OpenMP::OpenMP_CXX)
endif()