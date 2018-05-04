---
title: Standart Türler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- __time64_t
- _diskfree_t
- _CRT_DUMP_CLIENT
- _fsize_t
- __timeb64
- File
- __utimeb64
- jmp_buf
- __finddata64_t
- _wfinddata_t
- _finddata_t
- utimbuf64
- wint_t
- wctrans_t
- wctype_t
- _HFILE
- _secerr_handler_func
- clock_t
- fpos_t
- _dev_t
- time64_t
- wfinddata64_t
- stat64
- ldiv_t
- _EXCEPTION_POINTERS
- terminate_function
- size_t
- timeb64
- tm
- _HEAPINFO
- unexpected_function
- _CrtMemState
- _se_translator_function
- sig_atomic_t
- _CRT_REPORT_HOOK
- _complex
- _w_finddatai64_t
- _timeb
- _onexit_t
- _RTC_ErrorNumber
- lconv
- _PNH
- _off_t
- ptrdiff_t
- time_t
- _FPIEEE_RECORD
- _exception
- __w_finddata64_t
- __stat64
- _utimbuf
- __utimbuf64
- div_t
- _CRT_ALLOC_HOOK
- int8_t
- uint8_t
- int16_t
- uint16_t
- int32_t
- uint32_t
- int64_t
- int_least8_t
- uint_least8_t
- int_least16_t
- uint_least16_t
- int_least32_t
- uint_least32_t
- int_least64_t
- uint_least64_t
- int_fast8_t
- uint_fast8_t
- int_fast16_t
- uint_fast16_t
- int_fast32_t
- uint_fast32_t
- int_fast64_t
- uint_fast64_t
- intmax_t
- uintmax_t
dev_langs:
- C++
helpviewer_keywords:
- __timeb64 type
- tm type
- clock_t type
- intptr_t type
- diskfree_t type
- wctype_t type
- CRT_DUMP_CLIENT type
- sig_atomic_t type
- _PNH type
- time_t type
- wfinddata_t type
- timeb64
- CRT, standard types
- wint_t type
- _RTC_ErrorNumber type
- _diskfree_t type
- _dev_t type
- _wfinddata_t type
- HFILE type
- __utimbuf64 type
- div_t type
- _onexit_t type
- _secerr_handler_func type
- FPIEEE_RECORD type
- HEAPINFO type
- PNH type
- _CRT_ALLOC_HOOK type
- _se_translater_function type
- va_list type
- wctrans_t type
- secerr_handler_func type
- _locale_t type
- timeb type
- lconv type
- utimbuf type
- dev_t type
- unexpected_function typedef
- _complex type
- _off_t type
- off_t type
- RTC_ErrorNumber type
- _FPIEEE_RECORD type
- exception type
- _CRT_REPORT_HOOK type
- _HEAPINFO type
- ldiv_t type
- terminate_function type
- uintptr_t type
- _CRT_DUMP_CLIENT type
- _utimbuf type
- wfinddatai64_t type
- fpos_t type
- wchar_t type
- CRT_ALLOC_HOOK type
- _HFILE type
- __time64_t type
- _timeb type
- CrtMemState type
- __finddata64_t type
- _exception type
- stat type
- onexit_t type
- FILE constant
- _stat type
- finddata_t type
- __wfinddata64_t type
- ptrdiff_t type
- complex types
- _wfinddatai64_t type
- _EXCEPTION_POINTERS type
- jmp_buf type
- se_translater_function type
- size_t type
- EXCEPTION_POINTERS type
- __stat64 type
- _fsize_t type
- CRT_REPORT_HOOK type
- _finddata_t type
ms.assetid: 23312dd2-4a6a-4d70-9b48-2a5d0d8c9f28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a66b351ba03ad6d8afb9d7423a2d1833eec8e2b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="standard-types"></a>Standart Türler
Microsoft çalışma zamanı kitaplığı aşağıdaki standart türler ve tür tanımları tanımlar.  
  
### <a name="fixed-width-integral-types-stdinth"></a>Sabit genişlikte tam sayı türleri (stdint.h)  
  
|Ad|Eşdeğer yerleşik türü|  
|----------|-------------------------------|  
|int8\_t, uint8\_t|İmzalı char, imzasız char|  
|int16\_t, uint16\_t|kısa, kısa imzalanmamış|  
|Int32\_t, uint32\_t|int, imzasız int|  
|int64\_t, uint64\_t|uzun uzun, imzasız long long|  
|int_least8_t, uint_least8_t|İmzalı char, imzasız char|  
|int_least16_t, uint_least16_t|kısa, kısa imzalanmamış|  
|int_least32_t, uint_least32_t|int, imzasız int|  
|int_least64_t, uint_least64_t|uzun uzun, imzasız long long|  
|int_fast8_t, uint_fast8_t|İmzalı char, imzasız char|  
|int_fast16_t, uint_fast16_t|int, imzasız int|  
|int_fast32_t, uint_fast32_t|int, imzasız int|  
|int_fast64_t, uint_fast64_t|uzun uzun, imzasız long long|  
|intmax_t, uintmax_t|uzun uzun, imzasız long long|  
  
|Tür|Açıklama|Şurada bildirilir:|  
|----------|-----------------|-----------------|  
|`clock_t` (uzun)|Depoları saat değerlerine; tarafından kullanılan [saat](../c-runtime-library/reference/clock.md).|TIME.H|  
|`_complex` yapısı|Karmaşık numaralar gerçek ve sanal bölümlerini depolar; tarafından kullanılan [_cabs](../c-runtime-library/reference/cabs.md).|MATH.H|  
|`_CRT_ALLOC_HOOK`|Kullanıcı tanımlı kanca işlevini tanımlayan tür. Kullanılan [_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md).|CRTDBG.H|  
|`_CRT_DUMP_CLIENT`,<br /><br /> `_CRT_DUMP_CLIENT_M`|Tür tanımlama çağrılmadığı bir geri arama işlevi için [_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md).|CRTDBG.H|  
|`_CrtMemState` yapısı|C çalışma zamanı hata ayıklama yığınının geçerli durumu hakkında bilgi sağlar.|CRTDBG.H|  
|`_CRT_REPORT_HOOK`,<br /><br /> `_CRT_REPORT_HOOKW`,<br /><br /> `_CRT_REPORT_HOOKW_M`|Tür tanımlama çağrılmadığı bir geri arama işlevi için [_CrtDbgReport](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).<br /><br /> Bu işlevin parametreleri: rapor türü, çıktı iletisi ve geri arama işlevinin dönüş değeri.|CRTDBG.H|  
|`dev_t`, `_dev_t` kısa veya işaretsiz tamsayı|Cihaz tanıtıcılarını temsil eder.|SYS\TYPES.H|  
|`_diskfree_t` yapısı|Bir disk sürücüsü hakkında bilgi içerir. Tarafından kullanılan [_getdiskfree](../c-runtime-library/reference/getdiskfree.md)**.**|DOS.H ve DIRECT.H|  
|`div_t`, `ldiv_t` ve `lldiv_t` yapıları|Depolama tarafından döndürülen değer [div](../c-runtime-library/reference/div.md), [ldiv](../c-runtime-library/reference/ldiv-lldiv.md), ve [lldiv](../c-runtime-library/reference/ldiv-lldiv.md)sırasıyla.|STDLIB.H|  
|`errno_t` tamsayı|İşlev dönüş türü veya hata kodlarını ile ilgilenir parametresi için kullanılan `errno`.|STDDEF.H,<br /><br /> CRTDEFS.H|  
|`_exception` yapısı|Hata bilgileri için depolar [_matherr](../c-runtime-library/reference/matherr.md).|MATH.H|  
|`_EXCEPTION_POINTERS`|Bir özel durum kaydı içerir. Bkz: [exceptıon_poınters](http://msdn.microsoft.com/library/windows/desktop/ms679331) daha fazla bilgi için.|FPIEEE.H|  
|`FILE` yapısı|Akış geçerli durumuyla ilgili bilgileri depolar; tüm G/Ç işlemlerinde kullanılır.|STDIO.H|  
|`_finddata_t`, `_wfinddata_t`, `_finddata32_t`, `_wfinddata32_t`, `_finddatai64_t`, `_wfinddatai64_t`, `__finddata64_t`, `__wfinddata64_t`, `__finddata32i64_t`, `__wfinddata32i64_t`, `__finddata64i32_t`, `__wfinddata64i32_t` yapıları|Depolama dosya öznitelik bilgileri tarafından döndürülen [_findfirst, _wfindfirst, ilgili işlevleri ve](../c-runtime-library/reference/findfirst-functions.md) ve [_findnext, _wfindnext ve ilgili işlevleri](../c-runtime-library/reference/findnext-functions.md). Bkz: [Filename arama işlevleri](../c-runtime-library/filename-search-functions.md) Yapı üyeleri hakkında bilgi için.|IO.H, WCHAR.H|  
|`_FPIEEE_RECORD` yapısı|IEEE kayan nokta özel durumu için ilgili bilgiler içerir. Kullanıcı tanımlı tuzak işleyici tarafından geçirilen [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md).|FPIEEE.H|  
|`fpos_t` (uzun tamsayı `__int64`, veya hedef platforma bağlı olarak yapısı)|Tarafından kullanılan [fgetpos](../c-runtime-library/reference/fgetpos.md) ve [fsetpos](../c-runtime-library/reference/fsetpos.md) benzersiz olarak her bir dosya konumlarını belirtme bilgileri kaydetmek için.|STDIO.H|  
|`_fsize_t` (imzasız uzun tamsayı)|Bir dosyanın boyutunu göstermek için kullanılır.|IO.H,<br /><br /> WCHAR.H|  
|`_HEAPINFO` yapısı|Sonraki yığın girişi hakkında bilgi içeren [_heapwalk](../c-runtime-library/reference/heapwalk.md).|MALLOC.H|  
|`_HFILE` (void *)|Bir işletim sisteminin dosya tanıtıcısı.|CRTDBG.H|  
|`imaxdiv_t`|Tarafından döndürülen değerin türü [imaxdiv](../c-runtime-library/reference/imaxdiv.md) sayının ve kalanı içeren işlev.|inttypes.h|  
|`ino_t`, `_ino_t` (kısa imzasız)|Durum bilgilerini döndürmek için.|WCHAR.H|  
|`intmax_t`|Herhangi işaretli tamsayı türünün herhangi bir değerini gösterebilen işaretli bir tamsayı türü.|stdint.h|  
|`intptr_t` (uzun tamsayı veya `__int64`hedef platformu bağlı olarak)|Win32 ve Win64 platformlarda bir işaretçi (veya TANITICI) depolar.|STDDEF.H ve diğer ekleme kodu dosyaları|  
|`jmp_buf` Dizi|Tarafından kullanılan [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) kaydetmek ve program ortamı geri yüklemek için.|SETJMP.H|  
|`lconv` yapısı|Farklı ülkelerde/bölgelerde sayısal değerlere yönelik biçimlendirme kuralları içerir. Tarafından kullanılan [localeconv](../c-runtime-library/reference/localeconv.md).|LOCALE.H|  
|`_LDOUBLE`,<br /><br /> `_LONGDOUBLE`,<br /><br /> `_LDBL12` (uzun çift veya imzasız char dizi)|Büyük çift değer göstermek için kullanın.|STDLIB.H|  
|`_locale_t` yapısı|Geçerli yerel ayar değerlerini saklar; tüm yerel ayarlara özgü C çalışma zamanı kitaplıklarında kullanılır.|CRTDEF.H|  
|`mbstate_t`|Çok baytlı bir karakter dönüştürme durumunu izler.|WCHAR.H|  
|`off_t`, `_off_t` uzun tamsayı|Dosya uzaklığı değerini gösterir.|WCHAR.H, SYS\TYPES.H|  
|`_onexit_t`,<br /><br /> `_onexit_m_t` İşaretçi|Tarafından döndürülen [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md).|STDLIB.H|  
|`_PNH` İşlev işaretçisi|Bağımsız değişken türü [_set_new_handler](../c-runtime-library/reference/set-new-handler.md).|NEW.H|  
|`ptrdiff_t` (uzun tamsayı veya `__int64`hedef platformu bağlı olarak)|İki işaretçinin çıkarılmasının sonucu.|CRTDEFS.H|  
|`_purecall_handler`,<br /><br /> `_purecall_handler_m`|Saf sanal bir işlev çağrıldığında çağrılan geri arama işlevini tanımlayan tür. Tarafından kullanılan [_get_purecall_handler, _set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md). A `_purecall_handler` işlevi geçersiz bir dönüş türüne sahip olmalıdır.|STDLIB.H|  
|`_RTC_error_fn` türünü tanımlayın|Çalışma zamanı hata denetimlerini işleyecek olan bir işlevi tanımlayan tür. Kullanılan [_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md).|RTCAPI.H|  
|`_RTC_error_fnW` türünü tanımlayın|Çalışma zamanı hata denetimlerini işleyecek olan bir işlevi tanımlayan tür. Kullanılan [_RTC_SetErrorFuncW](../c-runtime-library/reference/rtc-seterrorfuncw.md).|RTCAPI.H|  
|`_RTC_ErrorNumber` Numaralandırması|Hata koşulları için tanımlar [_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md) ve [_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md).|RTCAPI.H|  
|`_se_translator_function`|Bir özel durumu çeviren geri arama işlevini tanımlayan tür. İlk parametre özel durum kodu, ikinci parametre özel durum kaydıdır. Tarafından kullanılan [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).|EH.H|  
|`sig_atomic_t` tamsayı|Atomik bir varlık olarak bile zaman uyumsuz kesmeler bulunması değiştirilebilir nesnesinin türü; ile kullanılan [sinyal](../c-runtime-library/reference/signal.md).|SIGNAL.H|  
|`size_t` (imzasız __int64 ya da hedef platforma bağlı olarak imzalanmamış tamsayı)|Sonucu `sizeof` işleci.|CRTDEFS.H ve diğer ekleme kodu dosyaları|  
|`_stat` yapısı|Tarafından döndürülen dosya durum bilgisi içeren [_stat](../c-runtime-library/reference/stat-functions.md) ve [_fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md).|SYS\STAT.H|  
|`__stat64` yapısı|Tarafından döndürülen dosya durum bilgisi içeren [_fstat64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) ve [_stat64](../c-runtime-library/reference/stat-functions.md), ve [_wstat64](../c-runtime-library/reference/stat-functions.md).|SYS\STAT.H|  
|`_stati64` yapısı|Tarafından döndürülen dosya durum bilgisi içeren [_fstati64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [_stati64](../c-runtime-library/reference/stat-functions.md), ve [_wstati64](../c-runtime-library/reference/stat-functions.md).|SYS\STAT.H|  
|`terminate_function` türünü tanımlayın|Tür tanımlama aldığında çağrılan bir geri arama işlevi için [sonlandırmak](../c-runtime-library/reference/terminate-crt.md) olarak adlandırılır. Tarafından kullanılan [set_terminate](../c-runtime-library/reference/set-terminate-crt.md).|EH.H|  
|`time_t` (__int64 veya uzun tamsayı)|Saat değerleri temsil [mktime](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [zaman](../c-runtime-library/reference/time-time32-time64.md), [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _ wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) ve [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md). Ocak 1, 1970, 0:00 UTC tarihinden beri geçen saniye sayısı. _USE_32BIT_TIME_T tanımlanmışsa `time_t` uzun bir tamsayıdır. Tanımlı değilse, 64-bit bir tamsayıdır.|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|  
|`__time32_t` (uzun tamsayı)|Saat değerleri temsil [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _ wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) ve [damgasını, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md).|CRTDEFS.H, SYS\STAT.H,<br /><br /> SYS\TIMEB.H|  
|`__time64_t` (`__int64`)|Saat değerleri temsil [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [_ctime64, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md) ve [_time64](../c-runtime-library/reference/time-time32-time64.md).|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|  
|`_timeb` yapısı|Tarafından kullanılan [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) geçerli sistem saatinin depolamak için.|SYS\TIMEB.H|  
|`__timeb32` yapısı|Tarafından kullanılan [_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) geçerli sistem saatinin depolamak için.|SYS\TIMEB.H|  
|`__timeb64` yapısı|Tarafından kullanılan [_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) geçerli sistem saatinin depolamak için.|SYS\TIMEB.H|  
|`tm` yapısı|Tarafından kullanılan [asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md), [gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime_s, _gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), [damgasını, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), [mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md) ve [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) saat bilgilerini depolamak ve almak için.|TIME.H|  
|`uintmax_t`|Herhangi işaretsiz tamsayı türünün herhangi bir değerini gösterebilen işaretsiz bir tamsayı türü.|stdint.h|  
|`uintptr_t` (uzun tamsayı veya `__int64`hedef platformu bağlı olarak)|İmzasız tam sayı veya imzasız __int64 sürümü `intptr_t`.|STDDEF.H ve diğer ekleme kodu dosyaları|  
|`unexpected_function`|Tür tanımlama aldığında çağrılan bir geri arama işlevi için [beklenmeyen](../c-runtime-library/reference/unexpected-crt.md) olarak adlandırılır. Tarafından kullanılan [set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md).|EH.H|  
|`_utimbuf` yapısı|Depoları dosya tarafından kullanılan erişim ve değişiklik zamanları [_utime, _wutime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md) dosya değişikliği tarihleri değiştirmek için.|SYS\UTIME.H|  
|`_utimbuf32` yapısı|Depoları dosya tarafından kullanılan erişim ve değişiklik zamanları [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime, _futime32, _futime64](../c-runtime-library/reference/futime-futime32-futime64.md) dosya değişikliği tarihleri değiştirmek için.|SYS\UTIME.H|  
|`__utimbuf64` yapısı|Tarafından kullanılan [_utime64, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) geçerli saati depolamak için.|SYS\UTIME.H|  
|`va_list` yapısı|Gerekli bilgiyi tutmak için kullanılan [va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) ve [va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) makroları. Çağrılan işlev türünde değişken bildirir `va_list` , geçirilebilir bağımsız değişken olarak başka bir işlev.|STDARG.H,<br /><br /> CRTDEFS.H|  
|`wchar_t` Geniş karakter|Uluslararası pazarlar için taşınabilir programlar yazarken faydalıdır.|STDDEF.H, STDLIB.H,<br /><br /> CRTDEFS.H,<br /><br /> SYS\STAT.H|  
|`wctrans_t` tamsayı|Yerel ayara özgü karakter eşlemelerini temsil eder.|WCTYPE.H|  
|`wctype_t` tamsayı|Herhangi bir dil karakter kümesinin tüm karakterlerini temsil edebilir.|WCHAR.H,<br /><br /> CRTDEFS.H|  
|`wint_t` tamsayı|Herhangi bir geniş karakter veya geniş dosya sonu değerini tutabilen veri nesnesinin türü.|WCHAR.H,<br /><br /> CRTDEFS.H|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
