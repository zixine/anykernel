#Jembud-Gawuk-Lonte-Bajingan

gua cuma dev gadungan


⚡ Zixine AnyKernel3 TemplateA customized AnyKernel3 template optimized for GKI (Generic Kernel Image) Android 12 (5.10) devices. This repository is designed to be used as a submodule or cloned directly in GitHub Actions workflows for automated kernel packaging.


🌟 Key FeaturesCustom ASCII Banner Support: Automatically displays your banner file in TWRP during installation.GKI Optimized: Pre-configured for Android 12 Kernel 5.10 structure (/dev/block/by-name/boot).Smart Safety Check: Prevents flashing on incompatible kernel bases (checks uname -r).CI/CD Ready: Structure is clean and ready for GitHub Actions integration.Clean Output: Simplified UI prints for a professional look.📂 Repository Structure/
├── anykernel.sh    # Main installation script (Modified logic)
├── banner          # Custom ASCII Art (Edit this file!)
├── META-INF/       # Flashable zip binaries (update-binary)
└── tools/          # Essential tools (magiskboot, ak3-core.sh)



🎨 How to Customize BannerOpen the file named banner in the root directory.Paste your ASCII art text.Save the file.The installer will automatically detect and print it during flash!Tip: Use Text to ASCII Generator to create cool logos.🚀 Usage in GitHub ActionsTo use this template in your kernel build workflow, simply clone it during the packaging step:- name: Package Kernel
  run: |
    # 1. Clone this repository
    git clone --depth=1 [https://github.com/Kingfinik98/Zixine-AnyKernel.git](https://github.com/Kingfinik98/Zixine-AnyKernel.git) -b main anykernel
    
    # 2. Inject your kernel image
    cp out/arch/arm64/boot/Image anykernel/
    
    # 3. (Optional) Update version string dynamically
    sed -i "s|kernel.string=.*|kernel.string=MyKernel-v1.0|g" anykernel/anykernel.sh
    
    # 4. Zip it!
    cd anykernel
    zip -r9 "../Kernel-Update.zip" ./*


    
🛠 Manual Zipping (PC)If you want to zip it manually from your computer:Place your Image file in the root folder.Run the following command in terminal:zip -r9 Update-Kernel.zip * -x .git README.md
🤝 Creditsosm0sis @ xda-developers for the original AnyKernel3.Kingfinik98 for the Zixine Template modifications.Built with ❤️ for the Android Community.
