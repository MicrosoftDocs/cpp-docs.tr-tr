---
description: 'Daha fazla bilgi edinin: standart türler'
title: Standart Türler
ms.date: 11/04/2016
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
ms.openlocfilehash: 49a8e877987af97e961bb32f47bd857b4eceddfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235755"
---
# <a name="standard-types"></a>Standart Türler

Microsoft çalışma zamanı kitaplığı, aşağıdaki standart türleri ve tür tanımlarını tanımlar.

### <a name="fixed-width-integral-types-stdinth"></a>Sabit genişlikli integral türler (stdint. h)

|Ad|Eşdeğer yerleşik tür|
|----------|-------------------------------|
|int8 \_ t, uint8 \_ t|işaretli char, işaretsiz karakter|
|Int16 \_ t, UI \_|kısa, işaretsiz kısa|
|Int32 \_ t, uint32 \_|int, işaretsiz int|
|Int64 \_ t, UInt64 \_|uzun uzun, imzasız uzun uzun|
|int_least8_t, uint_least8_t|işaretli char, işaretsiz karakter|
|int_least16_t, uint_least16_t|kısa, işaretsiz kısa|
|int_least32_t, uint_least32_t|int, işaretsiz int|
|int_least64_t, uint_least64_t|uzun uzun, imzasız uzun uzun|
|int_fast8_t, uint_fast8_t|işaretli char, işaretsiz karakter|
|int_fast16_t, uint_fast16_t|int, işaretsiz int|
|int_fast32_t, uint_fast32_t|int, işaretsiz int|
|int_fast64_t, uint_fast64_t|uzun uzun, imzasız uzun uzun|
|intmax_t, uintmax_t|uzun uzun, imzasız uzun uzun|

|Tür|Açıklama|Şurada bildirilir:|
|----------|-----------------|-----------------|
|`clock_t` kalacağını|Zaman değerlerini depolar; [saat](../c-runtime-library/reference/clock.md)tarafından kullanılır.|TIME.H|
|`_complex` yapısı|Karmaşık sayıların gerçek ve sanal parçalarını depolar; [_cabs](../c-runtime-library/reference/cabs.md)tarafından kullanılır.|MATH.H|
|`_CRT_ALLOC_HOOK`|Kullanıcı tanımlı kanca işlevini tanımlayan tür. [_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)' de kullanılır.|CRTDBG.H|
|`_CRT_DUMP_CLIENT`,<br /><br /> `_CRT_DUMP_CLIENT_M`|Bir tür, [_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)çağrılan geri çağırma işlevini tanımlar.|CRTDBG.H|
|`_CrtMemState` yapısı|C çalışma zamanı hata ayıklama yığınının geçerli durumu hakkında bilgi sağlar.|CRTDBG.H|
|`_CRT_REPORT_HOOK`,<br /><br /> `_CRT_REPORT_HOOKW`,<br /><br /> `_CRT_REPORT_HOOKW_M`|Bir tür, [_CrtDbgReport](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)çağrılan geri çağırma işlevini tanımlar.<br /><br /> Bu işlevin parametreleri: rapor türü, çıktı iletisi ve geri arama işlevinin dönüş değeri.|CRTDBG.H|
|`dev_t`, `_dev_t` Short veya işaretsiz tamsayı|Cihaz tanıtıcılarını temsil eder.|SYS\TYPES.H|
|`_diskfree_t` yapısı|Bir disk sürücüsü hakkında bilgi içerir. [_Getdiskfree](../c-runtime-library/reference/getdiskfree.md)tarafından kullanılır **.**|DOS.H ve DIRECT.H|
|`div_t``ldiv_t`ve `lldiv_t` yapılar|Sırasıyla [div](reference/div.md), [ldiv](./reference/div.md)ve [lldiv](./reference/div.md)tarafından döndürülen değerleri depolayın.|STDLIB.H|
|`errno_t` gir|Hata kodlarıyla ilgilenen bir işlev dönüş türü veya parametresi için kullanılır `errno` .|STDDEF.H,<br /><br /> CRTDEFS.H|
|`_exception` yapısı|[_Matherr](../c-runtime-library/reference/matherr.md)için hata bilgilerini depolar.|MATH.H|
|`_EXCEPTION_POINTERS`|Bir özel durum kaydı içerir. Daha fazla bilgi için bkz. [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) .|FPIEEE.H|
|`FILE` yapısı|Akış geçerli durumuyla ilgili bilgileri depolar; tüm G/Ç işlemlerinde kullanılır.|STDIO.H|
|`_finddata_t`, `_wfinddata_t` , `_finddata32_t` , `_wfinddata32_t` , `_finddatai64_t` , `_wfinddatai64_t` , `__finddata64_t` , `__wfinddata64_t` , `__finddata32i64_t` , `__wfinddata32i64_t` , `__finddata64i32_t` , `__wfinddata64i32_t` yapıları|[_Findfirst, _wfindfirst ve ilgili işlevler](../c-runtime-library/reference/findfirst-functions.md) ve [_findnext, _wfindnext ve ilgili işlevler](../c-runtime-library/reference/findnext-functions.md)tarafından döndürülen dosya öznitelik bilgilerini depolayın. Yapı üyeleri hakkında bilgi için bkz. [dosya adı arama işlevleri](../c-runtime-library/filename-search-functions.md) .|IO.H, WCHAR.H|
|`_FPIEEE_RECORD` yapısı|IEEE kayan nokta özel durumuyla ilgili bilgiler içerir; [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)tarafından Kullanıcı tanımlı tuzak işleyicisine geçildi.|FPIEEE.H|
|`fpos_t` ( **`__int64`** hedef platforma bağlı olarak uzun tamsayı, veya yapı)|Bir dosya içindeki her konumu benzersiz bir şekilde belirtmek için bilgi kaydetmek üzere [fgetpos](../c-runtime-library/reference/fgetpos.md) ve [fsetpos](../c-runtime-library/reference/fsetpos.md) tarafından kullanılır.|STDIO.H|
|`_fsize_t` (işaretsiz uzun tamsayı)|Bir dosyanın boyutunu göstermek için kullanılır.|IO.H,<br /><br /> WCHAR.H|
|`_HEAPINFO` yapısı|[_Heapwalk](../c-runtime-library/reference/heapwalk.md)için bir sonraki yığın girişi hakkında bilgi içerir.|MALLOC.H|
|`_HFILE` (void \* )|Bir işletim sisteminin dosya tanıtıcısı.|CRTDBG.H|
|`imaxdiv_t`|[Imaxdiv](../c-runtime-library/reference/imaxdiv.md) işlevi tarafından döndürülen ve hem bölümü hem de kalanı içeren değerin türü.|inttypes.h|
|`ino_t`, `_ino_t` (işaretsiz kısa)|Durum bilgilerini döndürmek için.|WCHAR.H|
|`intmax_t`|Herhangi işaretli tamsayı türünün herhangi bir değerini gösterebilen işaretli bir tamsayı türü.|stdint.h|
|`intptr_t` ( **`__int64`** hedef platforma bağlı olarak uzun tamsayı veya)|Win32 ve Win64 platformlarda bir işaretçi (veya TANITICI) depolar.|STDDEF.H ve diğer ekleme kodu dosyaları|
|`jmp_buf` dizide|[Setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) tarafından program ortamını kaydetmek ve geri yüklemek için kullanılır.|SETJMP.H|
|`lconv` yapısı|Farklı ülkelerde/bölgelerde sayısal değerlere yönelik biçimlendirme kuralları içerir. [Localeconv](../c-runtime-library/reference/localeconv.md)tarafından kullanılır.|LOCALE.H|
|`_LDOUBLE`,<br /><br /> `_LONGDOUBLE`,<br /><br /> `_LDBL12` (Long Double veya işaretsiz char dizisi)|Büyük çift değer göstermek için kullanın.|STDLIB.H|
|`_locale_t` yapısı|Geçerli yerel ayar değerlerini saklar; tüm yerel ayarlara özgü C çalışma zamanı kitaplıklarında kullanılır.|CRTDEFS.H|
|`mbstate_t`|Çok baytlı bir karakter dönüştürme durumunu izler.|WCHAR.H|
|`off_t`, `_off_t` uzun tamsayı|Dosya uzaklığı değerini gösterir.|WCHAR.H, SYS\TYPES.H|
|`_onexit_t`,<br /><br /> `_onexit_m_t` çağrısı|_Onexit tarafından döndürülen [_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md).|STDLIB.H|
|`_PNH` işlev işaretçisi|[_Set_new_handler](../c-runtime-library/reference/set-new-handler.md)bağımsız değişkeninin türü.|NEW.H|
|`ptrdiff_t` ( **`__int64`** hedef platforma bağlı olarak uzun tamsayı veya)|İki işaretçinin çıkarılmasının sonucu.|CRTDEFS.H|
|`_purecall_handler`,<br /><br /> `_purecall_handler_m`|Saf sanal bir işlev çağrıldığında çağrılan geri arama işlevini tanımlayan tür. [_Get_purecall_handler, _set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)tarafından kullanılır. Bir `_purecall_handler` işlev void dönüş türüne sahip olmalıdır.|STDLIB.H|
|`_RTC_error_fn` tür tanımla|Çalışma zamanı hata denetimlerini işleyecek olan bir işlevi tanımlayan tür. [_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)' de kullanılır.|RTCAPI.H|
|`_RTC_error_fnW` tür tanımla|Çalışma zamanı hata denetimlerini işleyecek olan bir işlevi tanımlayan tür. [_RTC_SetErrorFuncW](../c-runtime-library/reference/rtc-seterrorfuncw.md)' de kullanılır.|RTCAPI.H|
|`_RTC_ErrorNumber` listelenen|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md) ve [_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)için hata koşullarını tanımlar.|RTCAPI.H|
|`_se_translator_function`|Bir özel durumu çeviren geri arama işlevini tanımlayan tür. İlk parametre özel durum kodu, ikinci parametre özel durum kaydıdır. [_Set_se_translator](../c-runtime-library/reference/set-se-translator.md)tarafından kullanılır.|EH.H|
|`sig_atomic_t` gir|Zaman uyumsuz kesmelerin bulunması durumunda bile atomik varlık olarak değiştirilebilen nesne türü; [sinyalle](../c-runtime-library/reference/signal.md)kullanılır.|SIGNAL.H|
|`size_t` (hedef platforma bağlı olarak işaretsiz __int64 veya işaretsiz tamsayı)|İşlecin sonucu **`sizeof`** .|CRTDEFS.H ve diğer ekleme kodu dosyaları|
|`_stat` yapısı|[_Stat](../c-runtime-library/reference/stat-functions.md) ve [_fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)tarafından döndürülen dosya durumu bilgilerini içerir.|SYS\STAT.H|
|`__stat64` yapısı|[_Fstat64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) , [_stat64](../c-runtime-library/reference/stat-functions.md)ve [_wstat64](../c-runtime-library/reference/stat-functions.md)tarafından döndürülen dosya durumu bilgilerini içerir.|SYS\STAT.H|
|`_stati64` yapısı|[_Fstati64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [_stati64](../c-runtime-library/reference/stat-functions.md)ve [_wstati64](../c-runtime-library/reference/stat-functions.md)tarafından döndürülen dosya durumu bilgilerini içerir.|SYS\STAT.H|
|`terminate_function` tür tanımla|Bir tür, [Terminate](../c-runtime-library/reference/terminate-crt.md) çağrıldığında çağrılan geri çağırma işlevini tanımlar. [Set_terminate](../c-runtime-library/reference/set-terminate-crt.md)tarafından kullanılır.|EH.H|
|`time_t` (__int64 veya uzun tamsayı)|[Mksaat](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [saat](../c-runtime-library/reference/time-time32-time64.md), [csaat, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s,](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)_wctime_s, _wctime32_s, _wctime64_s, [ctime, _ctime32, _ctime64, _wctime, _wctime32](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) , _wctime64 ve [gmsaati, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)için zaman değerlerini temsil eder. Ocak 1, 1970, 0:00 UTC tarihinden beri geçen saniye sayısı. _USE_32BIT_TIME_T tanımlanmışsa, `time_t` uzun bir tamsayıdır. Tanımlı değilse, 64-bit bir tamsayıdır.|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|`__time32_t` (uzun tamsayı)|[Mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [gmsaati, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) ve [localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)zaman değerlerini temsil eder.|CRTDEFS.H, SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|`__time64_t` (**`__int64`**)|[Mktime, _mktime32, _mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [_ctime64, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), ctime_s, _ctime32_s, [_ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md) ve [_time64](../c-runtime-library/reference/time-time32-time64.md)zaman değerlerini temsil eder.|TIME.H,<br /><br /> SYS\STAT.H,<br /><br /> SYS\TIMEB.H|
|`_timeb` yapısı|[_Ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s _ftime64_s,](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) geçerli sistem saatini depolamak için kullanılır.|SYS\TIMEB.H|
|`__timeb32` yapısı|Geçerli sistem saatini depolamak için [_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) tarafından kullanılır.|SYS\TIMEB.H|
|`__timeb64` yapısı|[_Ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) ve [_ftime_s, _ftime32_s _ftime64_s,](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) geçerli sistem saatini depolamak için kullanılır.|SYS\TIMEB.H|
|`tm` yapısı|[Asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md), [gmsaati, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), gmtime_s, [_gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), [localtime, _localtime32](../c-runtime-library/reference/localtime-localtime32-localtime64.md), _localtime64, localtime_s, _localtime32_s [,](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)_localtime64_s, [mktime](../c-runtime-library/reference/mktime-mktime32-mktime64.md) , _mktime32, _mktime64 ve [strftime, wcsftime, _strftime_l,](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) _wcsftime_l, zaman bilgilerini depolamak ve almak için kullanılır.|TIME.H|
|`uintmax_t`|Herhangi işaretsiz tamsayı türünün herhangi bir değerini gösterebilen işaretsiz bir tamsayı türü.|stdint.h|
|`uintptr_t` ( **`__int64`** hedef platforma bağlı olarak uzun tamsayı veya)|İşaretsiz bir tamsayı veya imzasız __int64 sürümü `intptr_t` .|STDDEF.H ve diğer ekleme kodu dosyaları|
|`unexpected_function`|Bir tür, [beklenmeyen](../c-runtime-library/reference/unexpected-crt.md) çağrıldığında çağrılan geri çağırma işlevini tanımlar. [Set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)tarafından kullanılır.|EH.H|
|`_utimbuf` yapısı|Dosya değiştirme tarihlerini değiştirmek için [_utime, _wutime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime, _futime32 _futime64](../c-runtime-library/reference/futime-futime32-futime64.md) tarafından kullanılan dosya erişimini ve değişiklik zamanlarını depolar.|SYS\UTIME.H|
|`_utimbuf32` yapısı|Dosya değiştirme tarihlerini değiştirmek için [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime, _futime32,](../c-runtime-library/reference/futime-futime32-futime64.md) _futime64 tarafından kullanılan dosya erişimini ve değişiklik zamanlarını depolar.|SYS\UTIME.H|
|`__utimbuf64` yapısı|[_Utime64, _wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) ve [_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) geçerli zamanı depolamak için kullanılır.|SYS\UTIME.H|
|`va_list` yapısı|[Va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) ve [va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) makroları için gereken bilgileri tutmak için kullanılır. Çağrılan işlev, `va_list` başka bir işleve bağımsız değişken olarak geçirilebilecek tür değişkenini bildirir.|STDARG.H,<br /><br /> CRTDEFS.H|
|**`wchar_t`** geniş karakter|Uluslararası pazarlar için taşınabilir programlar yazarken faydalıdır.|STDDEF.H, STDLIB.H,<br /><br /> CRTDEFS.H,<br /><br /> SYS\STAT.H|
|`wctrans_t` gir|Yerel ayara özgü karakter eşlemelerini temsil eder.|WCTYPE.H|
|`wctype_t` gir|Herhangi bir dil karakter kümesinin tüm karakterlerini temsil edebilir.|WCHAR.H,<br /><br /> CRTDEFS.H|
|`wint_t` gir|Herhangi bir geniş karakter veya geniş dosya sonu değerini tutabilen veri nesnesinin türü.|WCHAR.H,<br /><br /> CRTDEFS.H|

## <a name="see-also"></a>Ayrıca bkz.

[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
