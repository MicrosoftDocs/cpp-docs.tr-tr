---
title: Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri
description: Evrensel Windows Platformu uygulamalarında desteklenen CRT işlevlerine yönelik başvuru kılavuzu.
ms.date: 04/16/2020
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
ms.openlocfilehash: 793283a5c20f04e58de22fcfca5ede1926de369c
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041841"
---
# <a name="crt-functions-not-supported-in-universal-windows-platform-apps"></a>Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri

Evrensel Windows Platformu (UWP) uygulamaları oluştururken birçok C Runtime (CRT) işlevi kullanılamaz. Bazen geçici çözümler kullanılabilir — Örneğin, Windows Çalışma Zamanı veya Win32 API 'Leri kullanabilirsiniz. Diğer durumlarda, ilgili özellikler veya destekleyici API 'Ler UWP uygulamaları için geçerli olmadığından CRT işlevleri yasaklanmış. Windows Çalışma Zamanı için desteklenen alternatif bir yöntemi aramak için bkz. [UWP uygulamalarında Windows API 'Lerinin alternatifleri](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Aşağıdaki tabloda, UWP uygulamaları oluştururken kullanılamayan CRT işlevleri listelenmektedir. Bu, uygulanan tüm geçici çözümleri gösterir.

## <a name="unsupported-crt-functions"></a>Desteklenmeyen CRT Işlevleri

| İşlev | Açıklama | Geçici çözüm |
|-|-|-|
|`_beep` `_sleep` `_seterrormode`|Bu işlevler, önceki CRT sürümlerinde kullanılmıyor. Ayrıca, ilgili Win32 API 'Leri UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|`chdir` `_chdrive` `getcwd`|Bu işlevler artık kullanılmıyor veya iş parçacığı açısından güvenli değildir.|Kullanın `_chdir` `_getcwd` ve ilgili işlevleri.|
|`_cgets` `_cgets_s` `_cgetws` `_cgetws_s` `_cprintf` `_cprintf_l` `_cprintf_p` `_cprintf_p_l` `_cprintf_s` `_cprintf_s_l` `_cputs` `_cputws` `_cscanf` `_cscanf_l` `_cscanf_s` `_cscanf_s_l` `_cwait` `_cwprintf` `_cwprintf_l` `_cwprintf_p` `_cwprintf_p_l` `_cwprintf_s` `_cwprintf_s_l` `_cwscanf` `_cwscanf_l` `_cwscanf_s` `_cwscanf_s_l` `_vcprintf` `_vcprintf_l` `_vcprintf_p` `_vcprintf_p_l` `_vcprintf_s` `_vcprintf_s_l` `_vcwprintf` `_vcwprintf_l` `_vcwprintf_p` `_vcwprintf_p_l` `_vcwprintf_s` `_vcwprintf_s_l` `_getch` `_getch_nolock` `_getche` `_getche_nolock` `_getwch` `_getwch_nolock` `_getwche` `_getwche_nolock` `_putch` `_putch_nolock` `_putwch` `_putwch_nolock` `_ungetch` `_ungetch_nolock` `_ungetwch` `_ungetwch_nolock` `_kbhit` `kbhit` `putch` `cgets` `cprintf` `cputs` `cscanf` `cwait` `getch` `getche` `ungetch`|Bu işlevler, doğrudan ve konsolu arasında okumak ve yazmak için kullanılır. UWP uygulamaları yalnızca GUI amaçlıdır; Konsol desteği yoktur.|Geçici çözüm yok.|
|`getpid` `_getpid` | Bu işlevler artık kullanılmıyor.|Win32 API kullanın `GetCurrentProcessId` .|
|`_getdiskfree`|Kullanılamıyor.|Win32 API kullanın `GetDiskFreeSpaceExW` .|
|`_getdrive` `_getdrives`|İlgili API, UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|`_inp` `_inpd` `_inpw` `_outp` `_outpd` `_outpw` `inp` `inpd` `inpw` `outp` `outpd` `outpw`|UWP uygulamalarında bağlantı noktası GÇ desteklenmez.|Geçici çözüm yok.|
|`_ismbcalnum` `_ismbcalnum_l` `_ismbcalpha` `_ismbcalpha_l` `_ismbcdigit` `_ismbcdigit_l` `_ismbcgraph` `_ismbcgraph_l` `_ismbchira` `_ismbchira_l` `_ismbckata` `_ismbckata_l` `_ismbcl0` `_ismbcl0_l` `_ismbcl1` `_ismbcl1_l` `_ismbcl2` `_ismbcl2_l` `_ismbclegal` `_ismbclegal_l` `_ismbclower` `_ismbclower_l` `_ismbcprint` `_ismbcprint_l` `_ismbcpunct` `_ismbcpunct_l` `_ismbcspace` `_ismbcspace_l` `_ismbcsymbol` `_ismbcsymbol_l` `_ismbcupper` `_ismbcupper_l` `_mbbtombc` `_mbbtombc_l` `_mbbtype` `_mbbtype_l` `_mbccpy` `_mbccpy_l` `_mbccpy_s` `_mbccpy_s_l` `_mbcjistojms` `_mbcjistojms_l` `_mbcjmstojis` `_mbcjmstojis_l` `_mbclen` `_mbclen_l` `_mbctohira` `_mbctohira_l` `_mbctokata` `_mbctokata_l` `_mbctolower` `_mbctolower_l` `_mbctombb` `_mbctombb_l` `_mbctoupper` `_mbctoupper_l` `_mbsbtype` `_mbsbtype_l` `_mbscat` `_mbscat_l` `_mbscat_s` `_mbscat_s_l` `_mbschr` `_mbschr_l` `_mbscmp` `_mbscmp_l` `_mbscoll` `_mbscoll_l` `_mbscpy` `_mbscpy_l` `_mbscpy_s` `_mbscpy_s_l` `_mbscspn` `_mbscspn_l` `_mbsdec` `_mbsdec_l` `_mbsicmp` `_mbsicmp_l` `_mbsicoll` `_mbsicoll_l` `_mbsinc` `_mbsinc_l` `_mbslen` `_mbslen_l` `_mbslwr` `_mbslwr_l` `_mbslwr_s` `_mbslwr_s_l` `_mbsnbcat` `_mbsnbcat_l` `_mbsnbcat_s` `_mbsnbcat_s_l` `_mbsnbcmp` `_mbsnbcmp_l` `_mbsnbcnt` `_mbsnbcnt_l` `_mbsnbcoll` `_mbsnbcoll_l` `_mbsnbcpy` `_mbsnbcpy_l` `_mbsnbcpy_s` `_mbsnbcpy_s_l` `_mbsnbicmp` `_mbsnbicmp_l` `_mbsnbicoll` `_mbsnbicoll_l` `_mbsnbset` `_mbsnbset_l` `_mbsnbset_s` `_mbsnbset_s_l` `_mbsncat` `_mbsncat_l` `_mbsncat_s` `_mbsncat_s_l` `_mbsnccnt` `_mbsnccnt_l` `_mbsncmp` `_mbsncmp_l` `_mbsncoll` `_mbsncoll_l` `_mbsncpy` `_mbsncpy_l` `_mbsncpy_s` `_mbsncpy_s_l` `_mbsnextc` `_mbsnextc_l` `_mbsnicmp` `_mbsnicmp_l` `_mbsnicoll` `_mbsnicoll_l` `_mbsninc` `_mbsninc_l` `_mbsnlen` `_mbsnlen_l` `_mbsnset` `_mbsnset_l` `_mbsnset_s` `_mbsnset_s_l` `_mbspbrk` `_mbspbrk_l` `_mbsrchr` `_mbsrchr_l` `_mbsrev` `_mbsrev_l` `_mbsset` `_mbsset_l` `_mbsset_s` `_mbsset_s_l` `_mbsspn` `_mbsspn_l` `_mbsspnp` `_mbsspnp_l` `_mbsstr` `_mbsstr_l` `_mbstok` `_mbstok_l` `_mbstok_s` `_mbstok_s_l` `_mbsupr` `_mbsupr_l` `_mbsupr_s` `_mbsupr_s_l` `is_wctype`|Çoklu bayt dizeleri UWP uygulamalarında desteklenmez.|Bunun yerine Unicode dizeleri kullanın.|
|`_pclose` `_pipe` `_popen` `_wpopen`|Kanal işlevselliği UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|`_resetstkoflw`|UWP uygulamaları için Win32 API 'Leri destekleme kullanılamaz.|Geçici çözüm yok.|
|`_getsystime` `_setsystime`|Önceki CRT sürümlerindeki bu kullanılmayan API 'Ler vardı. Ayrıca, bir Kullanıcı, izin eksikliği nedeniyle UWP uygulamasında sistem saatini ayarlayaamaz.|Yalnızca sistem saatini almak için Win32 API kullanın `GetSystemTime` . Sistem saati ayarlanamıyor.|
|`_environ``_putenv` `_putenv_s` `_searchenv` `_searchenv_s` `_dupenv_s` `_wputenv` `_wputenv_s` `_wsearchenv` getenv getenv_s `_wdupenv_s` `_wenviron` `_wgetenv` `_wgetenv_s` putenv `_wsearchenv_s``tzset`|Ortam değişkenleri UWP uygulamaları için kullanılamaz.|Geçici çözüm yok. Saat dilimini ayarlamak için kullanın `_tzset` .|
|`_loaddll` `_getdllprocaddr` `_unloaddll`|Bunlar önceki CRT sürümlerindeki eski işlevlerdi. Ayrıca, bir kullanıcı aynı uygulama paketinden olanlar hariç dll 'Leri yükleyemez.|`LoadPackagedLibrary` `GetProcAddress` `FreeLibrary` Paketlenmiş DLL 'leri yüklemek ve kullanmak Için Win32 API 'leri kullanın.|
|`_wexecl` `_wexecle` `_wexeclp` `_wexeclpe` `_wexecv` `_wexecve` `_wexecvp` `_wexecvpe` `_execl` `_execle` `_execlp` `_execlpe` `_execv` `_execve` `_execvp` `_execvpe` `_spawnl` `_spawnle` `_spawnlp` `_spawnlpe` `_spawnv` `_spawnve` `_spawnvp` `_spawnvpe` `_wspawnl` `_wspawnle` `_wspawnlp` `_wspawnlpe` `_wspawnv` `_wspawnve` `_wspawnvp` `_wspawnvpe` `_wsystem` `execl` `execle` `execlp` `execlpe` `execv` `execve` `execvp` `execvpe` `spawnl` `spawnle` `spawnlp` `spawnlpe` `spawnv` `spawnve` `spawnvp` `spawnvpe` `system`|İşlevler UWP uygulamalarında kullanılamaz. UWP uygulaması başka bir UWP uygulaması veya masaüstü uygulaması çağrılamaz.|Geçici çözüm yok.|
|`_heapwalk` `_heapadd` `_heapchk` `_heapset` `_heapused`|Bu işlevler genellikle yığın ile çalışmak için kullanılır. Ancak, UWP uygulamalarında ilgili Win32 API 'Leri desteklenmez. Uygulamalar artık özel Heap 'ler oluşturamaz veya kullanamaz.|Geçici çözüm yok. Ancak, hata ayıklama `_heapwalk` CRT ' de yalnızca hata ayıklama amacıyla kullanılabilir. Bu işlevler Microsoft Store yüklenen uygulamalarda kullanılamaz.|

UWP uygulamalarında CRT ' de aşağıdaki işlevler bulunur. Ancak, bunları yalnızca, büyük kod tabanlarında olduğu gibi, karşılık gelen Win32 veya Windows Çalışma Zamanı API 'Lerini kullanamıyoruz kullanın:

| İşlevler | Geçici çözüm |
|-|-|
|Tek baytlık dize işlevleri — Örneğin,,, `strcat` vb `strcpy` `strlwr` .|Tüm Win32 API 'Leri ve sunulan Windows Çalışma Zamanı API 'Leri yalnızca Unicode karakter kümelerini kullandığından, UWP uygulamalarınızı tamamen Unicode yapın.  Büyük kod temellerine yönelik tek baytlı işlevler kalmadı, ancak Aksi takdirde bu işlemler kaçınılmalıdır. Karşılık gelen geniş char işlevleri mümkünse bunun yerine kullanılmalıdır.|
|Stream ıO ve alt düzey dosya GÇ işlevleri — Örneğin,,, `fopen` vb `open` .|Bu işlevler, UWP uygulamaları için önerilmeyen zaman uyumludur. UWP uygulamalarınızda, UI iş parçacığının kilitlenmesini engellemek için dosyaları açmak, okumak ve yazmak üzere zaman uyumsuz API 'Ler kullanın. Bu tür API örnekleri `Windows::Storage::FileIO` sınıfınlardır.|

## <a name="windows-8x-store-apps-and-windows-phone-8x-apps"></a>Windows 8. x Mağazası uygulamaları ve Windows Phone 8. x uygulamaları

Hem önceden bahsedilen API 'Ler hem de aşağıdaki API 'Ler Windows 8. x Mağazası uygulamaları ve Windows Phone 8. x uygulamalarında kullanılamaz.

| İşlevler | Description | Geçici çözüm |
|-|-|-|
|`_beginthread` `_beginthreadex` `_endthread` `_endthreadex`|Windows 8. x Mağaza uygulamalarında iş parçacığı Win32 API 'Leri kullanılamaz.|`Windows Runtime Windows::System::Threading::ThreadPool` `concurrency::task` Bunun yerine veya kullanın.|
|`_chdir` `_wchdir` `_getcwd` `_getdcwd` `_wgetcwd` `_wgetdcwd`|Çalışma dizini kavramı, Windows 8. x Mağazası uygulamaları için geçerlidir.|Bunun yerine tam yolları kullanın.|
|`_isleadbyte_l` `_ismbbalnum`, `_ismbbalnum_l`, `_ismbbalpha`, `_ismbbalpha` `_ismbbalpha_l` `_ismbbgraph` `_ismbbgraph_l` `_ismbbkalnum` `_ismbbkalnum_l` `_ismbbkana` `_ismbbkana_l` `_ismbbkprint` `_ismbbkprint_l` `_ismbbkpunct` `_ismbbkpunct_l` `_ismbblead` `_ismbblead_l` `_ismbbprint` `_ismbbprint_l` `_ismbbpunct` `_ismbbpunct_l` `_ismbbtrail` `_ismbbtrail_l` `_ismbslead` `_ismbslead_l` `_ismbstrail` `_ismbstrail_l` `_mbsdup` `isleadbyte`|Çoklu baytlık dizeler Windows 8. x Mağaza uygulamalarında desteklenmez.|Bunun yerine Unicode dizeleri kullanın.|
|`_tzset`|Ortam değişkenleri Windows 8. x Mağazası uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|`_get_heap_handle`, `_heapmin`|Karşılık gelen Win32 API 'Leri, Windows 8. x Mağaza uygulamalarında desteklenmez. Uygulamalar artık özel Heap 'ler oluşturamaz.|Geçici çözüm yok. Ancak, hata ayıklama ``_get_heap_handle`` CRT ' de yalnızca hata ayıklama amacıyla kullanılabilir.|
