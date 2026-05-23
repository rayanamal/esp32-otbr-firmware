### The command to produce these .bin files

After you run `idf.py build`, from inside the `examples/openthread/ot_rcp/build/` directory, run these commands to produce the final `result.bin` binary.

- For ESP32-C6:
```bash
esptool --chip esp32c6 merge-bin --flash-mode dio --flash-size 2MB --flash-freq 80m --output result.bin 0x0 bootloader/bootloader.bin 0x8000 partition_table/partition-table.bin 0x10000 esp_ot_rcp.bin
```

- For ESP32-H2:
```bash
esptool --chip esp32h2 merge-bin --flash-mode dio --flash-size 2MB --flash-freq 48m --output result.bin 0x0 bootloader/bootloader.bin 0x8000 partition_table/partition-table.bin 0x10000 esp_ot_rcp.bin
```

- For ESP32-C5:
```bash
esptool --chip esp32c5 merge-bin --flash-mode dio --flash-size 2MB --flash-freq 80m --output result.bin 0x2000 bootloader/bootloader.bin 0x8000 partition_table/partition-table.bin 0x10000 esp_ot_rcp.bin
```