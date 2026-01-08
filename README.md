⚡ Zixine AnyKernel3 Template
A customized AnyKernel3 template optimized for GKI (Generic Kernel Image) Android 12 (5.10) devices.

🌟 Key Features
Custom ASCII Banner Support: Automatically displays your banner file in TWRP.
GKI Optimized: Pre-configured for Android 12 Kernel 5.10 structure.
Smart Safety Check: Prevents flashing on incompatible kernel bases.
📂 Repository Structure
anykernel.sh - Main installation script
banner - Custom ASCII Art (Edit this file!)
META-INF/ - Flashable zip binaries
tools/ - Essential tools (magiskboot, ak3-core.sh)
🎨 How to Customize Banner
Open the file named banner.
Paste your ASCII art text.
Save the file.

🚀 Usage in GitHub Actions
- name: Package Kernel
 run: |
   git clone --depth=1 https://github.com/Zixine-AnyKernel.git -b main anykernel
   cp out/arch/arm64/boot/Image anykernel/
   sed -i "s|kernel.string=.*|kernel.string=MyKernel-v1.0|g" anykernel/anykernel.sh
   cd anykernel
   zip -r9 "../Kernel-Update.zip" ./*

🤝 Credits
osm0sis for AnyKernel3
