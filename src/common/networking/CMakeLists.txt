#src/common/networking

add_library(networking STATIC 
	"networking.cpp"
	"connection.cpp")
 target_link_libraries(networking PUBLIC ssl include_dir)
 target_compile_definitions(networking PUBLIC ASIO_STANDALONE)

 if(win32)
    target_compile_definitions(networking PUBLIC _WIN32_WINNT_WIN10=0x0A00 _WIN32_WINNT=0x0A00)
endif(win32)