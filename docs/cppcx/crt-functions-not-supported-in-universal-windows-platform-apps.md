---
title: Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri
ms.date: 12/30/2016
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
ms.openlocfilehash: cf67cb9c0a2438ee6ac1bcc7753c0f89b63a356d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214324"
---
# <a name="crt-functions-not-supported-in-universal-windows-platform-apps"></a>Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri

Evrensel Windows Platformu (UWP) uygulamaları oluştururken birçok C Runtime (CRT) işlevi kullanılamaz. Bazı durumlarda, geçici çözümler kullanılabilir — Örneğin, Windows Çalışma Zamanı veya Win32 API 'Leri kullanabilirsiniz. Ancak, diğer durumlarda, bunlara karşılık gelen özellikler veya destekleyici API 'Ler UWP uygulamaları için geçerli olmadığından CRT işlevleri yasaklanmış. Windows Çalışma Zamanı için desteklenen alternatif bir yöntemi aramak için bkz. [UWP uygulamalarında Windows API 'Lerinin alternatifleri](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Aşağıdaki tablo, UWP uygulamaları oluştururken kullanılamayan CRT işlevlerini listeler ve uygulanan tüm geçici çözümleri gösterir.

## <a name="unsupported-crt-functions"></a>Desteklenmeyen CRT Işlevleri

||||
|-|-|-|
|_beep _sleep _seterrormode|Bu işlevler, önceki CRT sürümlerinde kullanılmıyor. Ayrıca, ilgili Win32 API 'Leri UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|chdir _chdrive getcwd|Bu işlevler artık kullanılmıyor veya iş parçacığı açısından güvenli değildir.|_Chdir, _getcwd ve ilgili işlevleri kullanın.|
|_cgets _cgets_s _cgetws _cgetws_s _cprintf _cprintf_l _cprintf_p _cprintf_p_l _cprintf_s _cprintf_s_l _cputs _cputws _cscanf _cscanf_l _cscanf_s _cscanf_s_l _cwait _cwprintf _cwprintf_l _cwprintf_p _cwprintf_p_l _cwprintf_s _cwprintf_s_l _cwscanf _ cwscanf_l _cwscanf_s _cwscanf_s_l _vcprintf _vcprintf_l _vcprintf_p _vcprintf_p_l _vcprintf_s _vcprintf_s_l _vcwprintf _vcwprintf_l _vcwprintf_p _vcwprintf_p_l _vcwprintf_s _vcwprintf_s_l _getch _getch_nolock _getche _getche_nolock _getwch _ getwch_nolock _getwche _getwche_nolock _putch _putch_nolock _putwch _putwch_nolock _ungetch _ungetch_nolock _ungetwch _ungetwch_nolock _kbhit kbhit Putch Cal cprintf cput cscanf cwait getch getche ungetch|Bu işlevler, doğrudan ve konsolu arasında okumak ve yazmak için kullanılır. UWP uygulamaları yalnızca GUI amaçlıdır; Konsol desteği yoktur.|Geçici çözüm yok.|
|getpid|Bu işlev artık kullanılmıyor.|_Getpid veya Win32 API `GetCurrentProcessId()`kullanın.|
|_getdiskfree|Kullanılamıyor.|Win32 API `GetDiskFreeSpaceExW()`kullanın.|
|_getdrive _getdrives|İlgili API, UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|_inp _inpd _inpw _outp _outpd _outpw INP ınpd ınpw outp outpd outw|UWP uygulamalarında bağlantı noktası GÇ desteklenmez.|Geçici çözüm yok.|
|_ismbcalnum _ismbcalnum_l _ismbcalpha _ismbcalpha_l _ismbcdigit _ismbcdigit_l _ismbcgraph _ismbcgraph_l _ismbchira _ismbchira_l _ismbckata _ismbckata_l _ismbcl0 _ismbcl0_l _ismbcl1 _ismbcl1_l _ismbcl2 _ismbcl2_l _ismbclegal _ismbclegal_l _ ismbclower _ismbclower_l _ismbcprint _ismbcprint_l _ismbcpunct _ismbcpunct_l _ismbcspace _ismbcspace_l _ismbcsymbol _ismbcsymbol_l _ismbcupper _ismbcupper_l _mbbtombc _mbbtombc_l _mbbtype _mbbtype_l _mbccpy _mbccpy_l _mbccpy_s _mbccpy_s_l _ mbcjistojms _mbcjistojms_l _mbcjmstojis _mbcjmstojis_l _mbclen _mbclen_l _mbctohira _mbctohira_l _mbctokata _mbctokata_l _mbctolower _mbctolower_l _mbctombb _mbctombb_l _mbctoupper _mbctoupper_l _mbsbtype _mbsbtype_l _mbscat _mbscat_l _mbscat_s _ mbscat_s_l _mbschr _mbschr_l _mbscmp _mbscmp_l _mbscoll _mbscoll_l _mbscpy _mbscpy_l _mbscpy_s _mbscpy_s_l _mbscspn _mbscspn_l _mbsdec _mbsdec_l _mbsicmp _mbsicmp_l _mbsicoll _mbsicoll_l _mbsinc _mbsinc_l _mbslen _mbslen_l _mbslwr _mbslwr_l _mbslwr_s _mbslwr_s_l _mbsnbcat _mbsnbcat_l _mbsnbcat_s _mbsnbcat_s_l _mbsnbcmp _mbsnbcmp_l _mbsnbcnt _mbsnbcnt_l _mbsnbcoll _mbsnbcoll_l _mbsnbcpy _mbsnbcpy_l _mbsnbcpy_s _mbsnbcpy_s_l _mbsnbicmp _mbsnbicmp_l _mbsnbicoll _mbsnbicoll_l _mbsnbset _mbsnbset _l _mbsnbset_s _mbsnbset_s_l _mbsncat _mbsncat_l _mbsncat_s _mbsncat_s_l _mbsnccnt _mbsnccnt_l _mbsncmp _mbsncmp_l _mbsncoll _mbsncoll_l _mbsncpy _mbsncpy_l _mbsncpy_s _mbsncpy_s_l _mbsnextc _mbsnextc_l _mbsnicmp _mbsnicmp_l _mbsnicoll _mbsnicoll_ l _mbsninc _mbsninc_l _mbsnlen _mbsnlen_l _mbsnset _mbsnset_l _mbsnset_s _mbsnset_s_l _mbspbrk _mbspbrk_l _mbsrchr _mbsrchr_l _mbsrev _mbsrev_l _mbsset _mbsset_l _mbsset_s _mbsset_s_l _mbsspn _mbsspn_l _mbsspnp _mbsspnp_l _mbsstr _mbsstr_l _mbstok _ mbstok_l _mbstok_s _mbstok_s_l _mbsupr _mbsupr_l _mbsupr_s _mbsupr_s_l is_wctype|Çoklu bayt dizeleri UWP uygulamalarında desteklenmez.|Bunun yerine Unicode dizeleri kullanın.|
|_pclose _pipe _popen _wpopen|Kanal işlevselliği UWP uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|_resetstkoflw|UWP uygulamaları için Win32 API 'Leri destekleme kullanılamaz.|Geçici çözüm yok.|
|_getsystime _setsystime|Önceki CRT sürümlerindeki bu kullanılmayan API 'Ler vardı. Ayrıca, bir Kullanıcı, izin eksikliği nedeniyle UWP uygulamasında sistem saatini ayarlayaamaz.|Yalnızca sistem saatini almak için Win32 API `GetSystemTime`kullanın. Sistem saati ayarlanamıyor.|
|_environ _putenv _putenv_s _searchenv _searchenv_s _dupenv_s _wputenv _wputenv_s _wsearchenv getenv getenv_s putenv _wdupenv_s _wenviron _wgetenv _wgetenv_s _wsearchenv_s tzset|Ortam değişkenleri UWP uygulamaları için kullanılamaz.|Geçici çözüm yok. Saat dilimini ayarlamak için _tzset kullanın.|
|_loaddll _getdllprocaddr _unloaddll|Bunlar önceki CRT sürümlerindeki eski işlevlerdi. Ayrıca, Kullanıcı aynı uygulama paketinden olanlar dışında dll 'Leri yükleyemez.|Paketlenmiş DLL 'Leri yüklemek ve kullanmak için `LoadPackagedLibrary`, `GetProcAddress`ve `FreeLibrary` Win32 API 'Lerini kullanın.|
|_wexecl _wexecle _wexeclp _wexeclpe _wexecv _wexecve _wexecvp _wexecvpe _execl _execle _execlp _execlpe _execv _execve _execvp _execvpe _spawnl _spawnle _spawnlp _spawnlpe _spawnv _spawnve _spawnvp _spawnvpe _wspawnl _wspawnle _wspawnlp _wspawnlpe _ wspawnv _wspawnve _wspawnvp _wspawnvpe _wsystem Execl execle execlp execlpe execv execve execvp execvpe ürenl spawnle ürenlp oluşturma nlpe oluşturma NV spawnve spawnvp spawnvpe System|İşlevler UWP uygulamalarında kullanılamaz. UWP uygulaması başka bir UWP uygulaması veya masaüstü uygulaması çağrılamaz.|Geçici çözüm yok.|
|_heapwalk _heapadd _heapchk _heapset _heapused|Bu işlevler genellikle yığın ile çalışmak için kullanılır. Ancak, UWP uygulamalarında ilgili Win32 API 'Leri desteklenmez. Uygulamalar artık özel Heap 'ler oluşturamaz veya kullanamaz.|Geçici çözüm yok. Ancak, hata ayıklama CRT ' de yalnızca hata ayıklama amacıyla kullanılabilir `_heapwalk`. Bunlar Microsoft Store yüklenen uygulamalarda kullanılamaz.|

Aşağıdaki işlevler UWP uygulamalarına yönelik CRT ' de kullanılabilir, ancak yalnızca ilgili Win32 veya Windows Çalışma Zamanı API 'Leri kullanılamadığı zaman kullanılmalıdır (örneğin, büyük kod tabanlarının taşıma sırasında).

|||
|-|-|
|Tek baytlı dize işlevleri — Örneğin, `strcat`, `strcpy`, `strlwr`ve benzeri.|Tüm Win32 API 'Leri ve sunulan Windows Çalışma Zamanı API 'Leri yalnızca Unicode karakter kümelerini kullandığından, UWP uygulamalarınızı tamamen Unicode yapın.  Tek baytlı işlevler büyük kod temellerine taşıma için ayrılmıştı, aksi halde kaçınılması gerekir ve buna karşılık gelen geniş char işlevleri mümkün olduğunda kullanılmalıdır.|
|Stream GÇ ve alt düzey dosya GÇ işlevleri — Örneğin, `fopen`, `open`vb.|Bu işlevler, UWP uygulamaları için önerilmeyen bir zaman uyumludur. UWP uygulamalarınızda, UI iş parçacığının kilitlenmesini engellemek için dosyaları açmak, okumak ve yazmak üzere zaman uyumsuz API 'Ler kullanın. Bu tür API örnekleri, `Windows::Storage::FileIO` sınıfındaki olanlardır.|

## <a name="windows-8x-store-apps-and-windows-phone-8x-apps"></a>Windows 8. x Mağazası uygulamaları ve Windows Phone 8. x uygulamaları

Daha önce bahsedilen API 'lere ek olarak, aşağıdaki API 'Ler Windows 8. x Mağazası uygulamaları ve Windows Phone 8. x uygulamalarında kullanılamaz.

||||
|-|-|-|
|_beginthread _beginthreadex _endthread _endthreadex|Windows 8. x Mağaza uygulamalarında iş parçacığı Win32 API 'Leri kullanılamaz.|Bunun yerine `Windows Runtime Windows::System::Threading::ThreadPool` veya `concurrency::task` kullanın.|
|_chdir _wchdir _getcwd _getdcwd _wgetcwd _wgetdcwd|Çalışma dizini kavramı, Windows 8. x Mağazası uygulamaları için geçerlidir.|Bunun yerine tam yolları kullanın.|
|_getpid|Bu işlev, CRT 'nin önceki sürümlerinde kullanılmıyor.|Win32 API kullanın `GetCurrentProcessId()`|
|_isleadbyte_l _ismbbalnum, _ismbbalnum_l, _ismbbalpha, _ismbbalpha _ismbbalpha_l _ismbbgraph _ismbbgraph_l _ismbbkalnum _ismbbkalnum_l _ismbbkana _ismbbkana_l _ismbbkprint _ismbbkprint_l _ismbbkpunct _ismbbkpunct_l _ismbblead _ismbblead_l _ ismbbprint _ismbbprint_l _ismbbpunct _ismbbpunct_l _ismbbtrail _ismbbtrail_l _ismbslead _ismbslead_l _ismbstrail _ismbstrail_l _mbsdup ıleadbyte|Çoklu baytlık dizeler Windows 8. x Mağaza uygulamalarında desteklenmez.|Bunun yerine Unicode dizeleri kullanın.|
|_tzset|Ortam değişkenleri Windows 8. x Mağazası uygulamaları için kullanılamaz.|Geçici çözüm yok.|
|_get_heap_handle, _heapmin|Karşılık gelen Win32 API 'Leri, Windows 8. x Mağaza uygulamalarında desteklenmez. Uygulamalar artık özel Heap 'ler oluşturamaz.|Geçici çözüm yok. Ancak, `_get_heap_handle` hata ayıklama CRT öğesinde yalnızca hata ayıklama amacıyla kullanılabilir.|
