# VMware-Kickstart-Config-File


Disable Secure Boot



Step by Step:

 VMware-VMvisor-installer-*.iso

	• Unpack the iso file
	
	Double click to mount the iso file
	
	Copy files to folder: 
	
    # cp -r /Volumes/ESXI-9.1.0.0100-25433460-STANDAR ./unpacked

	• Create the KS folder and copy KS.CFG to KS folder
	
	• Edit BOOT.CFG and EFI/BOOT/BOOT.CFG and edit kernelopt to
	kernelopt=ks=cdrom:/KS/KS.CFG
	

	• Pack the files and make iso again
	To use mkisofs on your Mac, you need to install the cdrtools: brew install cdrtools
	# /opt/homebrew/Cellar/cdrtools/3.02a09/bin/mkisofs -relaxed-filenames -J -R -o custom_esxi_91.iso -b ISOLINUX.BIN -c BOOT.CAT -no-emul-boot -boot-load-size 4 -boot-info-table -eltorito-alt-boot -b EFIBOOT.IMG -no-emul-boot ./ESXI-9.1.0.0100-25433460-STANDAR
	
