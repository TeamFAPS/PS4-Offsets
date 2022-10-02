# PS4Offsets & Payloads 1.76/4.05/4.55/5.01/5.05

<p align="center">
🔥 PS4Offsets ~ Use these offsets if you need to update your old payloads. 🔥
  <br>
</p>

# 3.55

# 3.70

# 4.05
```
#define KERN_XFAST_SYSCALL 0x30EB30
#define KERN_PROCESS_ASLR 0x2862D6
#define KERN_PRISON_0 0xF26010
#define KERN_ROOTVNODE 0x206D250
#define KERN_PTRACE_CHECK_1 0xAC2F1
#define KERN_PTRACE_CHECK_2 0xAC6A2
#define KERNEL_REGMGR_SETINT 0x4CEAB0
```
```
//Perm Browser Patch - CrazyVoids 
uint64_t *(sceRegMgrSetInt)(uint32_t regId, int value) = NULL;
sceRegMgrSetInt = (void *)&ptrKernel[KERNEL_REGMGR_SETINT];
sceRegMgrSetInt(0x3C040000, 0);

Will add more soon.
```

# 4.55  
``` 
//4.55 KERN
#define	KERN_XFAST_SYSCALL 0x3095D0
#define KERN_PROCESS_ASLR 0x1BA559
#define KERN_PRISON_0 0x10399B0
#define KERN_ROOTVNODE 0x21AFA30
#define KERN_PTRACE_CHECK 0x17D2C1

```
```
// debug settings FULL
kernelBase[0x1B6D086] |= 0x14;
kernelBase[0x1B6D0A9] |= 0x3;
kernelBase[0x1B6D0AA] |= 0x1;
kernelBase[0x1B6D0C8] |= 0x1;

// Disable write protection
*(uint32_t*)&kernelBase[0x4D70F7] = 0;
*(uint32_t*)&kernelBase[0x4D7F81] = 0;

//UART Enabler 4.55
*(char *)(kernel_base + 0x1997BC8) = 0;

//EAP Internal Partition Key
kernelBase[0x258CCD0]

#elif defined PS4_4_55

#define kern_off_printf 0x17F30
#define kern_off_copyin 0x14A890
#define kern_off_copyout 0x14A7B0
#define kern_off_copyinstr 0x14AD00
#define kern_off_kmem_alloc_contig 0x250320
#define kern_off_kmem_free 0x16EEA0
#define kern_off_pmap_extract 0x41DBC0
#define kern_off_pmap_protect 0x420310
#define kern_off_sched_pin 0x73770
#define kern_off_sched_unpin 0x73780
#define kern_off_smp_rendezvous 0xB2BB0
#define kern_off_smp_no_rendevous_barrier 0xB2970
#define kern_off_icc_query_nowait 0x808C0
#define kern_off_kernel_map 0x1B31218
#define kern_off_sysent 0x102B690
#define kern_off_kernel_pmap_store 0x21BCC38
#define kern_off_Starsha_UcodeInfo 0
#define kern_off_gpu_devid_is_9924 0x496720
#define kern_off_gc_get_fw_info 0x4A12D0

#define kern_off_pml4pml4i 0x21BCC28
#define kern_off_dmpml4i 0x21BCC2C
#define kern_off_dmpdpi 0x21BCC30
```

# 4.74 Offsets
```
#define KERN_XFAST_SYSCALL  0x30B7D0
#define KERN_PRISON_0		0x1042AB0
#define KERN_ROOTVNODE		0x21B89E0
#define KERN_PROCESS_ASLR   0x1BC769
#define KERN_PTRACE_CHECK 	0x17C521
#define DT_HASH_SEGMENT		0xB26020

#elif defined PS4_4_74

#define kern_off_printf                     0x17F30  // Updated
#define kern_off_copyin                     0x149f20 // Updated
#define kern_off_copyout                    0x149E40 // Updated
#define kern_off_copyinstr                  0x14A5C0 // Updated
#define kern_off_kmem_alloc_contig          0x2527A0 // Updated
#define kern_off_kmem_free                  0x16E100 // Updated
#define kern_off_pmap_extract               0x41EA30 // Updated
#define kern_off_pmap_protect               0x421180 // Updated
#define kern_off_sched_pin                  0x072D50 // Updated
#define kern_off_sched_unpin                0X072D60 // Updated
#define kern_off_smp_rendezvous             0x0B2210 // Updated
#define kern_off_smp_no_rendevous_barrier   0x0B1FD0 // Updated
#define kern_off_icc_query_nowait           0x07FF00 // Updated

#define kern_off_kernel_map                 0x1B39218 // Updated CB
#define kern_off_sysent                     0x1034790 // Updated CB
#define kern_off_kernel_pmap_store          0x21C5A38 // Updated CB
#define kern_off_Starsha_UcodeInfo 0
#define kern_off_gpu_devid_is_9924          0x4976A0 // Needs Verification
#define kern_off_gc_get_fw_info             0x4A2250 // Updated
#define kern_off_pml4pml4i                  0x21C5A28 // Updated
#define kern_off_dmpml4i                    0x21C5A2C // Updated
#define kern_off_dmpdpi                     0x21C5E30 // Updated
#endif

```
# 5.01 Offsets

```

KERN_XFAST_SYSCALL 0x1C0 //5.0x https://twitter.com/C0rpVultra/status/992789973966512133
KERN_PRISON_0		0x10986A0 //5.01
KERN_ROOTVNODE		0x22C19F0 //5.01
KERN_PMAP_PROTECT	0x2E2D00 //5.01
KERN_PMAP_PROTECT_P	0x2E2D44 //5.01
KERN_PMAP_STORE		0x22CB4F0 //5.01
KERN_REGMGR_SETINT	0x4F8940 //5.01
KERN_PROCESS_ASLR 0x194765 //5.01 Thanks to J00ni3 - Need Verification
KERN_PTRACE_CHECK 0x30D633 //5.01 Thanks to J00ni3 - Need Verification
DT_HASH_SEGMENT		0xB5EE20 //5.01
```
```
  
// debug settings patches 5.01
*(char *)(kernel_base + 0x1CD0686) |= 0x14;
*(char *)(kernel_base + 0x1CD06A9) |= 3;
*(char *)(kernel_base + 0x1CD06AA) |= 1;
*(char *)(kernel_base + 0x1CD06C8) |= 1;

// debug menu error patches 5.01
*(uint32_t *)(kernel_base + 0x4F8C78) = 0;
*(uint32_t *)(kernel_base + 0x4F9D8C) = 0;

// target_id patches 5.01
*(uint16_t *)(kernel_base + 0x1CD068C) = 0x8101;
*(uint16_t *)(kernel_base + 0x236B7FC) = 0x8101;

// disable pfs signature 5.01
*(uint32_t *)(kernel_base + 0x6A2320) = 0x90C3C031;

// flatz enable RIFs 5.01
  *(uint32_t *)(kernel_base + 0x64AED0) = 0x90C301B0;
  *(uint32_t *)(kernel_base + 0x64AEF0) = 0x90C301B0;
  
// enable perm browser 5.01
uint64_t *(sceRegMgrSetInt)(uint32_t regId, int value) = NULL;
sceRegMgrSetInt = (void *)&ptrKernel[KERNEL_REGMGR_SETINT];
sceRegMgrSetInt(0x3C040000, 0, 0, 0, 0);

// enable mmap of all SELF 5.01
*(uint8_t*)(kernel_base + 0x117B0) = 0xB0;
*(uint8_t*)(kernel_base + 0x117B1) = 0x01;
*(uint8_t*)(kernel_base + 0x117B2) = 0xC3;

*(uint8_t*)(kernel_base + 0x117C0) = 0xB0;
*(uint8_t*)(kernel_base + 0x117C1) = 0x01;
*(uint8_t*)(kernel_base + 0x117C2) = 0xC3;

*(uint8_t*)(kernel_base + 0x13EF2F) = 0x31;
*(uint8_t*)(kernel_base + 0x13EF30) = 0xC0;
*(uint8_t*)(kernel_base + 0x13EF31) = 0x90;
*(uint8_t*)(kernel_base + 0x13EF32) = 0x90;
*(uint8_t*)(kernel_base + 0x13EF33) = 0x90;

#elif defined PS4_5_01

#define kern_off_printf 0x00435C70
#define kern_off_copyin 0x1EA600
#define kern_off_copyout 0x1EA520
#define kern_off_copyinstr 0x1EAA30
#define kern_off_kmem_alloc_contig 0xF1B80
#define kern_off_kmem_free 0xFCD40
#define kern_off_pmap_extract 0x2E02A0
#define kern_off_pmap_protect 0x2E2D00
#define kern_off_sched_pin 0x31FB70
#define kern_off_sched_unpin 0x31FB80
#define kern_off_smp_rendezvous 0x1B84A0
#define kern_off_smp_no_rendevous_barrier 0x1B8260
#define kern_off_icc_query_nowait 0x44020
#define kern_off_kernel_map 0x1AC60E0
#define kern_off_sysent 0x107C610
#define kern_off_kernel_pmap_store 0x22CB4F0
#define kern_off_Starsha_UcodeInfo 0
#define kern_off_gpu_devid_is_9924 0x4DDC00
#define kern_off_gc_get_fw_info 0x4D33D0

#define kern_off_pml4pml4i 0x22CB4E0
#define kern_off_dmpml4i 0x22CB4E4
#define kern_off_dmpdpi 0x22CB4E8

#endif
```
# 5.05 Offsets
```
KERN_XFAST_SYSCALL 0x00001C0 //5.0x https://twitter.com/C0rpVultra/status/992789973966512133
KERN_PRISON_0		0x10986a0
KERN_ROOTVNODE	0x22c1a70
KERN_PMAP_PROTECT	0x2E3090
KERN_PROCESS_ASLR 0x194875
KERN_PTRACE_CHECK 0x30D9AA

KERN_PMAP_PROTECT	0x2E3090
KERN_PMAP_PROTECT_P	0x2E30D4
KERN_PMAP_STORE		0x22CB570

DT_HASH_SEGMENT		0xB5EF30

```
```
//UART Enabler 5.05 Thanks to @DiwiDog // https://twitter.com/diwidog/status/996362528312647680
*(char *)(kernel_base + 0x09ECEB0) = 0;

// debug settings patches 5.05
*(char *)(kernel_base + 0x1CD0686) |= 0x14;
*(char *)(kernel_base + 0x1CD06A9) |= 3;
*(char *)(kernel_base + 0x1CD06AA) |= 1;
*(char *)(kernel_base + 0x1CD06C8) |= 1;

// debug menu error patches 5.05
*(uint32_t *)(kernel_base + 0x4F9048) = 0;
*(uint32_t *)(kernel_base + 0x4FA15C) = 0;

// enable mmap of all SELF 5.05
*(uint8_t*)(kernel_base + 0x117B0) = 0xB0;
*(uint8_t*)(kernel_base + 0x117B1) = 0x01;
*(uint8_t*)(kernel_base + 0x117B2) = 0xC3;

*(uint8_t*)(kernel_base + 0x117C0) = 0xB0;
*(uint8_t*)(kernel_base + 0x117C1) = 0x01;
*(uint8_t*)(kernel_base + 0x117C2) = 0xC3;

*(uint8_t*)(kernel_base + 0x13F03F) = 0x31;
*(uint8_t*)(kernel_base + 0x13F040) = 0xC0;
*(uint8_t*)(kernel_base + 0x13F041) = 0x90;
*(uint8_t*)(kernel_base + 0x13F042) = 0x90;
*(uint8_t*)(kernel_base + 0x13F043) = 0x90;

// flatz disable pfs signature check 5.05
*(uint32_t *)(kernel_base + 0x6A2700) = 0x90C3C031;
// flatz enable debug RIFs 5.05
*(uint32_t *)(kernel_base + 0x64B2B0) = 0x90C301B0;
*(uint32_t *)(kernel_base + 0x64B2D0) = 0x90C301B0;

// debug pkg free string
#define fake_free_patch                 0xEA96A7

// make pkgs installer working with external hdd
#define pkg_installer_patch		0x9312A1


// Fself
#define sceSblAuthMgrSmStart_addr       0x6418E0
#define sceSblServiceMailbox_addr       0x632540
#define sceSblAuthMgrGetSelfInfo_addr   0x63CD40
#define sceSblAuthMgrIsLoadable2_addr   0x63C4F0
#define sceSblAuthMgrVerifyHeader_addr  0x642B40

// Fpkg
#define sceSblPfsKeymgrGenKeys_addr     0x62D480
#define sceSblPfsSetKeys_addr           0x61EFA0
#define sceSblKeymgrClearKey_addr       0x62DB10
#define sceSblKeymgrSetKeyForPfs_addr   0x62D780
#define sceSblKeymgrSmCallfunc_addr     0x62E2A0
#define sceSblDriverSendMsg_addr        0x61D7F0
#define RsaesPkcs1v15Dec2048CRT_addr    0x1FD7D0
#define AesCbcCfb128Encrypt_addr        0x3A2BD0
#define AesCbcCfb128Decrypt_addr        0x3A2E00
#define Sha256Hmac_addr                 0x2D55B0

// Patch
#define proc_rwmem_addr                 0x30D150
#define vmspace_acquire_ref_addr        0x19EF90
#define vmspace_free_addr               0x19EDC0
#define vm_map_lock_read_addr           0x19F140
#define vm_map_unlock_read_addr         0x19F190
#define vm_map_lookup_entry_addr        0x19F760

// Fself hooks
#define sceSblAuthMgrIsLoadable2_hook                             0x63E3A1
#define sceSblAuthMgrVerifyHeader_hook1                           0x63EAFC
#define sceSblAuthMgrVerifyHeader_hook2                           0x63F718
#define sceSblAuthMgrSmLoadSelfSegment__sceSblServiceMailbox_hook 0x64318B
#define sceSblAuthMgrSmLoadSelfBlock__sceSblServiceMailbox_hook   0x643DA2

// Fpkg hooks
#define sceSblKeymgrSmCallfunc_npdrm_decrypt_isolated_rif_hook    0x64C720
#define sceSblKeymgrSmCallfunc_npdrm_decrypt_rif_new_hook         0x64D4FF
#define sceSblKeymgrSetKeyStorage__sceSblDriverSendMsg_hook       0x624065
#define mountpfs__sceSblPfsSetKeys_hook1                          0x6AAAD5
#define mountpfs__sceSblPfsSetKeys_hook2                          0x6AAD04

// SceShellCore patches

// call sceKernelIsGenuineCEX
#define sceKernelIsGenuineCEX_patch1    0x16D05B 
#define sceKernelIsGenuineCEX_patch2    0x79980B
#define sceKernelIsGenuineCEX_patch3    0x7E5A13
#define sceKernelIsGenuineCEX_patch4    0x94715B

// call nidf_libSceDipsw
#define nidf_libSceDipsw_patch1         0x16D087
#define nidf_libSceDipsw_patch2         0x23747B
#define nidf_libSceDipsw_patch3         0x799837
#define nidf_libSceDipsw_patch4         0x947187

// enable fpkg
#define enable_fpkg_patch               0x3E0602

#elif defined PS4_5_05  Thanks to #J0nni3

#define kern_off_printf                     0x436040
#define kern_off_copyin                     0x1EA710
#define kern_off_copyout                    0x1EA630
#define kern_off_copyinstr                  0x1EAB40
#define kern_off_kmem_alloc_contig          0xF1C90
#define kern_off_kmem_free                  0xFCE50
#define kern_off_pmap_extract               0x2E0570
#define kern_off_pmap_protect               0x2E3090
#define kern_off_sched_pin                  0x31FF40
#define kern_off_sched_unpin                0x31FF50
#define kern_off_smp_rendezvous             0x1B85B0
#define kern_off_smp_no_rendevous_barrier   0x1B8366
#define kern_off_icc_query_nowait           0x44020
#define kern_off_kernel_map                 0x1AC60E0
#define kern_off_sysent                     0x107C610
#define kern_off_kernel_pmap_store          0x22CB570
#define kern_off_Starsha_UcodeInfo 0
#define kern_off_gpu_devid_is_9924          0x4DE010
#define kern_off_gc_get_fw_info             0x4D37A0
#define kern_off_pml4pml4i                  0x22CB560 // Pending verification.
#define kern_off_dmpml4i                    0x22CB564
#define kern_off_dmpdpi                     0x22CB568
```
# 6.00 Offsets
```
KERN_XFAST_SYSCALL 0x00001C0

```
Please make an pull request for anything that is missing or want to add something.
This will be updated over a period of time adding more offsets.

## Contributors
Massive thanks to the following:

- [qwertyoruiopz](https://twitter.com/qwertyoruiopz)
- [Flatz](https://twitter.com/flat_z)
- SpecterDev
- Many others
