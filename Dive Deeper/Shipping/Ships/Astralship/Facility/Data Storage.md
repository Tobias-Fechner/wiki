- **Model**: Seagate IronWolf 4TB
- **Purpose**: Built for NAS systems, optimized for RAID configurations.
- **Features**: 5900 RPM, AgileArray technology for enhanced RAID performance and reliability.
### Cost Estimates and Purchase Options

#### Western Digital Red Plus 4TB

- **Price**: Approximately $100-$120 per drive
- **Total Cost**: Around $200-$240 for 2 drives
- **Where to Buy**: Amazon, Newegg, Best Buy, or directly from Western Digital's website

#### Seagate IronWolf 4TB

- **Price**: Approximately $100-$120 per drive
- **Total Cost**: Around $200-$240 for 2 drives
- **Where to Buy**: Amazon, Newegg, Best Buy, or directly from Seagate's website

### Example Links for Purchase

1. **WD Red Plus 4TB**:
   - [Amazon](https://www.amazon.com/WD-Red-Plus-Hard-Drive/dp/B08V81D2YT/)
   - [Newegg](https://www.newegg.com/western-digital-wd40efzx-4tb/p/N82E16822236872)
   - [Best Buy](https://www.bestbuy.com/site/wd-red-plus-4tb-internal-sata-nas-hard-drive-for-desktops/6453332.p)

2. **Seagate IronWolf 4TB**:
   - [Amazon](https://www.amazon.com/Seagate-IronWolf-4TB-Internal-ST4000VN008/)
   - [Newegg](https://www.newegg.com/seagate-ironwolf-st4000vn008-4tb/p/N82E16822178781)
   - [Best Buy](https://www.bestbuy.com/site/seagate-ironwolf-4tb-internal-sata-nas-hard-drive-for-desktops/5715743.p)

### Steps for Setting Up RAID 1

Once you have purchased and received the drives, follow these steps to set up RAID 1:

1. **Install the Drives**:
   - Mount the drives into your server chassis.
   - Connect the drives to the motherboard using SATA cables.

2. **Configure RAID in BIOS/UEFI**:
   - Boot into the BIOS/UEFI settings of your server.
   - Locate the RAID configuration utility.
   - Select RAID 1 and choose the two 4TB drives.
   - Save and exit the BIOS/UEFI.

3. **Operating System Installation**:
   - If not already installed, install your chosen OS (e.g., Ubuntu Server).
   - Partition and format the RAID array.

4. **Create Filesystem**:
   - Use a command like `mkfs.ext4` to create a filesystem on the RAID array.
   ```sh
   sudo mkfs.ext4 /dev/md0
   ```
   - Mount the RAID array.
   ```sh
   sudo mkdir /mnt/media
   sudo mount /dev/md0 /mnt/media
   ```

5. **Automate Mounting**:
   - Add the RAID array to `/etc/fstab` for automatic mounting on boot.
   ```sh
   UUID=$(blkid -s UUID -o value /dev/md0)
   echo "UUID=$UUID /mnt/media ext4 defaults 0 2" | sudo tee -a /etc/fstab
   ```

6. **Backup and Monitoring**:
   - Implement regular backup solutions.
   - Monitor RAID health using tools like `mdadm`.

### Monitoring and Maintenance

- **Use `mdadm` for monitoring RAID health**:
  ```sh
  sudo mdadm --detail /dev/md0
  ```
- **Set up automated monitoring tools** like `prometheus` or `glances` to keep an eye on system performance.

By selecting either the WD Red Plus or Seagate IronWolf drives, you ensure a reliable and cost-effective setup for your local server with RAID 1 configuration, providing redundancy and data protection.