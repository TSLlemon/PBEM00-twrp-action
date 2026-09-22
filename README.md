# PBEM00 TWRP 云编译（GitHub Actions）

为 **OPPO R17 (PBEM00)** 预填的 TWRP 10 云编译仓库。  
设备树：[AmeChanRain/android_device_oppo_PBEM00](https://github.com/AmeChanRain/android_device_oppo_PBEM00)（`twrp-10`）  
源码：`minimal-manifest-twrp` / `platform_manifest_twrp_omni` 分支 **`twrp-10.0-deprecated`**

## 你怎么用

1. 用 GitHub 账号 **Fork** 本仓库，或新建空仓库后把本目录文件推上去  
2. 打开仓库 **Settings → Actions → General**，允许 Actions，并允许创建 Release（workflow 权限选 Read and write）  
3. 打开 **Actions** → 选 **Build TWRP (PBEM00)** → **Run workflow**  
4. 参数已默认填好，一般不用改，直接 Run  
5. 等待（通常 1～3 小时，看排队和磁盘；失败可再点一次）  
6. 成功后到 **Releases** 或该次运行的 **Artifacts** 下载 `PBEM00-recovery-*.img`

## 刷机注意

```bash
adb reboot bootloader
fastboot boot PBEM00-recovery-xxxx.img    # 先试启动
# 确认界面正常后再考虑：
# fastboot flash recovery PBEM00-recovery-xxxx.img
```

- 这是**非官方**包，且设备树停更于约 2022，不保证适配你现在的 **F.29**  
- 进 TWRP 后先备份，**不要乱点**去强制加密之类选项  
- 免费 GitHub Actions 有时长/磁盘限制，偶发失败属正常

## 默认参数对照

| 参数 | 默认值 |
| --- | --- |
| MANIFEST_URL | `https://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni` |
| MANIFEST_BRANCH | `twrp-10.0-deprecated` |
| DEVICE_TREE_URL | `https://github.com/AmeChanRain/android_device_oppo_PBEM00` |
| DEVICE_TREE_BRANCH | `twrp-10` |
| DEVICE_PATH | `device/oppo/PBEM00` |
| DEVICE_NAME | `PBEM00` |
| MAKEFILE_NAME | `omni_PBEM00` |
| BUILD_TARGET | `recovery` |
