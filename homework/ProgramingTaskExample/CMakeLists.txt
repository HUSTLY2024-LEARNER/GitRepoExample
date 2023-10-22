cmake_minimum_required(VERSION 3.12)

project(ProgrammingTask)

find_package(OpenCV 4 REQUIRED)					# find opencv 4
set(sc_program_name ${PROJECT_NAME})			# make the name of the output program follow the name of this project.
aux_source_directory(src/ sc_program_src)		# find all source files

# make target of executable output
add_executable(${sc_program_name}
	${sc_program_src}
)

# include header files in the executable target
target_include_directories(${sc_program_name} BEFORE
	PUBLIC include
)

# link the libraries to the executable target
target_link_libraries(${sc_program_name} 
	PUBLIC ${OpenCV_LIBS}
)
