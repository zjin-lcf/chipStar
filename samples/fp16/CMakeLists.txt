if(DETECTED_ARCHITECTURE STREQUAL "riscv64")
  message(STATUS "RISC-V 64-bit architecture detected. Skipping fp16 tests.")
else()
  add_chip_test(fp16 fp16 PASSED haxpy-base.cpp)
  add_chip_test(fp16_math fp16_math PASSED half_math.cpp)
  add_chip_test(fp16_half2_math fp16_half2_math PASSED half2_math.cpp)
endif()