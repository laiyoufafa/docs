# Building the Kconfig Visual Configuration

## Overview

### Kconfig Visual Configuration
Kconfig visual configuration is implemented on [Kconfiglib](https://github.com/ulfalizer/Kconfiglib) and [Kconfig](https://www.kernel.org/doc/html/latest/kbuild/kconfig-language.html#introduction). It allows customized configuration of OpenHarmony subsystem components.

This function has the following advantages:

- Intuitive display of software component options
- High reliability (Linux kernel and Buildroot use Kconfig for visualized configuration)

### Key Concepts

- [Kconfig](https://www.kernel.org/doc/html/latest/kbuild/kconfig-language.html#introduction): a visual configuration file format for Linux.

- [Kconfiglib](https://github.com/ulfalizer/Kconfiglib): a visual configuration tool based on the Kconfig format for Linux.

### Related Modules

- [Kconfig update module](https://gitee.com/openharmony/build/blob/master/tools/component_tools/generate_kconfig.py): updates the component information list in the Kconfig menu.

- [Config format conversion](https://gitee.com/openharmony/build/blob/master/tools/component_tools/parse_kconf.py): converts the **config** file generated on the GUI to the standard format for compilation and build.

## Procedure

1. Obtain the source code.

   For details, see [Obtaining Source Code](https://gitee.com/openharmony/docs/blob/master/en/device-dev/get-code/sourcecode-acquire.md).

2. Set up the environment.

   The Kconfiglib required for environment configuration has been embedded in the OpenHarmony hb tool. For details about how to install the hb tool, see [Install hb](https://gitee.com/openharmony/docs/blob/master/en/device-dev/quick-start/quickstart-lite-env-setup.md#install-hb).

3. Open the Kconfig configuration interface.

   ```shell
   #Go to the build repository directory.
   cd build/tools/component_tools
   menuconfig kconfig
   ```

   ![Kconfig example](./figure/kconfig_interface.png)

4. Set parameters.

   For details about the parameters, see [productdefine/common/base/base_product.json](https://gitee.com/openharmony/productdefine_common/blob/master/base/base_product.json).

   ![Setting parameters](./figure/kconfig_set_parameters.gif)

5. Select and configure the component.

   1. Press the arrow keys and select a subsystem. The component list of the subsystem is displayed.

   2. Press **Enter** to select a component.

   3. When setting `feature`, use commas (,) to separate multiple values.

      ![Selecting a component](./figure/kconfig_select_component.gif)

6. Save the settings.

   Press **S** to save the settings. You can set the name of the file to generate. By default, a file named `.config` file is generated in the current directory.

   ![Save settings](./figure/kconfig_save.png)

7. Generate the OpenHarmony style configuration file.

   Example:

   1. Perform a global build.

      ```shell
      cp productdefine/common/base/base_product.json productdefine/common/products/ohos-arm64.json
      ./build.sh --product-name ohos-arm64  --build-only-gn --ccache --gn-args pycache_enable=true --gn-args check_deps=true --build-only-gn
      ```

   2. Generate dependency files for the component.

      ```shell
      ./build/tools/module_dependence/part_deps.py --deps-files-path out/arm64/deps_files
      # output: out/arm64/part_deps_info/part_deps_info.json
      ```

   3. Generate the OpenHarmony style configuration file.

      ```shell
      cd build/tools/component_tools
      python3 parse_kconf.py --deps=/path/to/out/arm64/part_deps_info/part_deps_info.json
      ```

      By default, the file **product.json** is generated in the current directory. You can also use `python3 parse_kconf.py --out="example/out.json"` to specify the file path.

      For more operations, see `python3 parse_kconf.py -h`.

​	

## FAQs

### The latest component information is missing from the menu.

The component list [productdefine/common/base/base_product.json](https://gitee.com/openharmony/productdefine_common/blob/master/base/base_product.json) is updated with product updates and iterations. As a result, the Kconfig menu does not contain the latest components.

Solution:

- Update the [Kconfig file](https://gitee.com/openharmony/build/blob/master/tools/component_tools/kconfig).

  ```shell
  cd build/tools/component_tools
  python3 generate_kconfig.py
  ```

  For more details, see `python3 generate_kconfig.py -h`.
