add_library(reflexxes SHARED 
    ReflexxesAPI.cpp
    TypeIIRMLCalculatePositionalExtrems.cpp
    TypeIIRMLDecisions.cpp
    TypeIIRMLDecisionTree1A.cpp
    TypeIIRMLDecisionTree1B.cpp
    TypeIIRMLDecisionTree1C.cpp
    TypeIIRMLDecisionTree2.cpp
    TypeIIRMLFallBackStrategy.cpp
    TypeIIRMLIsPhaseSynchronizationPossible.cpp
    TypeIIRMLPolynomial.cpp
    TypeIIRMLPosition.cpp
    TypeIIRMLQuicksort.cpp
    TypeIIRMLSetupModifiedSelectionVector.cpp
    TypeIIRMLStep1.cpp
    TypeIIRMLStep1IntermediateProfiles.cpp
    TypeIIRMLStep1Profiles.cpp
    TypeIIRMLStep2.cpp
    TypeIIRMLStep2IntermediateProfiles.cpp
    TypeIIRMLStep2PhaseSynchronization.cpp
    TypeIIRMLStep2Profiles.cpp
    TypeIIRMLStep2WithoutSynchronization.cpp
    TypeIIRMLStep3.cpp
    TypeIIRMLVelocityCalculatePositionalExtrems.cpp
    TypeIIRMLVelocity.cpp
    TypeIIRMLVelocityFallBackStrategy.cpp
    TypeIIRMLVelocityIsPhaseSynchronizationPossible.cpp
    TypeIIRMLVelocityMethods.cpp
    TypeIIRMLVelocitySetupPhaseSyncSelectionVector.cpp
)

file(GLOB files "${reflexxes_SOURCE_DIR}/include/*.h")
install(FILES ${files} DESTINATION include/reflexxes)

install(TARGETS reflexxes LIBRARY DESTINATION lib)

set(TARGET_NAME reflexxes)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/${TARGET_NAME}.pc.in
    ${CMAKE_CURRENT_BINARY_DIR}/${TARGET_NAME}.pc @ONLY)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/${TARGET_NAME}.pc
    DESTINATION lib/pkgconfig)
