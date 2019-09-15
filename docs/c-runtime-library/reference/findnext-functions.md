---
title: _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
ms.date: 11/04/2016
api_name:
- _wfindnext
- _findnext
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- findnext
- _wfindnext32i64
- _tfindnext64i32
- findnext32
- findnext32i64
- wfindnext64i32
- _wfindnext
- tfindnext64
- findnexti64
- _findnexti64
- _tfindnexti64
- _findnext64i32
- tfindnexti64
- tfindnext32
- _wfindnext64i32
- findnext64i32
- _findnext
- _tfindnext32i64
- _wfindnext64
- wfindnext
- wfindnext32
- tfindnext32i64
- _findnext64
- _tfindnext64
- _wfindnext32
- findnext64
- _findnext32i64
- tfindnext
- wfindnexti64
- tfindnext64i32
- _tfindnext32
- wfindnext32i64
- wfindnext64
- _wfindnexti64
- _tfindnext
- _findnext32
helpviewer_keywords:
- _wfindnexti64 function
- _tfindnext32 function
- wfindnexti64 function
- _wfindnext32i64 function
- findnext32i64 function
- tfindnext64i32 function
- _tfindnext64i32 function
- _findnext function
- findnext64i32 function
- _tfindnext function
- findnext32 function
- tfindnext32 function
- _findnext32 function
- _tfindnext32i64 function
- _wfindnext function
- tfindnext function
- _findnext64 function
- findnext64 function
- _findnext64i32 function
- wfindnext32i64 function
- findnext function
- wfindnext32 function
- _wfindnext64i32 function
- findnexti64 function
- _wfindnext64 function
- _findnext32i64 function
- _findnexti64 function
- _tfindnext64 function
- wfindnext64i32 function
- tfindnexti64 function
- wfindnext64 function
- wfindnext function
- tfindnext64 function
- _wfindnext32 function
- tfindnext32i64 function
- _tfindnexti64 function
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
ms.openlocfilehash: 083f0f1d383472c104a1e4fcb6f3139c7a9d9c88
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957242"
---
# <a name="_findnext-_findnext32-_findnext32i64-_findnext64-_findnext64i32-_findnexti64-_wfindnext-_wfindnext32-_wfindnext32i64-_wfindnext64-_wfindnext64i32-_wfindnexti64"></a>_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64

Bir sonraki adı (varsa), önceki [_findfirst](findfirst-functions.md)çağrısında *dosyabelirtimi* bağımsız değişkeniyle eşleşen ve ardından *Info* yapısı içeriğini uygun şekilde değiştirecek şekilde bulun.

## <a name="syntax"></a>Sözdizimi

```C
int _findnext(
   intptr_t handle,
   struct _finddata_t *fileinfo
);
int _findnext32(
   intptr_t handle,
   struct _finddata32_t *fileinfo
);
int _findnext64(
   intptr_t handle,
   struct __finddata64_t *fileinfo
);
int _findnexti64(
   intptr_t handle,
   struct __finddatai64_t *fileinfo
);
int _findnext32i64(
   intptr_t handle,
   struct _finddata32i64_t *fileinfo
);
int _findnext64i32(
   intptr_t handle,
   struct _finddata64i32_t *fileinfo
);
int _wfindnext(
   intptr_t handle,
   struct _wfinddata_t *fileinfo
);
int _wfindnext32(
   intptr_t handle,
   struct _wfinddata32_t *fileinfo
);
int _wfindnext64(
   intptr_t handle,
   struct _wfinddata64_t *fileinfo
);
int _wfindnexti64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext32i64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext64i32(
   intptr_t handle,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Parametreler

*tutamaçlardan*<br/>
Önceki **_findcall**çağrısı tarafından döndürülen arama tanıtıcısı.

*bilgis*<br/>
Dosya bilgileri arabelleği.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Aksi takdirde,-1 döndürür ve hata doğasını gösteren bir değere **errno** değeri ayarlar. Olası hata kodları aşağıdaki tabloda gösterilmiştir.

|errno değeri|Koşul|
|-|-|
| **EINVAL** | Geçersiz parametre: *FileInfo* **null**. Ya da, işletim sistemi beklenmeyen bir hata döndürdü. |
| **ENOENT** | Daha fazla eşleşen dosya bulunamadı. |
| **ENOMEM** | Yeterli bellek yok veya dosya adının uzunluğu **MAX_PATH**değerini aştı. |

Geçersiz bir parametre geçirilirse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**_Findfirst** veya **_sonrabul** işlevini (ya da herhangi bir varyantları) kullanmayı bitirdikten sonra [_findclose](findclose.md) öğesini çağırmanız gerekir. Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları serbest bırakır.

Bu işlevlerin **w** ön ekine sahip çeşitlemeleri, geniş karakter sürümleridir; Aksi takdirde, bunlara karşılık gelen tek baytlı işlevlerle aynıdır.

Bu işlevlerin çeşitlemeleri 32 bit veya 64 bit zaman türlerini ve 32-bit veya 64-bit dosya boyutlarını destekler. İlk sayısal sonek (**32** veya **64**) kullanılan zaman türü boyutunu belirtir; İkinci sonek, dosya boyutunun 32-bit veya 64 bit tamsayı olarak temsil edilip edilmeyeceğini gösteren **i32** veya **i64**. Hangi sürümlerin 32-bit ve 64 bit zaman türlerini ve dosya boyutlarını desteklediği hakkında bilgi için aşağıdaki tabloya bakın. 64 bitlik bir zaman türü kullanan Çeşitlemeler, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC; ile belirtilmesine izin verir 32 bit zaman türlerini kullanan olanlar yalnızca tarihleri 23:59:59 Ocak 2038, UTC olarak temsil eder. Gece yarısı, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırdır.

Zaman boyutunu açıkça belirten sürümleri kullanmak için özel bir nedeniniz yoksa, **_sonrabul** veya **_wsonrakiniya** veya 3 GB 'tan büyük dosya boyutlarını desteklemeniz gerekiyorsa **_findnexti64** veya **_wfindnexti64**kullanın. Tüm bu işlevler 64 bitlik saat türünü kullanır. Önceki sürümlerde, bu işlevler 32 bitlik bir zaman türü kullandı. Bu bir uygulama için önemli bir değişiklik ise, eski davranışı almak için **_Use_32bit_time_t** tanımlayabilirsiniz. **_Use_32bit_time_t** tanımlanmışsa, **_sonrabul**, **_finnexti64** ve karşılık gelen Unicode sürümleri 32 bitlik bir süre kullanır.

### <a name="time-type-and-file-length-type-variations-of-_findnext"></a>Zaman türü ve dosya uzunluğu türü _sonrabul çeşitlemeleri

|İşlevler|**_Use_32bit_time_t** tanımlandı mı?|Zaman türü|Dosya uzunluğu türü|
|---------------|----------------------------------|---------------|----------------------|
|**_sonrakinibul**, **_wsonra**|Tanımsız|64 bit|32 bit:|
|**_sonrakinibul**, **_wsonra**|Tanımlı|32 bit:|32 bit:|
|**_findnext32**, **_wfindnext32**|Makro tanımından etkilenmedi|32 bit:|32 bit:|
|**_findnext64**, **_wfindnext64**|Makro tanımından etkilenmedi|64 bit|64 bit|
|**_findnexti64**, **_wfindnexti64**|Tanımsız|64 bit|64 bit|
|**_findnexti64**, **_wfindnexti64**|Tanımlı|32 bit:|64 bit|
|**_findnext32i64**, **_wfindnext32i64**|Makro tanımından etkilenmedi|32 bit:|64 bit|
|**_findnext64i32**, **_wfindnext64i32**|Makro tanımından etkilenmedi|64 bit|32 bit:|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsonrabul**|**_sonrakini bul**|**_sonrakini bul**|**_wsonrabul**|
|**_tfindnext32**|**_findnext32**|**_findnext32**|**_wfindnext32**|
|**_tfindnext64**|**_findnext64**|**_findnext64**|**_wfindnext64**|
|**_tfindnexti64**|**_findnexti64**|**_findnexti64**|**_wfindnexti64**|
|**_tfindnext32i64**|**_findnext32i64**|**_findnext32i64**|**_wfindnext32i64**|
|**_tfindnext64i32**|**_findnext64i32**|**_findnext64i32**|**_wfindnext64i32**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_sonrakini bul**|\<GÇ. h >|
|**_findnext32**|\<GÇ. h >|
|**_findnext64**|\<GÇ. h >|
|**_findnexti64**|\<GÇ. h >|
|**_findnext32i64**|\<GÇ. h >|
|**_findnext64i32**|\<GÇ. h >|
|**_wsonrabul**|\<GÇ. h > veya \<wchar. h >|
|**_wfindnext32**|\<GÇ. h > veya \<wchar. h >|
|**_wfindnext64**|\<GÇ. h > veya \<wchar. h >|
|**_wfindnexti64**|\<GÇ. h > veya \<wchar. h >|
|**_wfindnext32i64**|\<GÇ. h > veya \<wchar. h >|
|**_wfindnext64i32**|\<GÇ. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../../c-runtime-library/system-calls.md)<br/>
[fileName İşlevleri Ara](../../c-runtime-library/filename-search-functions.md)<br/>
