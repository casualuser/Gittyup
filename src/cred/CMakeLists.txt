if(WIN32)
  set(CREDENTIAL_IMPL_FILE WinCred.cpp)
endif()

add_library(cred Cache.cpp Store.cpp CredentialHelper.cpp GitCredential.cpp
                 ${CREDENTIAL_IMPL_FILE})

target_link_libraries(cred conf git Qt5::Core)

set_target_properties(cred PROPERTIES AUTOMOC ON)
