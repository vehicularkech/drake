if(Bullet_FOUND)
  drake_add_cc_test(rigid_body_plant_test)
  target_link_libraries(rigid_body_plant_test
      drakeMultibodyParsers
      drakeRigidBodyPlant)

  drake_add_cc_test(compute_contact_result_test)
  target_link_libraries(compute_contact_result_test
      drakeRigidBodyPlant
      drakeIK
      drakeMultibodyParsers
      drakeOptimization
      drakeRBM
      drakeRigidBodyConstraint
      Eigen3::Eigen
      spruce
      )

  drake_add_cc_test(compliant_contact_model_test)
  target_link_libraries(compliant_contact_model_test
          drakeRigidBodyPlant
          drakeIK
          drakeMultibodyParsers
          drakeOptimization
          drakeRBM
          drakeRigidBodyConstraint
          Eigen3::Eigen
          spruce
          )

  drake_add_cc_test(contact_force_formula_test)
  target_link_libraries(contact_force_formula_test
      drakeRigidBodyPlant
      drakeIK
      drakeMultibodyParsers
      drakeOptimization
      drakeRBM
      drakeRigidBodyConstraint
      Eigen3::Eigen
      spruce
      )

  if (lcm_FOUND)
    drake_add_cc_test(rigid_body_plant_that_publishes_xdot_test)
    target_link_libraries(rigid_body_plant_that_publishes_xdot_test
        drakeLcm
        drakeMultibodyParsers
        drakeRigidBodyPlant)

    drake_add_cc_test(viewer_draw_translator_test)
    target_link_libraries(viewer_draw_translator_test drakeRigidBodyPlant)

    drake_add_cc_test(drake_visualizer_test)
    target_link_libraries(drake_visualizer_test
        drakeRigidBodyPlant
        drakeSystemAnalysis)
  endif()
endif()

if (lcm_FOUND)
  drake_add_cc_test(frame_visualizer_test)
  target_link_libraries(frame_visualizer_test
      drakeMultibodyParsers
      drakeRigidBodyPlant)
endif()

drake_add_cc_test(contact_force_test)
target_link_libraries(contact_force_test drakeRigidBodyPlant)

drake_add_cc_test(contact_resultant_force_test)
target_link_libraries(contact_resultant_force_test drakeRigidBodyPlant)

drake_add_cc_test(contact_detail_test)
target_link_libraries(contact_detail_test drakeRigidBodyPlant)

drake_add_cc_test(contact_info_test)
target_link_libraries(contact_info_test drakeRigidBodyPlant)

drake_add_cc_test(kinematics_results_test)
target_link_libraries(kinematics_results_test
    drakeMultibodyParsers
    drakeRigidBodyPlant)
