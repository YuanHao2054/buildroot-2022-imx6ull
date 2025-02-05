# 一、配置交叉编译工具链

2022版buildroot，根据教程使用gcc-arm-10.3-2021.07-x86_64-arm-none-linux-gnueabihf

路径和前缀参考：

```bash
BR2_TOOLCHAIN_EXTERNAL_PATH="/usr/local/arm/gcc-arm-10.3-2021.07-x86_64-arm-none-linux-gnueabihf"
BR2_TOOLCHAIN_EXTERNAL_CUSTOM_PREFIX="$(ARCH)-none-linux-gnueabihf"
```

需要到menuconfig中修改

# 二、配置defconfig文件

指定defconfig文件

```bash
make imx6ull_yuanhao_defconfig
```

用menuconfig修改defconfig

```bash
# 先用menuconfig修改
make menuconfig

#再保存到指定的defconfig中
make savedefconfig
```



# 三、配置编译选项

# 四、编译

**在wsl2中进行编译时，$PATH会把Windows中的路径也包含进去，需要指定Linux的路径**

```bash
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin make 
```

2022版buildroot，已经可以正常编译，但是它会同时打包uboot和内核镜像，暂时搁置。