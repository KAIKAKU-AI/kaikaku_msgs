cmake_minimum_required(VERSION 3.8)
project(kaikaku_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/NewLineItem.msg"
  "msg/OrderLineItem.msg"
  "msg/PickupDetails.msg"
  "msg/DeliveryDetails.msg"
  "msg/Fulfillment.msg"
  "msg/Recipient.msg"

  "msg/PrintJob.msg"
  "msg/LineItemRecipe.msg"
  "msg/RecipeIngredient.msg"

  "msg/BarcodeScan.msg"
  "msg/ScannerStatus.msg"

  "msg/FusionLayout.msg"
  "msg/StationLayout.msg"
  "msg/DispenserLayout.msg"
  "msg/ConveyorLayout.msg"

  "msg/GetMass.msg"
  "msg/CurrentMass.msg"
  "msg/ConveyorMove.msg"
  "msg/ConveyorInterrupt.msg"
  "msg/DispenserDispense.msg"
  "msg/DispenserMove.msg"
  "msg/DispenserDispensed.msg"
  "msg/IngredientParameters.msg"

  # Cloud Services .msg and .srv
  "msg/CallStatus.msg"
  "srv/BarcodeToIngredients.srv"
  "srv/FetchIngredients.srv",
  "srv/FetchFusionLayout.srv"
)


if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
