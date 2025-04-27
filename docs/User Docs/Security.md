# Security Considerations
This section is intended to be a non-exhaustive list of factors to consider when evaluating the security of a KFDtool system.

## P25 Keyloading Considerations
- Some radios store keys in software rather than hardware, making them potentially retrievable. 
    - What this means
        - Some keys are stored in a hardware security module or HSM (e.g. UCM, MACE) which is very secure as barring an exploit for the specific chip being used, once written the keys are unable to be retrieved as plaintext from the HSM. Additionally, many HSMs have various methods of tamper detection to erase all keys if the unit is tampered with. This means that ideally, if an attacker had physical access to the radio, they would be unable to retrieve the key material from the radio. However, some radios store keys in software (e.g. software ADP, Motorola APX900 and Kenwood VP8000 software crypto), which has far fewer protections than a hardware security module. A skilled attacker, given enough time with a radio, could extract key material from a radio using software encryption. This is not to say that software encryption has no place; however it should be factored in when evaluating your individual threat model.

- Keys are forever.
    - What this means
        - It is not always possible to remotely erase a lost radio's keys for a multitude of reasons. Therefore, if a keyed radio is lost, any keys that were installed in it should be considered compromised.

## KFDtool-specific Considerations
- The KFDtool as a computer peripheral has several important considerations to keep in mind when secure keyloading is required.
    - What this means
        - Because the KFDtool keyloader is made up of a USB peripheral and software for use on a Windows PC, precautions have to be taken to preserve the integrity of the encryption keys due to the complex nature of the systems involved.

- The following points are only valid with unmodified software, firmware, and hardware. With physical access to the PC or adapter, the software, firmware, or hardware could be modified to covertly retain the plaintext keying material.
    - What this means
        - With physical access to the KFDtool adapter or computer running the KFDtool software, someone could modify them in a way to record or transmit the encryption keys without your knowledge. Therefore, you should physically secure the KFDtool adapter and the computer used for keyloading.

- Plaintext keying material is present in the PC's RAM, over the USB connection, in the adapter's RAM, and over the keyload connection. Therefore, you must trust the PC that the software is running on, or air gap it.
    - What this means
        - If the computer you use for keyloading is connected to a network, it is possible that the encryption keys could be accessed without your knowledge due to vulnerabilities in Windows or other software installed on your computer. Therefore, it is recommended that you use a computer that is not connected to any networks, and that you only install software and connect devices to it that you trust.

- It is possible that plaintext keying material in the PC's RAM is paged out to disk. It is also possible that Windows crash dumps may contain plaintext keying material. Therefore, it is recommended that the PC's hard drive is protected using full disk encryption such as BitLocker and powered off when unattended.
    - What this means
        - Windows is a complex operating system, and there are many ways for the encryption keys to end up on the hard drive without your knowledge. Therefore, encrypting the hard drive of the computer you use for keyloading is a good idea as it provides another layer of security against unauthorized users accessing the encryption keys without your knowledge.

- After the KFDtool adapter has been disconnected from the USB port, any residual plaintext keying material present in the microcontroller's RAM will be lost.
    - What this means
        - When unplugging the KFDtool adapter from the computer, any encryption keys are lost due to the memory type used. The KFDtool adapter by design does not store any encryption keys.

- When certain non-default logging is enabled, plaintext keying material is written out to the log file on disk. This logging should only be enabled when diagnostic information needs to be collected, and only used with dummy keying material.
    - What this means
        - There are options in the KFDtool software configuration files that can be set to write detailed information to the hard drive for use to diagnose issues. If you are directed to change these files to enable logging to diagnose an issue, understand that the keys you use may be included in these logs. Therefore, you should not use your production keys when collecting these logs.