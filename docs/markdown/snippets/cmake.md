## Configure CMake subprojects with meson.subproject_options

Meson now supports passing configuration options to CMake and overriding
certain build details extracted from the CMake subproject.

The new CMake configuration options object is very similar to the
[configuration data object](Reference-manual.md#configuration-data-object) object
returned by [`configuration_data`](Reference-manual.md#configuration_data). It
is generated by the `subproject_options` function

All configuration options have to be set *before* the subproject is configured
and must be passed to the `subproject` method via the `options` key. Altering
the configuration object won't have any effect on previous `cmake.subproject`
calls.

**Note:** The `cmake_options` kwarg for the `subproject` function is now
deprecated since it is replaced by the new `options` system.
