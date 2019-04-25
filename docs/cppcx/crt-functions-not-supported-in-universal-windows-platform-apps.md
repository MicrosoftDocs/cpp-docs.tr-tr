---
title: Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri
ms.date: 12/30/2016
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
ms.openlocfilehash: 763d76dd9eb139c10f4147e5fa069a0901fe5398
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188388"
---
# <a name="crt-functions-not-supported-in-universal-windows-platform-apps"></a>Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri

Evrensel Windows Platformu (UWP) uygulamaları oluştururken çok sayıda C çalışma zamanı (CRT) işlevleri kullanılamaz. Bazı durumlarda, geçici çözümler kullanılabilir —-örneğin, Windows çalışma zamanı veya Win32 API'larını kullanabilirsiniz. Bunları veya destekleyici API'leri için karşılık gelen özellikleri UWP uygulamaları için geçerli olmadığından ancak diğer durumlarda, CRT işlevleri yasaklanmış. Windows çalışma zamanı için desteklenen alternatif bir yöntem aramak için bkz: [UWP uygulamalarında Windows API'lere alternatifler](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Aşağıdaki tabloda, UWP uygulamaları oluştururken bulunmayan CRT işlevleri listeler ve uygulama herhangi bir geçici çözüm gösterir.

## <a name="unsupported-crt-functions"></a>Desteklenmeyen CRT işlevleri

||||
|-|-|-|
|_beep _sleep _seterrormode|Bu işlevler, CRT önceki sürümleri artık kullanılmıyor. Ayrıca, karşılık gelen Win32 API'ları, UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|chdir _chdrive getcwd|Bu işlevler, artık kullanılmayan veya iş parçacığı açısından güvenli değildir.|_Chdir _getcwd ve ilgili işlevleri kullanın.|
|_cgets _cgets_s _cgetws _cgetws_s _cprintf _cprintf_l _cprintf_p _cprintf_p_l _cprintf_s _cprintf_s_l _cputs _cputws _cscanf _cscanf_l _cscanf_s _cscanf_s_l _cwait _cwprintf _cwprintf_l _cwprintf_p _cwprintf_p_l _cwprintf_s _cwprintf_s_l _cwscanf _ cwscanf_l _cwscanf_s _cwscanf_s_l _vcprintf _vcprintf_l _vcprintf_p _vcprintf_p_l _vcprintf_s _vcprintf_s_l _vcwprintf _vcwprintf_l _vcwprintf_p _vcwprintf_p_l _vcwprintf_s _vcwprintf_s_l _getch _getch_nolock _getche _getche_nolock _getwch _ getwch_nolock _getwche _getwche_nolock _putch _putch_nolock _putwch _putwch_nolock _ungetch _ungetch_nolock _ungetwch _ungetwch_nolock _kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|Bu işlevler doğrudan ve konsola okuma ve yazma için kullanılır. UWP uygulamalar, yalnızca GUI, Bunlar, konsol desteklemez.|Geçici çözüm yok.|
|getpid|Bu işlev artık kullanılmıyor.|_Getpid veya Win32 API `GetCurrentProcessId()`.|
|_getdiskfree|Kullanılabilir değil.|Win32 API kullanma `GetDiskFreeSpaceExW()`.|
|_getdrive _getdrives|Karşılık gelen API UWP uygulamaları için kullanılabilir değil.|Geçici çözüm yok.|
|_inp _inpd _inpw _outp _outpd _outpw inp inpd inpw outp outpd outpw|UWP uygulamalarında g/ç bağlantı noktası desteklenmiyor.|Geçici çözüm yok.|
|_ismbcalnum _ismbcalnum_l _ismbcalpha _ismbcalpha_l _ismbcdigit _ismbcdigit_l _ismbcgraph _ismbcgraph_l _ismbchira _ismbchira_l _ismbckata _ismbckata_l _ismbcl0 _ismbcl0_l _ismbcl1 _ismbcl1_l _ismbcl2 _ismbcl2_l _ismbclegal _ismbclegal_l _ ismbclower _ismbclower_l _ismbcprint _ismbcprint_l _ismbcpunct _ismbcpunct_l _ismbcspace _ismbcspace_l _ismbcsymbol _ismbcsymbol_l _ismbcupper _ismbcupper_l _mbbtombc _mbbtombc_l _mbbtype _mbbtype_l _mbccpy _mbccpy_l _mbccpy_s _mbccpy_s_l _ mbcjistojms _mbcjistojms_l _mbcjmstojis _mbcjmstojis_l _mbclen _mbclen_l _mbctohira _mbctohira_l _mbctokata _mbctokata_l _mbctolower _mbctolower_l _mbctombb _mbctombb_l _mbctoupper _mbctoupper_l _mbsbtype _mbsbtype_l _mbscat _mbscat_l _mbscat_s _ mbscat_s_l _mbschr _mbschr_l _mbscmp _mbscmp_l _mbscoll _mbscoll_l _mbscpy _mbscpy_l _mbscpy_s _mbscpy_s_l _mbscspn _mbscspn_l _mbsdec mbsdec_l _mbsicmp _mbsicmp_l _mbsicoll _mbsicoll_l _mbsinc _mbsinc_l _mbslen _mbslen_l _mbslwr _mbslwr_l _mbslwr_s _mbslwr_s_l _mbsnbcat _mbsnbcat_l _mbsnbcat_s _mbsnbcat_s_l _mbsnbcmp _mbsnbcmp_l _mbsnbcnt _mbsnbcnt_l _mbsnbcoll _mbsnbcoll_l _mbsnbcpy _mbsnbcpy_l _mbsnbcpy_s _mbsnbcpy_s_l _mbsnbicmp _mbsnbicmp_l _mbsnbicoll _mbsnbicoll_l _mbsnbset _mbsnbset _L _mbsnbset_s _mbsnbset_s_l _mbsncat _mbsncat_l _mbsncat_s _mbsncat_s_l _mbsnccnt _mbsnccnt_l _mbsncmp _mbsncmp_l _mbsncoll _mbsncoll_l _mbsncpy _mbsncpy_l _mbsncpy_s _mbsncpy_s_l _mbsnextc _mbsnextc_l _mbsnicmp _mbsnicmp_l _mbsnicoll _mbsnicoll_ m _mbsninc _mbsninc_l _mbsnlen _mbsnlen_l _mbsnset _mbsnset_l _mbsnset_s _mbsnset_s_l _mbspbrk _mbspbrk_l _mbsrchr _mbsrchr_l _mbsrev _mbsrev_l _mbsset _mbsset_l _mbsset_s _mbsset_s_l _mbsspn _mbsspn_l _mbsspnp _mbsspnp_l _mbsstr _mbsstr_l _mbstok _ mbstok_l _mbstok_s _mbstok_s_l _mbsupr _mbsupr_l _mbsupr_s _mbsupr_s_l is_wctype|Çok baytlı dizeleri UWP uygulamalarında desteklenmez.|Unicode dizelerini kullanın.|
|_pclose _pipe _popen _wpopen|Kanal işlevselliği UWP uygulamaları için kullanılabilir değil.|Geçici çözüm yok.|
|_resetstkoflw|Destekleyen Win32 API'ları UWP uygulamaları için kullanılabilir değil.|Geçici çözüm yok.|
|_getsystime _setsystime|Bunlar, önceki CRT sürümlerinde eski API'ler yoktu. Ayrıca, bir kullanıcı Sistem saatini bir UWP uygulamasında izinleri yetersiz olduğundan ayarlanamaz.|Yalnızca sistem saatini almak için Win32 API kullanma `GetSystemTime`. Sistem saatini ayarlanamaz.|
|_environ _putenv _putenv_s _searchenv _searchenv_s _dupenv_s _wputenv _wputenv_s _wsearchenv getenv getenv_s putenv _wdupenv_s _wenviron _wgetenv _wgetenv_s _wsearchenv_s tzset|Ortam değişkenleri UWP uygulamaları için kullanılabilir değildir.|Geçici çözüm yok. Saat dilimini ayarlamak için _tzset kullanın.|
|_loaddll _getdllprocaddr _unloaddll|Bunlar, önceki CRT sürümlerde artık kullanılmayan işlevleri yoktu. Ayrıca, kullanıcı aynı uygulama paketi dosyalardan dışında DLL yüklenemiyor.|Win32 API'larını kullanın `LoadPackagedLibrary`, `GetProcAddress`, ve `FreeLibrary` yüklemek ve paketlenmiş DLL'leri kullanma.|
|_wexecl _wexecle _wexeclp _wexeclpe _wexecv _wexecve _wexecvp _wexecvpe _execl _execle _execlp _execlpe _execv _execve _execvp _execvpe _spawnl _spawnle _spawnlp _spawnlpe _spawnv _spawnve _spawnvp _spawnvpe _wspawnl _wspawnle _wspawnlp _wspawnlpe _ wspawnv _wspawnve _wspawnvp _wspawnvpe _wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe sistem|UWP uygulamalarında işlevi kullanılamaz. Bir UWP uygulaması başka bir UWP uygulaması veya bir masaüstü uygulaması çağrılamıyor.|Geçici çözüm yok.|
|_heapwalk _heapadd _heapchk _heapset _heapused|Bu işlevler genellikle yığın ile çalışmak için kullanılır. Ancak, karşılık gelen Win32 API'ları UWP uygulamalarında desteklenmez. Ve uygulamaları, artık oluşturun veya özel yığınlar kullanın.|Geçici çözüm yok. Ancak, `_heapwalk` CRT'deki hata ayıklama hata ayıklama amacıyla yalnızca, kullanılabilir. Bunlar için Microsoft Store karşıya uygulamalarında kullanılamaz.|

Aşağıdaki işlevleri CRT UWP uygulamaları için kullanılabilir, ancak karşılık gelen bir Win32 veya Windows çalışma zamanı API'leri kullanılamaz olduğunda kullanılmalıdır — Örneğin, ne zaman, taşıma büyük kod temelleri

|||
|-|-|
|Tek baytlı dize işlevleri — Örneğin, `strcat`, `strcpy`, `strlwr`ve benzeri.|UWP uygulamalarınızın kesinlikle Unicode karakter kümeleri yalnızca Unicode tüm Win32 API'ları ve Windows çalışma zamanı API'de sunulan kullandığından.  Tek baytlı işlevleri taşıma büyük kod tabanları, ancak Aksi halde kaçınılmalıdır ve karşılık gelen geniş karakter işlevleri, bunun yerine mümkün olduğunda kullanılmalıdır kalmıştır.|
|GÇ ve düşük düzeyli dosya g/ç işlevleri Stream — Örneğin, `fopen`, `open`ve benzeri.|Bu işlevler zaman uyumlu, UWP uygulamaları için önerilmez. UWP uygulamalarınızda zaman uyumsuz API'leri kullanan açmak, okumak ve kullanıcı Arabirimi iş parçacığı kilitlenmesini önlemek için dosyalara yazma. Bu API'leri örnekler dışındaki `Windows::Storage::FileIO` sınıfı.|

## <a name="windows-8x-store-apps-and-windows-phone-8x-apps"></a>Windows 8.x Store uygulamaları ve Windows Phone 8.x uygulamaları

Daha önce bahsedilen API'lerine ek olarak, Windows 8.x Store uygulamaları ve Windows Phone 8.x uygulamalarda aşağıdaki API'leri kullanılamaz.

||||
|-|-|-|
|_beginthread _beginthreadex _endthread _endthreadex|İş parçacığı Win32 API'ları, Windows 8.x Store uygulamalarında kullanılamaz.|Kullanım `Windows Runtime Windows::System::Threading::ThreadPool` veya `concurrency::task` yerine.|
|_chdir _wchdir _getcwd _getdcwd _wgetcwd _wgetdcwd|Çalışan bir dizine kavramı, Windows 8.x Store uygulamaları için geçerli değildir.|Bunun yerine tam yolları kullan.|
|_getpid|Bu işlev CRT önceki sürümleri artık kullanılmıyor.|Win32 API kullanma `GetCurrentProcessId()`|
|_isleadbyte_l _ismbbalnum, _ismbbalnum_l, _ismbbalpha, _ismbbalpha _ismbbalpha_l _ismbbgraph _ismbbgraph_l _ismbbkalnum _ismbbkalnum_l _ismbbkana _ismbbkana_l _ismbbkprint _ismbbkprint_l _ismbbkpunct _ismbbkpunct_l _ismbblead _ismbblead_l _ ismbbprint _ismbbprint_l _ismbbpunct _ismbbpunct_l _ismbbtrail _ismbbtrail_l _ismbslead _ismbslead_l _ismbstrail _ismbstrail_l _mbsdup isleadbyte|Çok baytlı dizeleri, Windows 8.x Store uygulamalarında desteklenmez.|Unicode dizelerini kullanın.|
|_tzset|Ortam değişkenleri, Windows 8.x Store uygulamaları için kullanılabilir değildir.|Geçici çözüm yok.|
|_get_heap_handle, _heapmin|Karşılık gelen Win32 API'ları, Windows 8.x Store uygulamalarında desteklenmez. Ve uygulamaları, artık özel yığınlar oluşturabilirsiniz.|Geçici çözüm yok. Ancak, `_get_heap_handle` hata ayıklama için yalnızca hata ayıklama CRT, kullanılabilir.|