cmake_minimum_required(VERSION 3.12.2)

project(STP2X3D)

set(CMAKE_CXX_STANDARD 17)

find_package (OpenCASCADE
    NO_DEFAULT_PATH
    REQUIRED)

add_executable(STP2X3D
  Component.cpp
  Component.h
  GDT_Item.cpp
  GDT_Item.h
  IShape.cpp
  IShape.h
  Mesh.cpp
  Mesh.h
  Model.cpp
  Model.h
  NumTool.h
  OCCLib.h
  OCCUtil.cpp
  OCCUtil.h
  S2X_Option.cpp
  S2X_Option.h
  StatsPrinter.h
  stdafx.cpp
  stdafx.h
  STEP_Data.cpp
  STEP_Data.h
  STEP_Reader.cpp
  STEP_Reader.h
  StopWatch.cpp
  StopWatch.h
  STP2X3D.cpp
  StrTool.h
  Tessellator.cpp
  Tessellator.h
  X3D_Writer.cpp
  X3D_Writer.h
)

target_include_directories(${PROJECT_NAME} PRIVATE ${OpenCASCADE_INCLUDE_DIR})
target_link_directories(${PROJECT_NAME} PRIVATE ${OpenCASCADE_LIBRARY_DIR})
target_link_libraries(${PROJECT_NAME} ${OpenCASCADE_LIBRARIES})

install(TARGETS ${PROJECT_NAME} DESTINATION bin)
