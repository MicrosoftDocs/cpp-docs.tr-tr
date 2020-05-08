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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 879a84b14f612992ae7ed3a96211637aaf5c4783
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911735"
---
# <a name="_findfirst-_findfirst32-_findfirst32i64-_findfirst64-_findfirst64i32-_findfirsti64-_wfindfirst-_wfindfirst32-_wfindfirst32i64-_wfindfirst64-_wfindfirst64i32-_wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64

Dosya adının, *dosyabelirtimi* bağımsız değişkeninde belirtilen dosyayla eşleşen ilk örneği hakkında bilgi sağlayın.

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

*dosyabelirtimi*<br/>
Hedef dosya belirtimi (joker karakterler içerebilir).

*bilgis*<br/>
Dosya bilgileri arabelleği.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa **_findfirst** , [_findnext](findnext-functions.md) veya [_findclose](findclose.md)için sonraki bir çağrıda kullanılabilen, *dosyabelirtimi* belirtimiyle eşleşen dosya veya dosya grubunu tanımlayan benzersiz bir arama tutamacı döndürür. Aksi takdirde, **_findfirst** -1 döndürür ve **errno** değerini aşağıdaki değerlerden birine ayarlar.

| errno değeri | Koşul |
|-|-|
| **EıNVAL** | Geçersiz parametre: *dosyabelirtimi* veya *FILEINFO* **null**. Ya da, işletim sistemi beklenmeyen bir hata döndürdü. |
| **ENOENT** | Eşleştirileceği dosya belirtimi. |
| **ENOMEM** | Yetersiz bellek. |
| **EıNVAL** | Geçersiz dosya adı belirtimi veya verilen dosya adı **MAX_PATH**daha büyük. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Geçersiz bir parametre geçirilirse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**_Findfirst** veya [_findnext](findnext-functions.md) işleviyle (veya herhangi bir çeşitle) işiniz bittiğinde [_findclose](findclose.md) çağırmanız gerekir. Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları serbest bırakır.

**W** ön ekine sahip bu işlevlerin çeşitlemeleri, geniş karakter sürümleridir; Aksi takdirde, bunlara karşılık gelen tek baytlı işlevlerle aynıdır.

Bu işlevlerin çeşitlemeleri 32 bit veya 64 bit zaman türlerini ve 32-bit veya 64-bit dosya boyutlarını destekler. İlk sayısal sonek (**32** veya **64**), zaman türünün boyutunu belirtir; İkinci sonek **i32** veya **i64**' dir ve dosya boyutunun 32-bit veya 64 bit tam sayı olarak temsil edilip edilmeyeceğini gösterir. Hangi sürümlerin 32-bit ve 64 bit zaman türlerini ve dosya boyutlarını desteklediği hakkında bilgi için aşağıdaki tabloya bakın. **İ32** veya **i64** son eki, zaman türünün boyutuyla aynıysa atlanır, bu nedenle **_findfirst64** Ayrıca 64 bitlik dosya uzunluklarını destekler ve **_findfirst32** yalnızca 32 bit dosya uzunluklarını destekler.

Bu işlevler, *FileInfo* parametresi için **_finddata_t** yapısının çeşitli biçimlerini kullanır. Yapı hakkında daha fazla bilgi için bkz. [dosya adı arama işlevleri](../../c-runtime-library/filename-search-functions.md).

64 bitlik bir zaman türü kullanan Çeşitlemeler, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC 'ye kadar ifade edilmesi için izin sağlar. 32 bitlik zaman türleri kullanan olanlar yalnızca 23:59:59 Ocak 2038 ve UTC tarihleri arasında tarihleri temsil eder. Gece yarısı, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırdır.

Zaman boyutunu açıkça belirten sürümleri kullanmak için belirli bir nedeniniz yoksa **_findfirst** veya **_wfindfirst** kullanın veya 3 GB 'tan büyük dosya boyutlarını desteklemeniz gerekiyorsa, **_findfirsti64** veya **_wfindfirsti64**kullanın. Tüm bu işlevler 64 bitlik saat türünü kullanır. Önceki sürümlerde, bu işlevler 32 bitlik bir zaman türü kullandı. Bu bir uygulama için önemli bir değişiklik ise eski davranışa dönmek için **_USE_32BIT_TIME_T** tanımlayabilirsiniz. **_USE_32BIT_TIME_T** tanımlanmışsa, **_findfirst**, **_Finfirsti64**ve bunlara karşılık gelen Unicode sürümleri 32 bitlik bir süre kullanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="time-type-and-file-length-type-variations-of-_findfirst"></a>_Findfirst için zaman türü ve dosya uzunluğu türü çeşitleri

|İşlevler|**_USE_32BIT_TIME_T** tanımlandı mı?|Zaman türü|Dosya uzunluğu türü|
|---------------|----------------------------------|---------------|----------------------|
|**_findfirst**, **_wfindfirst**|Tanımlı değil|64 bit|32 bit|
|**_findfirst**, **_wfindfirst**|Tanımlı|32 bit|32 bit|
|**_findfirst32**, **_wfindfirst32**|Makro tanımından etkilenmedi|32 bit|32 bit|
|**_findfirst64**, **_wfindfirst64**|Makro tanımından etkilenmedi|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlı değil|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlı|32 bit|64 bit|
|**_findfirst32i64**, **_wfindfirst32i64**|Makro tanımından etkilenmedi|32 bit|64 bit|
|**_findfirst64i32**, **_wfindfirst64i32**|Makro tanımından etkilenmedi|64 bit|32 bit|

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
|**_findfirst**|\<GÇ. h>|
|**_findfirst32**|\<GÇ. h>|
|**_findfirst64**|\<GÇ. h>|
|**_findfirsti64**|\<GÇ. h>|
|**_findfirst32i64**|\<GÇ. h>|
|**_findfirst64i32**|\<GÇ. h>|
|**_wfindfirst**|\<GÇ. h> veya \<wchar. h>|
|**_wfindfirst32**|\<GÇ. h> veya \<wchar. h>|
|**_wfindfirst64**|\<GÇ. h> veya \<wchar. h>|
|**_wfindfirsti64**|\<GÇ. h> veya \<wchar. h>|
|**_wfindfirst32i64**|\<GÇ. h> veya \<wchar. h>|
|**_wfindfirst64i32**|\<GÇ. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sistem çağrıları](../../c-runtime-library/system-calls.md)<br/>
[Dosya adı arama Işlevleri](../../c-runtime-library/filename-search-functions.md)<br/>
