LINK_LIBRARIES(${PROJECT_NAME} aruco)

ADD_EXECUTABLE(aruco_test aruco_test.cpp)
ADD_EXECUTABLE(aruco_simple aruco_simple.cpp)
ADD_EXECUTABLE(aruco_create_marker aruco_create_marker.cpp)
ADD_EXECUTABLE(aruco_create_board aruco_create_board.cpp)
ADD_EXECUTABLE(aruco_selectoptimalmarkers aruco_selectoptimalmarkers.cpp)
ADD_EXECUTABLE(aruco_simple_board aruco_simple_board.cpp)
ADD_EXECUTABLE(aruco_test_board aruco_test_board.cpp)
ADD_EXECUTABLE(aruco_board_pix2meters aruco_board_pix2meters.cpp)
ADD_EXECUTABLE(aruco_calibration aruco_calibration.cpp)
#ADD_EXECUTABLE(aruco_test_board_stability aruco_test_board_stability.cpp)

INSTALL(TARGETS aruco_test  aruco_board_pix2meters aruco_simple aruco_create_marker aruco_create_board aruco_simple_board aruco_test_board aruco_selectoptimalmarkers RUNTIME DESTINATION bin)
IF(GL_FOUND AND BUILD_GLSAMPLES)
  ADD_EXECUTABLE(aruco_test_gl aruco_test_gl.cpp)
  TARGET_LINK_LIBRARIES(aruco_test_gl ${OPENGL_LIBS})

  ADD_EXECUTABLE(aruco_test_board_gl aruco_test_board_gl.cpp)
  TARGET_LINK_LIBRARIES(aruco_test_board_gl ${OPENGL_LIBS})
  
  ADD_EXECUTABLE(aruco_test_board_gl_mask aruco_test_board_gl_mask.cpp)
  TARGET_LINK_LIBRARIES(aruco_test_board_gl_mask ${OPENGL_LIBS})  

  INSTALL(TARGETS aruco_test_gl aruco_test_board_gl aruco_test_board_gl_mask RUNTIME DESTINATION bin)
ENDIF()
