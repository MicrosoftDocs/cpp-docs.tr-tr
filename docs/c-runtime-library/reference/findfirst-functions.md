---
title: _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
ms.date: 4/2/2020
api_name:
- _findfirst
- _wfindfirst
- _findfirst32
- _wfindfirst32
- _findfirst32i64
- _wfindfirst32i64
- _findfirst64
- _wfindfirst64
- _findfirst64i32
- _wfindfirst64i32
- _findfirsti64
- _wfindfirsti64
- _o__findfirst32
- _o__findfirst32i64
- _o__findfirst64
- _o__findfirst64i32
- _o__wfindfirst32
- _o__wfindfirst32i64
- _o__wfindfirst64
- _o__wfindfirst64i32
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- findfirst32i64
- wfindfirst32i64
- tfindfirst64
- _findfirst64i32
- _wfindfirst32i64
- _wfindfirsti64
- wfindfirst
- _tfindfirsti64
- findfirst32
- _tfindfirst32
- _findfirsti64
- findfirst
- wfindfirst64
- wfindfirst32
- tfindfirst32
- _wfindfirst64i32
- findfirst64i32
- tfindfirst64i32
- _wfindfirst
- findfirsti64
- _findfirst32i64
- wfindfirst64i32
- _wfindfirst32
- _findfirst32
- _tfindfirst32i64
- tfindfirst
- _tfindfirst64i32
- findfirst64
- _tfindfirst
- _findfirst64
- _tfindfirst64
- tfindfirst32i64
- _findfirst
- _wfindfirst64
helpviewer_keywords:
- _tfindfirst64 function
- _wfindfirst64i32 function
- _wfindfirst32i64 function
- wfindfirst32 function
- _findfirst function
- wfindfirst64 function
- _wfindfirst function
- _findfirst64i32 function
- wfindfirst function
- _findfirst64 function
- tfindfirst32 function
- _tfindfirst64i32 function
- findfirst function
- findfirst32i64 function
- tfindfirst64 function
- _tfindfirst32 function
- tfindfirst32i64 function
- tfindfirst64i32 function
- _wfindfirsti64 function
- _findfirst32i64 function
- findfirst32 function
- findfirsti64 function
- findfirst64i32 function
- tfindfirsti64 function
- tfindfirst function
- _wfindfirst32 function
- wfindfirsti64 function
- _tfindfirsti64 function
- _tfindfirst function
- _tfindfirst32i64 function
- findfirst64 function
- _findfirst32 function
- _findfirsti64 function
- wfindfirst32i64 function
- wfindfirst64i32 function
- _wfindfirst64 function
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
ms.openlocfilehash: d83cc0913584618897cbc4aec45cb137388674b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346821"
---
# <a name="_findfirst-_findfirst32-_findfirst32i64-_findfirst64-_findfirst64i32-_findfirsti64-_wfindfirst-_wfindfirst32-_wfindfirst32i64-_wfindfirst64-_wfindfirst64i32-_wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64

*Dosya özel* değişkeninde belirtilen dosyayla eşleşen bir dosya adının ilk örneği hakkında bilgi sağlayın.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _findfirst(
   const char *filespec,
   struct _finddata_t *fileinfo
);
intptr_t _findfirst32(
   const char *filespec,
   struct _finddata32_t *fileinfo
);
intptr_t _findfirst64(
   const char *filespec,
   struct _finddata64_t *fileinfo
);
intptr_t _findfirsti64(
   const char *filespec,
   struct _finddatai64_t *fileinfo
);
intptr_t _findfirst32i64(
   const char *filespec,
   struct _finddata32i64_t *fileinfo
);
intptr_t _findfirst64i32(
   const char *filespec,
   struct _finddata64i32_t *fileinfo
);
intptr_t _wfindfirst(
   const wchar_t *filespec,
   struct _wfinddata_t *fileinfo
);
intptr_t _wfindfirst32(
   const wchar_t *filespec,
   struct _wfinddata32_t *fileinfo
);
intptr_t _wfindfirst64(
   const wchar_t *filespec,
   struct _wfinddata64_t *fileinfo
);
intptr_t _wfindfirsti64(
   const wchar_t *filespec,
   struct _wfinddatai64_t *fileinfo
);
intptr_t _wfindfirst32i64(
   const wchar_t *filespec,
   struct _wfinddata32i64_t *fileinfo
);
intptr_t _wfindfirst64i32(
   const wchar_t *filespec,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Parametreler

*Filespec*<br/>
Hedef dosya belirtimi (joker karakter içerebilir).

*Fileınfo*<br/>
Dosya bilgi arabelleği.

## <a name="return-value"></a>Dönüş Değeri

Başarılı **_findfirst,** [_findnext](findnext-functions.md) veya [_findclose](findclose.md)sonraki bir çağrıda kullanılabilecek *dosya spec* belirtimi yle eşleşen dosya veya dosya grubunu tanımlayan benzersiz bir arama tanıtıcısı döndürür. Aksi takdirde, **_findfirst** -1 döndürür ve aşağıdaki değerlerden birine **errno** ayarlar.

| errno değeri | Koşul |
|-|-|
| **Eınval** | Geçersiz parametre: *filespec* veya *fileinfo* **NULL**oldu. Veya, işletim sistemi beklenmeyen bir hata döndürür. |
| **Enoent** | Eşleştirilmeyen dosya belirtimi. |
| **ENOMEM** | Yetersiz bellek. |
| **Eınval** | Geçersiz dosya adı belirtimi veya verilen dosya adı **MAX_PATH'den**büyüktü. |

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

Geçersiz bir parametre geçirilirse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**_findfirst** veya [_findnext](findnext-functions.md) işlevi (veya herhangi bir türevleri) ile bitirdikten sonra [_findclose](findclose.md) aramanız gerekir. Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları serbest sağlar.

**W** öneki ne sahip bu işlevlerin varyasyonları geniş karakterli sürümlerdir; aksi takdirde, bunlar karşılık gelen tek bayt işlevleri ile aynıdır.

Bu işlevlerin varyasyonları 32-bit veya 64-bit zaman türlerini ve 32-bit veya 64-bit dosya boyutlarını destekler. İlk sayısal sonek (**32** veya **64**) zaman türünün boyutunu gösterir; ikinci sonek **i32** veya **i64'tür**ve dosya boyutunun 32 bit veya 64 bit tamsayı olarak temsil edilip edilmediğini gösterir. Hangi sürümlerin 32 bit ve 64 bit zaman türlerini ve dosya boyutlarını desteklediği hakkında bilgi için aşağıdaki tabloya bakın. **i32** veya **i64** soneki, zaman türünün boyutuyla aynıysa atlanır, bu nedenle **_findfirst64** da 64 bit dosya uzunluklarını destekler ve **_findfirst32** yalnızca 32 bit dosya uzunluklarını destekler.

Bu *işlevler, fileinfo* parametresi için **_finddata_t** yapısının çeşitli biçimlerini kullanır. Yapı hakkında daha fazla bilgi için [Dosya Adı Arama Fonksiyonları'na](../../c-runtime-library/filename-search-functions.md)bakın.

64 bit zaman türü kullanan varyasyonlar, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC'ye kadar ifade edilmesini sağlar. 32 bit saat türleri kullananlar tarihleri yalnızca 23:59:59'a kadar temsil ediyor 18 Ocak 2038, UTC. Midnight, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırıdır.

Zaman boyutunu açıkça belirten sürümleri kullanmak için özel bir nedeniniz yoksa, **_findfirst** veya **_wfindfirst** kullanın veya 3 GB'tan büyük dosya boyutlarını desteklemeniz **gerekiyorsa, _findfirsti64** veya **_wfindfirsti64**kullanın. Tüm bu işlevler 64 bit zaman türünü kullanır. Önceki sürümlerde, bu işlevler 32 bitlik bir zaman türü kullanmİş. Bu, bir uygulama için bir kesme değişikliğiyse, eski davranışa geri dönmek için **_USE_32BIT_TIME_T** tanımlayabilirsiniz. **_USE_32BIT_TIME_T** tanımlanırsa, **_findfirst,** **_finfirsti64**ve bunların karşılık gelen Unicode sürümleri 32 bit lik bir süre kullanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="time-type-and-file-length-type-variations-of-_findfirst"></a>_findfirst Zaman Türü ve Dosya Uzunluğu Tür Varyasyonları

|İşlevler|**tanımlanmış _USE_32BIT_TIME_T?**|Zaman türü|Dosya uzunluğu türü|
|---------------|----------------------------------|---------------|----------------------|
|**_findfirst**, **_wfindfirst**|Tanımlı değil|64 bit|32 bit|
|**_findfirst**, **_wfindfirst**|Tanımlanan|32 bit|32 bit|
|**_findfirst32**, **_wfindfirst32**|Makro tanımından etkilenmez|32 bit|32 bit|
|**_findfirst64**, **_wfindfirst64**|Makro tanımından etkilenmez|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlı değil|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlanan|32 bit|64 bit|
|**_findfirst32i64**, **_wfindfirst32i64**|Makro tanımından etkilenmez|32 bit|64 bit|
|**_findfirst64i32**, **_wfindfirst64i32**|Makro tanımından etkilenmez|64 bit|32 bit|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindfirst**|**_findfirst**|**_findfirst**|**_wfindfirst**|
|**_tfindfirst32**|**_findfirst32**|**_findfirst32**|**_wfindfirst32**|
|**_tfindfirst64**|**_findfirst64**|**_findfirst64**|**_wfindfirst64**|
|**_tfindfirsti64**|**_findfirsti64**|**_findfirsti64**|**_wfindfirsti64**|
|**_tfindfirst32i64**|**_findfirst32i64**|**_findfirst32i64**|**_wfindfirst32i64**|
|**_tfindfirst64i32**|**_findfirst64i32**|**_findfirst64i32**|**_wfindfirst64i32**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findfirst**|\<io.h>|
|**_findfirst32**|\<io.h>|
|**_findfirst64**|\<io.h>|
|**_findfirsti64**|\<io.h>|
|**_findfirst32i64**|\<io.h>|
|**_findfirst64i32**|\<io.h>|
|**_wfindfirst**|\<io.h> \<veya wchar.h>|
|**_wfindfirst32**|\<io.h> \<veya wchar.h>|
|**_wfindfirst64**|\<io.h> \<veya wchar.h>|
|**_wfindfirsti64**|\<io.h> \<veya wchar.h>|
|**_wfindfirst32i64**|\<io.h> \<veya wchar.h>|
|**_wfindfirst64i32**|\<io.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Aramaları](../../c-runtime-library/system-calls.md)<br/>
[Dosya Adı Arama Fonksiyonları](../../c-runtime-library/filename-search-functions.md)<br/>
