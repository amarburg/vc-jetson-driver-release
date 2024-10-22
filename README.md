n.b. This repository is based on the [Allied Vision Alvium CSI Driver for Jetpack 6](https://github.com/alliedvision/alvium-jetson-driver-release).

# Vision Components MIPI driver for Jetpack 6 

## Building
1. Clone this repository including all submodules
2. Download the Jetson Linux driver package (BSP) and cross compiler from: [Jetson Linux Downloads](https://developer.nvidia.com/embedded/jetson-linux)
3. Extract the driver package **in this directory**: 
    ```shell
        tar -xf jetson_linux_r36*.bz2
    ```
4. Extract the kernel headers from the driver package:
    ```shell
        cd Linux_for_Tegra/kernel/
        tar -xf kernel_headers.tbz2
    ```
5. Extract the cross compiler **in this directory**:
   ```shell
        tar -xf aarch64--glibc--stable-2022.08-1.tar.bz2
   ```
6. Set the following environment variables ( `source setup.sh` is a convenience alias):
    ```shell
        export ARCH=arm64
        export CROSS_COMPILE=<path to cross compiler>/bin/aarch64-buildroot-linux-gnu-
        export KERNEL_SRC=Linux_for_Tegra/kernel/linux-headers-*-linux_x86_64/3rdparty/canonical/linux-jammy/kernel-source/
    ```

7. Build the kernel modules:
    ```shell
        make all 
    ```
7. **I'm not sure what happens next...**

8. Install the driver modules
    ```shell
        export INSTALL_MOD_PATH=<path to install directory>
        make install
    ```
   
# Beta Disclaimer

Please be aware that all code revisions not explicitly listed in the Github Release section are
considered a **Beta Version**.

For Beta Versions, the following applies in addition to the GPLv2 License:

THE SOFTWARE IS PRELIMINARY AND STILL IN TESTING AND VERIFICATION PHASE AND IS PROVIDED ON AN “AS
IS” AND “AS AVAILABLE” BASIS AND IS BELIEVED TO CONTAIN DEFECTS. THE PRIMARY PURPOSE OF THIS EARLY
ACCESS IS TO OBTAIN FEEDBACK ON PERFORMANCE AND THE IDENTIFICATION OF DEFECTS IN THE SOFTWARE,
HARDWARE AND DOCUMENTATION.


