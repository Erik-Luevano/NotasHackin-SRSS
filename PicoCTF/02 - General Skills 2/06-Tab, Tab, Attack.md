Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

### Solución
Shell

```
erik616-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
--2025-02-18 22:46:20--  https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4521 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                            100%[======================================================================================================>]   4.42K  --.-KB/s    in 0s      

2025-02-18 22:46:20 (1.29 GB/s) - 'Addadshashanammu.zip' saved [4521/4521]

erik616-picoctf@webshell:~$ ls
8#TT 1tt$DNnammu.zip  README.txt  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt
8#TT 1tt$DNnammu.zip README.txt ltdis.sh static static.ltdis.strings.txt static.ltdis.x86_64.txt 0)@k616-(;erik616-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ Archive: Addadshashanammu.zip creating: Addadshashanammu/ creating: Addadshashanammu/Almurbalarammi/ creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/ creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/ creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/ creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/ creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/ inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet erik616-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/ erik616-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ cat fang-of-haynekhtnamet HH/lib64/ld-linux-x86-64.so.2GNUGNUGے/8TN=Z= H Y h "libc.so.6puts__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_registerTMCloneTableui 1 Ht5 % @% h% H=1I^HHPTLH DH= UH H9HtHZ ]f.]@f.H=i H5b UH)HHHH?HHtH! Ht ]f]@f.= u/H= UHt H ]fDUH]fUHH=]f.DAWAVIAUATL%F UH-F SAIL)HWHt 1LLDAHH9u[]A\A]A^A_Ðf.*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}X"H0zRx Rx FJ R ?;*3$"D\RAC D|XeBBE B(H0H8M@r8A0A(B BB0 o GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.08Tt $ z @R Yx `e ~0+ : "` crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.7698__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryfang-of-haynekhtnamet.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5_edata__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.ABI-tag.note.gnu.build-id.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment

erik616-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep -i picoCTF
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```