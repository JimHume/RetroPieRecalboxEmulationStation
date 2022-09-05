# General Info
When downloading pre-built images (Damaso / Wolfanoz / etc) and attempting to run them on a newer Pi, they typically fail with the message `Start4.elf is not compatible` or `This board requires new software`

To fix newer boards vs. older, incompatible boot files:
1. Write the image to an SD card. 
2. Navigate to https://github.com/raspberrypi/firmware/tree/master/boot
3. Download all the fixup*.dat and start*.elf files (~16 files total)
4. Mount the boot partition onto a computer
5. Paste the fixup*.dat and start*.elf files into the appropriate folder, overwriting what is already there
6. umount
7. Try booting the Pi again with the updated SD card (it should now work in theory)

Note: some images seem to use different filesystems for the boot partition, deviating from the norm. These can be a bit tricky to deal with and/or just require them to be mounted onto a Linux vm / machine in order to properly update the files

