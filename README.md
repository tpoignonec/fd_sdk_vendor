# fd_sdk_vendor
ROS 2 vendor package for Force Dimension SDK

## Usage example


> `package.xml` :
```xml
...
<depend>fd_sdk_vendor</depend>
...
```

> `CMakeLists.txt` :
```cmake
...
find_package(fd_sdk_vendor)
...
ament_target_dependencies(<the_target> <type> fd_sdk_vendor)
...
```
> `xxx.cpp` :
```cpp
#include <fd_sdk_vendor/dhd.hpp>

/*
-----------------------------
List of valid include paths:
-----------------------------
  * Haptic SDK
#include <fd_sdk_vendor/dhd.hpp>

  * Robotic SDK
#include <fd_sdk_vendor/drd.hpp>

  * Legacy includes (provided for compatibility with older code)
#include "dhdc.h"
#include "drdc.h"
*/
...

int major, minor, release, revision;
dhdGetSDKVersion (&major, &minor, &release, &revision);
printf("Force Dimension SDK, version %i.%i.%i", major, minor, release);

...
```