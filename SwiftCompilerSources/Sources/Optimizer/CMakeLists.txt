# This source file is part of the Swift.org open source project
#
# Copyright (c) 2014 - 2021 Apple Inc. and the Swift project authors
# Licensed under Apache License v2.0 with Runtime Library Exception
#
# See http://swift.org/LICENSE.txt for license information
# See http://swift.org/CONTRIBUTORS.txt for Swift project authors

set(dependencies)
list(APPEND dependencies SIL)
if(SWIFT_ENABLE_EXPERIMENTAL_STRING_PROCESSING)
  list(APPEND dependencies ExperimentalRegex)
endif()

add_swift_compiler_module(Optimizer DEPENDS ${dependencies})

add_subdirectory(Analysis)
add_subdirectory(InstructionPasses)
add_subdirectory(PassManager)
add_subdirectory(FunctionPasses)
add_subdirectory(Utilities)
